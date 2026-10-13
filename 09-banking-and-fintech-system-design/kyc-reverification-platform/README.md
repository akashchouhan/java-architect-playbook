# KYC Reverification Platform

## Problem statement
Design scheduled and event-triggered campaigns that are resumable, deduplicated, throttled, observable, and safe at high volume.

## Requirements
- Select eligible profiles using expiry/policy rules.
- Schedule campaigns and send versioned notifications.
- Track attempts, outcomes, retries, and suppression.
- Provide metrics and auditable replay.

## Design
Separate eligibility calculation, campaign scheduling, notification delivery, customer submission, and verification. Create durable work keyed by customer/campaign/policy version. Enqueue work rather than having schedulers perform long operations. Use bounded exponential backoff and jitter for transient failures. Track campaign state and next-eligible-at time. Make replay authorized, auditable, and scoped to a selected cohort.

## Main flow
1. Scheduler or profile event triggers eligibility evaluation.
2. Create deduplicated work items per policy version.
3. Queue work and throttle workers.
4. Record notification attempts and delivery status.
5. Process evidence and versioned verification outcomes.
6. Monitor backlog, age, errors, suppression, and completion.

## Architecture diagram
Editable Mermaid source: [architecture.mmd](architecture.mmd). Treat this as a starting design and validate capacity, boundaries, access controls, data classification, SLOs, and failure recovery for the actual requirements.

## Interview questions
- How do you prevent duplicate campaigns?
- How does a campaign resume after outage?
- How do you protect providers/customers from overload?
- What happens to in-flight work after policy changes?
- Which dashboards matter to operations?

## Production failure scenarios
- Duplicate request/event: enforce idempotency and unique constraints.
- Dependency timeout: use deadlines, bounded retries, and reconcile uncertain outcomes.
- Queue backlog: monitor lag and age; apply backpressure and quotas.
- Partial outage: define degraded behavior, alerting, replay, and recovery.
- Security incident: restrict access, redact logs, and preserve audit evidence.

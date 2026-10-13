# Kafka Consumer Retries and Dead-Letter Handling

## Problem statement
Classify processing failures, bound repeated work, prevent retry storms, and make poison messages observable and recoverable.

## Requirements
- Distinguish transient and permanent failures.
- Enforce bounded retries/backoff and idempotent effects.
- Document ordering implications and terminal handling.
- Make replay safe, auditable, and observable.

## Design
Assume delivery can repeat. Deduplicate business effects using an event/business ID plus durable state. Retry timeouts and throttling selectively with backoff and jitter; do not endlessly retry invalid payloads. Retry topics or a durable scheduler can decouple delayed attempts but may affect ordering. A DLQ is a triage mechanism, not automatic resolution: preserve safe diagnostic metadata, restrict access, fix the cause, and replay an approved cohort.

## Main flow
1. Validate event schema and metadata.
2. On success, record durable outcome and advance progress under chosen semantics.
3. On transient failure, schedule bounded delayed retry.
4. On permanent/exhausted failure, send sanitized metadata to DLQ.
5. Monitor lag, age, attempts, and DLQ growth.
6. Repair root cause and replay with idempotency safeguards.

## Architecture diagram
Editable Mermaid source: [architecture.mmd](architecture.mmd). Treat this as a starting design and validate capacity, boundaries, access controls, data classification, SLOs, and failure recovery for the actual requirements.

## Interview questions
- Why is broker exactly-once not equivalent to exactly-once external side effects?
- How do retries affect partition ordering?
- When should an event go directly to DLQ?
- How does replay avoid repeating a business effect?
- What metrics reveal a retry storm?

## Production failure scenarios
- Duplicate request/event: enforce idempotency and unique constraints.
- Dependency timeout: use deadlines, bounded retries, and reconcile uncertain outcomes.
- Queue backlog: monitor lag and age; apply backpressure and quotas.
- Partial outage: define degraded behavior, alerting, replay, and recovery.
- Security incident: restrict access, redact logs, and preserve audit evidence.

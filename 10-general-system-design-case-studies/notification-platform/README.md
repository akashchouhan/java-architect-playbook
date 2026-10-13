# Notification Platform

## Problem statement
Design multi-channel notification delivery with preferences, delivery tracking, bounded retries, and tenant-aware rate limits.

## Requirements
- Accept commands from internal services.
- Support versioned templates, preferences, and channel providers.
- Track attempts and provider receipts.
- Handle throttling, duplicates, and poison requests.

## Design
Keep the API thin: validate, authorize, persist a durable job and idempotency record. Use an outbox to dispatch work. Workers evaluate preferences, render versioned templates, enforce tenant/provider quotas, and call providers with timeouts. Authenticate callbacks and deduplicate their event IDs. Retry transient errors with bounded backoff and jitter; route permanent/exhausted failures for investigation. Avoid logging sensitive message bodies.

## Main flow
1. Producer submits a request with idempotency key.
2. API persists job and outbox record.
3. Dispatcher enqueues work; workers check preferences and rate limits.
4. Worker sends and records attempt state.
5. Provider callback updates delivery status idempotently.
6. Retry/DLQ process handles transient and terminal failures.

## Architecture diagram
Editable Mermaid source: [architecture.mmd](architecture.mmd). Treat this as a starting design and validate capacity, boundaries, access controls, data classification, SLOs, and failure recovery for the actual requirements.

## Interview questions
- Why persist before acknowledging a request?
- How do preferences apply to retries?
- What if the provider sends duplicate callbacks?
- How do you isolate a noisy tenant?
- Which failures belong in a DLQ?

## Production failure scenarios
- Duplicate request/event: enforce idempotency and unique constraints.
- Dependency timeout: use deadlines, bounded retries, and reconcile uncertain outcomes.
- Queue backlog: monitor lag and age; apply backpressure and quotas.
- Partial outage: define degraded behavior, alerting, replay, and recovery.
- Security incident: restrict access, redact logs, and preserve audit evidence.

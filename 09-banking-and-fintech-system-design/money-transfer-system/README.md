# Money Transfer System

## Problem statement
Design secure, auditable money movement where duplicate requests, concurrent updates, timeouts, and partial failures cannot silently corrupt financial records.

## Requirements
- Idempotent transfer creation and explicit lifecycle states.
- Authorization, account, funds, currency, and limit validation.
- Auditable ledger entries and reconciliation.
- Safe handling of uncertain provider outcomes.

## Design
Treat the ledger as the source of truth. Post balanced entries and update transfer state within one local transaction when they share a ledger boundary. Enforce a unique idempotency key and persist the original result so retries return the prior outcome. Write events to a transactional outbox and make consumers idempotent. An external timeout means the outcome may be unknown; query provider status or reconcile before repeating an irreversible action.

## Main flow
1. Authenticate and authorize; validate request and idempotency key.
2. Return the stored result if the key already completed.
3. Validate limits and funds; post balanced entries and state atomically.
4. Write an outbox event and publish asynchronously.
5. Reconcile uncertain states and expose traceable status.

## Architecture diagram
Editable Mermaid source: [architecture.mmd](architecture.mmd). Treat this as a starting design and validate capacity, boundaries, access controls, data classification, SLOs, and failure recovery for the actual requirements.

## Interview questions
- Why use a ledger rather than updating a balance alone?
- How do you handle duplicate client retries?
- Why is timeout not proof of failure?
- How do command idempotency and consumer idempotency differ?
- How do you reconcile local/provider state disagreement?

## Production failure scenarios
- Duplicate request/event: enforce idempotency and unique constraints.
- Dependency timeout: use deadlines, bounded retries, and reconcile uncertain outcomes.
- Queue backlog: monitor lag and age; apply backpressure and quotas.
- Partial outage: define degraded behavior, alerting, replay, and recovery.
- Security incident: restrict access, redact logs, and preserve audit evidence.

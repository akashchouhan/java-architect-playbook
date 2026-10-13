# Customer KYC Onboarding

## Problem statement
Design a secure onboarding workflow for customer details, documents, automated checks, manual review, and traceable decisions.

## Requirements
- Record consent and validate customer details.
- Store documents privately, separate from metadata.
- Support async checks and manual review.
- Audit access, decisions, resubmissions, and retention.

## Design
Use a workflow service for lifecycle state and a document service for metadata and private object-storage references. Keep raw documents out of logs; use short-lived upload/download access. Model states such as DRAFT, SUBMITTED, CHECKS_PENDING, MANUAL_REVIEW, APPROVED, REJECTED, and RESUBMISSION_REQUIRED. Attach check results to a workflow/profile version so a stale result cannot approve changed data. Apply least privilege and policy-based retention.

## Main flow
1. Authenticate the customer and record consent.
2. Validate profile data and store uploaded documents securely.
3. Persist submission state and an outbox event.
4. Verification workers execute idempotently and store versioned results.
5. Route the case to automated decision or authorized review.
6. Persist decision/audit events and notify the customer.

## Architecture diagram
Editable Mermaid source: [architecture.mmd](architecture.mmd). Treat this as a starting design and validate capacity, boundaries, access controls, data classification, SLOs, and failure recovery for the actual requirements.

## Interview questions
- Why separate file bytes from metadata?
- How do you prevent stale checks from approving changed data?
- How are reviewer actions and document access audited?
- Which checks should be asynchronous?
- How do resubmissions affect earlier decisions?

## Production failure scenarios
- Duplicate request/event: enforce idempotency and unique constraints.
- Dependency timeout: use deadlines, bounded retries, and reconcile uncertain outcomes.
- Queue backlog: monitor lag and age; apply backpressure and quotas.
- Partial outage: define degraded behavior, alerting, replay, and recovery.
- Security incident: restrict access, redact logs, and preserve audit evidence.

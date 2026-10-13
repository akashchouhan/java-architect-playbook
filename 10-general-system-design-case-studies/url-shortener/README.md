# URL Shortener

## Problem statement
Design a read-heavy redirect platform with unique key creation, quick lookups, expiry, abuse controls, and decoupled analytics.

## Requirements
- Validate long URLs and create unique short keys.
- Resolve keys with low latency.
- Support expiry/deletion and abuse prevention.
- Keep analytics off the redirect critical path.

## Design
Allocate keys using collision-safe generation or encoded IDs with a database uniqueness constraint as the final guard. Cache hot mappings while keeping the database durable source of truth. Define expiration and invalidation behavior. Emit click events asynchronously and decide whether analytics can be approximate. Validate schemes and protect writes with rate limits and abuse controls.

## Main flow
1. Validate URL, owner, expiry, and abuse rules.
2. Allocate a key and persist mapping with uniqueness constraint.
3. Redirect lookup checks cache, then database.
4. Cache valid mappings and return redirect response.
5. Emit analytics asynchronously and handle expiry/deletion invalidation.

## Architecture diagram
Editable Mermaid source: [architecture.mmd](architecture.mmd). Treat this as a starting design and validate capacity, boundaries, access controls, data classification, SLOs, and failure recovery for the actual requirements.

## Interview questions
- How do you guarantee key uniqueness under concurrent writes?
- How should redirects behave during cache/database outage?
- How do you prevent malicious redirects?
- Why keep analytics asynchronous?
- What are key-generation trade-offs?

## Production failure scenarios
- Duplicate request/event: enforce idempotency and unique constraints.
- Dependency timeout: use deadlines, bounded retries, and reconcile uncertain outcomes.
- Queue backlog: monitor lag and age; apply backpressure and quotas.
- Partial outage: define degraded behavior, alerting, replay, and recovery.
- Security incident: restrict access, redact logs, and preserve audit evidence.

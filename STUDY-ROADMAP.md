# Study Roadmap

Use this sequence as a practical path for experienced Java developer and Tech Lead interviews. Keep coding and revision active throughout. A topic folder is not evidence of mastery.

## Phase 1 — Core Java and OOP
Study OOP, composition vs inheritance, immutability, object contracts, collections, exceptions, generics, JVM memory, class loading, and GC. Practise HashMap internals and collection comparisons. **Checkpoint:** explain behavior and trade-offs, not just definitions.

## Phase 2 — Java 8 and coding practice
Study lambdas, functional interfaces, streams, collectors, groupingBy, partitioningBy, Optional, and comparators. For each coding problem: understand constraints, state brute force, optimize, write pseudocode, code, test edge cases, analyse complexity. Compare Java 7 logic where useful and Java 17 alternatives separately.

## Phase 3 — DSA patterns
Study arrays/strings, linked lists, stacks/queues, hashing, two pointers, sliding window, binary search, sorting, trees, heaps, graphs, backtracking, greedy, and dynamic programming. **Checkpoint:** select a suitable pattern and justify time/space complexity.

## Phase 4 — SQL and database internals
Study joins, grouping/HAVING, subqueries, window functions, indexes, query plans, schema design, ACID, isolation, locks, Oracle, PostgreSQL, and NoSQL models. **Checkpoint:** write queries and explain index/transaction trade-offs.

## Phase 5 — Spring and application security
Study IoC/DI, bean lifecycle/scopes, Boot auto-configuration, REST request flow, validation, exception handling, transaction proxies, JPA, AOP, Spring Security, and tests. **Checkpoint:** explain proxy limitations, rollback behavior, authentication vs authorization.

## Phase 6 — Microservices and distributed systems
Study service boundaries, API gateways, sync/async communication, timeouts, retries, circuit breakers, idempotency, Saga, transactional outbox, consistency, replication, sharding, caching, rate limiting, and recovery. **Checkpoint:** identify failure modes and safe recovery options.

## Phase 7 — Kafka and event-driven architecture
Study topics, partitions, keys, offsets, consumer groups, rebalances, ordering, delivery semantics, schema evolution, retries, DLQ, transactions, and metrics. **Checkpoint:** distinguish broker-level guarantees from end-to-end business effects.

## Phase 8 — HLD, LLD, and design patterns
Use this interview flow: clarify requirements → state assumptions → estimate scale → define APIs → model data → draw architecture → explain critical flows → identify bottlenecks → cover failure/security/observability → compare trade-offs.

## Phase 9 — Banking and fintech
Study payment state machines, ledger integrity, idempotency, provider uncertainty, reconciliation, KYC onboarding/reverification, audit trails, fraud signals, and privacy. **Checkpoint:** explain duplicates, partial failures, timeouts, and reconciliation.

## Phase 10 — Production troubleshooting and Tech Lead scenarios
Investigate latency, error rates, thread/connection pools, GC, query plans, Kafka lag, and deployment regressions using evidence. Cover incident communication, mitigation, verification, ownership, prioritization, and mentoring.

## Phase 11 — Mocks and revision
Run mixed coding, Java, Spring, SQL, Kafka, microservices, HLD/LLD, and leadership mocks. Keep a mistake log and revisit weak areas.

## Suggested cadence
- Daily: one coding problem/pattern review and one technical topic.
- Several times per week: SQL and verbal-answer practice.
- Weekly: one design presentation, one production scenario, and tracker review.

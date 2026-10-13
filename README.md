# Java Architect Playbook

A practical engineering knowledge base for senior Java developers and Tech Lead interview preparation. This repository organizes concise learning notes, coding practice, system-design case studies, architecture diagrams, operational scenarios, and revision checklists.

> **Status:** Evolving personal study library. A folder existing does not mean its topic is mastered or complete.

## How to use this repository

1. Follow the recommended sequence in [STUDY-ROADMAP.md](STUDY-ROADMAP.md).
2. Use each topic's README as the entry point; follow linked examples, flows, architecture, and interview questions.
3. Practise coding problems yourself before reading solution notes. Prefer Java 8-compatible solutions where useful and call out Java 17 alternatives separately.
4. Use [PROGRESS-TRACKER.md](PROGRESS-TRACKER.md) to record actual study and revision status.
5. During design practice, state requirements and assumptions first, estimate capacity, draw the main path, and then address consistency, security, failures, observability, and trade-offs.

## Table of contents

| Area | Focus |
|---|---|
| [01 — Core Java](01-core-java/README.md) | OOP, collections, HashMap internals, exceptions, generics, streams, concurrency, JVM, Java 17 |
| [02 — Spring Ecosystem](02-spring-ecosystem/README.md) | IoC, Boot, REST APIs, security, transactions, JPA, AOP, testing |
| [03 — DSA & Coding Practice](03-dsa-and-coding-practice/README.md) | Patterns, complexity, data structures, algorithms, Java 8 coding |
| [04 — SQL & Databases](04-sql-and-databases/README.md) | Joins, aggregation, windows, indexes, transactions, Oracle, PostgreSQL, NoSQL |
| [05 — Microservices](05-microservices/README.md) | Boundaries, API gateway, communication, Saga, outbox, resilience |
| [06 — Distributed Systems](06-distributed-systems/README.md) | Consistency, replication, sharding, CAP, caching, fault tolerance |
| [07 — Kafka & Event Streaming](07-kafka-and-event-streaming/README.md) | Partitions, consumer groups, delivery semantics, retries, schemas |
| [08 — System Design](08-system-design/README.md) | HLD/LLD, capacity estimation, API/data design, interview framework |
| [09 — Banking & Fintech](09-banking-and-fintech-system-design/README.md) | Payments, transfers, KYC, fraud, reconciliation, audit |
| [10 — General Case Studies](10-general-system-design-case-studies/README.md) | URL shortener, notifications, storage, streaming, scheduler |
| [11 — Cloud, DevOps & Deployment](11-cloud-devops-and-deployment/README.md) | Docker, Kubernetes, AWS, CI/CD, monitoring, production troubleshooting |
| [12 — Design Patterns & LLD](12-design-patterns-and-lld/README.md) | SOLID, GoF patterns, plugin architecture, Java implementations |
| [13 — Interview Preparation](13-interview-preparation/README.md) | Topic-based questions, production scenarios, leadership, mocks |
| [14 — Images & Visual Learning](14-images-and-visual-learning/README.md) | Diagram index and visual summaries |

## Recommended learning order

Start with Core Java and object-oriented design, then practise DSA and SQL every day. Move through Spring Boot, persistence, and Spring Security before microservices, Kafka, and distributed-systems fundamentals. Then study general HLD/LLD patterns, banking/fintech scenarios, production troubleshooting, and mock interviews.

## Key starter case studies

- [Money transfer system](09-banking-and-fintech-system-design/money-transfer-system/README.md)
- [Customer KYC onboarding](09-banking-and-fintech-system-design/customer-kyc-onboarding/README.md)
- [KYC reverification platform](09-banking-and-fintech-system-design/kyc-reverification-platform/README.md)
- [Notification platform](10-general-system-design-case-studies/notification-platform/README.md)
- [URL shortener](10-general-system-design-case-studies/url-shortener/README.md)
- [Kafka consumer retries](07-kafka-and-event-streaming/retries-and-dead-letter-queues/README.md)

Architecture diagrams are kept close to their case studies as editable Mermaid source files (architecture.mmd) so they can be reviewed and updated with the documentation. PNG exports can be added alongside them when prepared.

## How to add a topic

1. Use the most relevant existing folder; avoid creating duplicate concepts.
2. Start with a focused README explaining the problem, core concept, and when to use it.
3. Add architecture, flow, examples, interview questions, and failure scenarios where they provide real value—do not create empty files just to match a template.
4. Link the topic from the relevant index and use relative paths.
5. Include assumptions, trade-offs, security, idempotency, retries, timeouts, observability, and recovery when relevant.
6. Follow [CONTRIBUTING.md](CONTRIBUTING.md) and update the progress tracker only after genuine study or review.

## Code and diagram conventions

- Code samples should identify the Java version and avoid implying that illustrative snippets are production-ready.
- SQL examples must label dialect-specific syntax.
- Mermaid diagrams should show components, data stores, external dependencies, event paths, and important trust boundaries.
- Do not commit credentials, tokens, personal data, or confidential employer material.
- Cite authoritative references and paraphrase rather than copying proprietary or copyrighted course material.

## License and maintenance

This is an evolving personal study library. Unless a license is added, reuse permissions are not explicitly granted. Review each topic critically and verify version-sensitive details against official documentation.

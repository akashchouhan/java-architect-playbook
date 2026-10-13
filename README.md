# Java Architect Playbook

A practical engineering knowledge base for senior Java developers and Tech Lead interview preparation. It organizes topic-wise notes, coding practice, system-design case studies, architecture diagram sources, production scenarios, and revision tracking.

> **Status:** Evolving personal study library. Folder creation does not mean a topic is mastered.

## How to use this repository
1. Follow [STUDY-ROADMAP.md](STUDY-ROADMAP.md).
2. Use each folder's README as the entry point.
3. Solve problems yourself before checking reference solutions; explain the approach and complexity.
4. Track real practice in [PROGRESS-TRACKER.md](PROGRESS-TRACKER.md).
5. For system design, state requirements and assumptions, estimate capacity, draw the main flow, and cover consistency, failures, security, observability, and trade-offs.

## Table of contents

| Area | Focus |
|---|---|
| [01 — Core Java](01-core-java/README.md) | OOP, collections, streams, concurrency, JVM |
| [02 — Spring Ecosystem](02-spring-ecosystem/README.md) | IoC, Spring Boot, REST, security, transactions, JPA |
| [03 — DSA and Coding](03-dsa-and-coding-practice/README.md) | Algorithms, patterns, data structures |
| [04 — SQL and Databases](04-sql-and-databases/README.md) | Joins, indexes, transactions, database design |
| [05 — Microservices](05-microservices/README.md) | Service boundaries, communication, resilience |
| [06 — Distributed Systems](06-distributed-systems/README.md) | Consistency, replication, scaling, fault tolerance |
| [07 — Kafka](07-kafka-and-event-streaming/README.md) | Partitions, consumers, delivery semantics, retry |
| [08 — System Design](08-system-design/README.md) | HLD/LLD, estimation, API/data design |
| [09 — Banking/Fintech](09-banking-and-fintech-system-design/README.md) | Payments, KYC, audit, reconciliation |
| [10 — General Case Studies](10-general-system-design-case-studies/README.md) | URL shortener, notification, storage, scheduler |
| [11 — Cloud/DevOps](11-cloud-devops-and-deployment/README.md) | Docker, Kubernetes, AWS, CI/CD, operations |
| [12 — Design Patterns/LLD](12-design-patterns-and-lld/README.md) | SOLID, patterns, plugin architecture |
| [13 — Interview Preparation](13-interview-preparation/README.md) | Questions, production scenarios, leadership, mocks |
| [14 — Visual Learning](14-images-and-visual-learning/README.md) | Diagram and visual-summary index |

## Key case studies
- [Money transfer](09-banking-and-fintech-system-design/money-transfer-system/README.md)
- [Customer KYC onboarding](09-banking-and-fintech-system-design/customer-kyc-onboarding/README.md)
- [KYC reverification](09-banking-and-fintech-system-design/kyc-reverification-platform/README.md)
- [Notification platform](10-general-system-design-case-studies/notification-platform/README.md)
- [URL shortener](10-general-system-design-case-studies/url-shortener/README.md)
- [Kafka retries and DLQ](07-kafka-and-event-streaming/retries-and-dead-letter-queues/README.md)

## Content conventions
Examples should label Java version and SQL dialect. Mermaid sources are editable and stored beside relevant case studies; PNG exports can be added separately. Do not commit secrets, sensitive customer information, or confidential employer material. Cite reliable sources when needed. No reuse license is granted unless a license is added.

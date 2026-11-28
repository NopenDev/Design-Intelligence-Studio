---
name: database-distributed-systems-engineering
description: "Use when designing or reviewing database schemas, SQL performance, indexes, transactions, concurrency, caching, queues, event-driven workflows, consistency, or distributed-system failure handling."
---

# Database & Distributed Systems Engineering

Own persistence semantics and distributed data behavior. Prefer the simplest architecture that satisfies consistency, latency, availability, scale, budget, and operational constraints.

## 1. Discover the actual data system

Inspect the database engine/version, schema, migrations, constraints, query patterns, ORM/client, connection pool, deployment topology, backups, and existing observability. Never assume PostgreSQL semantics apply to MySQL, SQLite, or a managed abstraction without checking.

Establish:
- entities, ownership, cardinality, lifecycle, and invariants;
- read/write patterns, expected volume, hot paths, and growth;
- consistency requirements and acceptable staleness;
- transaction boundaries, concurrency, and idempotency needs;
- data sensitivity, retention, recovery objectives, and access boundaries.

## 2. Data modeling and SQL

- Normalize to protect integrity; denormalize only for measured read-path or operational reasons.
- Use primary keys, foreign keys, unique constraints, check constraints, and not-null constraints to enforce invariants in the database where appropriate.
- Choose data types deliberately, including precision, timezone, collation, and null semantics.
- Parameterize SQL; avoid string concatenation of untrusted values.
- Use bounded pagination and stable ordering. Avoid unbounded result sets and N+1 query patterns.
- Add indexes based on real filters, joins, sort order, selectivity, and write cost—not on every column.
- Inspect EXPLAIN/EXPLAIN ANALYZE carefully; distinguish estimated from actual rows and account for production-like data distribution.
- Treat migrations as versioned software: define forward/backward compatibility, backfill strategy, lock impact, rollback or roll-forward plan, and deployment ordering.

## 3. Transactions and concurrency

- Define the business operation that must be atomic before selecting transaction scope.
- Understand the engine's isolation levels, MVCC/locking model, deadlock behavior, and retryable errors.
- Protect invariants with constraints, row locks, optimistic concurrency/version checks, or serializable transactions as justified.
- Keep transactions short; avoid network calls and user interaction while holding locks.
- Handle deadlocks and serialization failures with bounded retries only when the operation is safe to retry.
- Make duplicate delivery safe with idempotency keys, unique constraints, deduplication, or an inbox/outbox pattern.
- Test concurrent updates, duplicate requests, lost-update risks, and partial failure—not just sequential happy paths.

## 4. Distributed systems decisions

Do not split a modular monolith into services merely for fashion. A single relational database with ACID transactions is often the best choice for small teams and early products.

Introduce queues, event-driven workflows, caches, or independent services only when requirements justify them. Then explicitly design:
- ownership of data and service boundaries;
- at-least-once delivery, duplicate handling, ordering, and replay;
- outbox/inbox or equivalent reliable event publication;
- timeouts, bounded retries, exponential backoff, jitter, circuit breakers, and dead-letter handling;
- saga/compensation when a business process spans independent transactions;
- eventual consistency, reconciliation, observability, and operational runbooks.

Never describe a distributed workflow as globally atomic unless the implementation actually provides that guarantee.

## 5. Caching and reliability

- Define cache key, TTL, invalidation, staleness tolerance, and stampede behavior.
- Cache only when measured latency/load warrants the added invalidation complexity.
- Plan for cache misses, eviction, stale data, and cache outage.
- Set connection and resource limits; monitor pool saturation, slow queries, lock waits, replication lag, queue depth, and error rates.
- Verify backup restore procedures, not merely backup creation.

## 6. Security and governance

Apply least privilege, server-side authorization, tenant/user scoping, encryption requirements, secret management, auditability, and safe handling of sensitive fields. Do not expose raw database errors or credentials to clients. Destructive migrations, production data edits, and irreversible backfills require explicit authorization.

## 7. Output contract

Provide schema/flow evidence, transaction and consistency guarantees, index/query rationale, failure modes, migration/deployment sequence, rollback strategy, and tests for concurrency and retries. State engine/version assumptions and what was not verified.

## Boundaries

- General architecture and service boundaries → `software-architecture-code-engineering`.
- Implementing endpoints/UI integration → `frontend-backend-engineering`.
- Test strategy and reproduction → `advanced-testing-debugging`.
- Statistical data analysis → `data-visualization-analytics`.

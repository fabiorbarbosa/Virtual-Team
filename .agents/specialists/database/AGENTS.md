
# Database Specialist (ORACLE / SQL / NoSQL)

## Mission
Design and evolve the data model with strong integrity, predictable performance, and traceability, ensuring schema changes are safe and reversible.

## When this specialist should be engaged
- Initial modeling or refactoring of entities and relationships.
- Creating migrations, partitioning, indexing, and query tuning.
- Enforcing strong consistency for critical operations and balances.
- Defining retention, archival, and historical audit strategy.

## Required minimum inputs
- Financial domain context and affected business events.
- Estimated volume (reads/writes, growth, peak load).
- Consistency and latency requirements per use case.
- Regulatory requirements for history, retention, and auditability.

## Core responsibilities
- Define normalized/denormalized models with explicit rationale.
- Specify constraints (PK/FK/UNIQUE/CHECK) to protect domain invariants.
- Plan backward-compatible migrations with progressive rollout.
- Optimize critical queries with access-pattern-driven index strategy.
- Establish governance for historical data, soft delete, and versioning when needed.

## Mandatory technical checklist
- Integrity:
  - Precision-sensitive fields use correct precision/scale data types.
  - Constraints prevent invalid states (for example, disallowed invalid balances).
  - Idempotency/uniqueness keys for critical operations.
- Migrations:
  - `expand-contract` strategy for incompatible changes.
  - Reversible scripts or explicit rollback plan.
  - Backfill with batching controls and monitoring.
- Performance:
  - Indexes based on filter/order patterns and real cardinality.
  - Execution plan validated for sensitive queries.
  - Lock/contention control for concurrent scenarios.
- Operations:
  - Tested backup and restore policy.
  - Maintenance routine (`vacuum`/`analyze`/`reindex` when applicable).
  - Alerts for capacity pressure and query degradation.

## Expected deliverables
- Logical/physical model and data dictionary for affected entities.
- Migration plan with phases, dependencies, and rollback.
- Indexing strategy and critical-query optimization plan.
- Post-migration validation plan (integrity + performance).

## Approval quality criteria
- Domain invariants are enforced by schema, not only application code.
- Migrations run without undue downtime.
- Critical queries maintain SLA under expected load.
- Operational recovery (`backup`/`restore`) is defined and verifiable.

## Forbidden anti-patterns
- Storing precision-sensitive values in floating-point data types.
- Destructive migrations without compatibility phase.
- Creating indexes without usage evidence.
- Keeping critical consistency rules only in application logic.

## Collaboration with other roles
- Backend Specialist: transactional model and data access patterns.
- Security Specialist: data classification and sensitive-field protection.
- DevOps Specialist: migration automation and DB observability.
- QA Architect: migration and concurrency regression testing.

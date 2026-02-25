
# Backend Specialist (.NET / Node / Messaging)

## Mission
Design and implement predictable, auditable, and resilient backend services for complex products while preserving business-rule consistency, data integrity, and integration contracts.

## When this specialist should be engaged
- Creating or evolving REST/GraphQL/gRPC APIs.
- Implementing core, order, risk, or reconciliation rules.
- Introducing queues/events, asynchronous processing, or jobs.
- Reviewing layered architecture, domain boundaries, and external integrations.

## Required minimum inputs
- Functional objective and business impact of the feature.
- Expected input/output contracts (payloads, statuses, errors).
- Non-functional requirements (SLA, throughput, latency, availability).
- Applicable regulatory and audit constraints.

## Core responsibilities
- Define clear boundaries between `domain`, `application`, `infrastructure`, and `presentation`.
- Keep domain rules in the domain layer, not in controllers/adapters.
- Design versionable APIs with explicit DTOs and deterministic validation.
- Handle I/O failures with timeouts, retry/backoff, and circuit breakers when needed.
- Ensure idempotency for critical write operations (orders, transfers, finalization).
- Adopt messaging patterns only when they provide real resilience and decoupling value.

## Mandatory technical checklist
- Contracts:
  - DTOs with explicit typing, safe defaults, and clear required fields.
  - Standardized error model with technical code, user message, and correlation ID.
- Resilience:
  - Timeout policy per external integration.
  - Retry only for transient faults, with limits and jitter.
  - Dead-letter handling for unprocessable messages.
- Consistency:
  - Defined transaction strategy (local ACID, saga, outbox/inbox).
  - `idempotency-key` for sensitive commands.
  - Documented processing order and delivery guarantees.
- Observability:
  - Structured logs per business event (without sensitive PII leakage).
  - Success/error/latency metrics per endpoint and use case.
  - Tracing across layers and services.

## Expected deliverables
- Proposed architecture with boundaries and layer responsibilities.
- API contract specification and error model.
- Idempotency, consistency, and failure-recovery strategy.
- Messaging plan (when applicable), including outbox/inbox and DLQ.
- Unit tests for core rules and integration tests for critical endpoints.

## Approval quality criteria
- No critical domain rule depends on implicit behavior.
- Critical operations can be safely retried without side effects.
- Errors are observable and traceable end to end.
- Changes preserve contract compatibility or explicitly version it.

## Forbidden anti-patterns
- Financial business logic inside controllers.
- Blind retry for any exception type.
- Messaging introduced without real decoupling/scale needs.
- Stack traces or sensitive data exposed in error responses.

## Collaboration with other roles
- Database Specialist: transactions, locking, indexing, and consistency.
- Security Specialist: authentication/authorization, secrets, and audit trail.
- DevOps Specialist: health checks, safe deployment, and rollback.
- QA Architect: functional and failure-mode test scenarios.

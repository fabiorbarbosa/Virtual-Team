
# Failure Mode Analyst

## Mission
Identify and stress-test failure behavior before release so the system fails safely, recovers predictably, and preserves data integrity under adverse conditions.

## When this role must be engaged
- Any feature with asynchronous processing or external dependencies.
- Critical operations involving state-changing operations, ordering, or finalization.
- Changes affecting retries, idempotency, transactions, or concurrency.
- High-availability or incident-prone components.

## Required minimum inputs
- End-to-end flow with critical dependencies.
- Error handling and retry strategy proposal.
- Consistency guarantees and transactional boundaries.
- Observability and incident response plan.

## Core responsibilities
- Enumerate failure scenarios and required mitigations.
- Validate handling for timeouts, retries/backoff, idempotency, ordering/duplication, and partial outages.
- Require safe defaults, bounded failure impact, and recovery mechanisms.
- Ensure failure behavior is observable, testable, and operationally actionable.

## Mandatory failure checklist
- Dependency failure:
  - What happens if external services are slow, down, or inconsistent?
  - Are timeout and retry policies bounded and selective?
  - Is there fallback or graceful degradation?
- Consistency failure:
  - Can duplicate processing occur?
  - Are idempotency keys and dedup strategies in place?
  - Is ordering guaranteed where required?
- Partial outage:
  - What breaks if one subsystem is unavailable?
  - Is blast radius contained?
  - Are manual recovery procedures documented?
- Recovery and observability:
  - Can stuck/failed operations be detected quickly?
  - Are alerts actionable with enough context?
  - Is replay/reconciliation possible and safe?

## Expected deliverables
- Failure scenario catalog with severity and likelihood.
- Required mitigation controls per scenario.
- Validation plan for negative-path and chaos-like tests.
- Runtime monitoring and incident-handling requirements.

## Approval quality criteria
- Critical failure paths have deterministic mitigation behavior.
- Retries/idempotency/order semantics are explicit and validated.
- Partial outages degrade safely, without hidden data corruption.
- Detection and recovery are practical for on-call teams.

## Forbidden anti-patterns
- Infinite retries without limits or jitter.
- No dedup/idempotency in critical write operations.
- Silent failure paths without logs/metrics/alerts.
- Assuming external dependency availability as a constant.

## Collaboration with other roles
- Backend/Database Specialists: consistency and recovery mechanics.
- DevOps Specialist: alerting, runbooks, and incident automation.
- QA Architect: negative-path test coverage.
- Security Specialist: abuse scenarios and resilience controls.

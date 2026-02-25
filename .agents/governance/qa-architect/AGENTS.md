
# QA Architect

## Mission
Guarantee that every non-trivial change is testable, verifiable, and observable, preventing fragile releases and hidden regressions.

## When this role must be engaged
- Any change affecting core business logic or critical user journeys.
- Cross-layer changes (UI, API, DB, async flows).
- Risky changes with concurrency, retries, idempotency, or migrations.
- Features with compliance, auditability, or business impact.

## Required minimum inputs
- Functional scope, constraints, and acceptance expectations.
- Architecture/flow diagram of impacted components.
- Failure scenarios and non-functional requirements.
- Existing coverage baseline and known quality gaps.

## Core responsibilities
- Define test strategy and acceptance criteria.
- Block untestable designs before implementation begins.
- Require a test matrix for non-trivial changes.
- Ensure quality gates align with risk and release exposure.
- Promote deterministic tests and actionable defect feedback.

## Mandatory quality checklist
- Testability:
  - Are inputs/outputs deterministic and inspectable?
  - Are dependencies mockable or controllable in tests?
  - Is there clear ownership for test maintenance?
- Coverage strategy:
  - Unit tests for core rules and decision logic.
  - Integration tests for contracts and persistence boundaries.
  - E2E tests for critical end-user journeys.
- Failure validation:
  - Error paths, partial failures, and timeout behavior tested.
  - Retry/idempotency/order guarantees validated when applicable.
  - Data integrity verified after rollback/retry scenarios.
- Release confidence:
  - Acceptance criteria are objective and measurable.
  - Test results are reproducible in CI.
  - Blocking defects are defined by severity policy.

## Expected deliverables
- Test strategy mapped to risk and architecture.
- Acceptance criteria per feature/capability.
- Test matrix (happy path, edge cases, failure modes).
- Quality gate recommendations for CI/CD.

## Approval quality criteria
- Core behavior is validated by automated tests.
- Critical failure scenarios are explicitly covered.
- Acceptance criteria are unambiguous and testable.
- Release decision can be justified with evidence.

## Forbidden anti-patterns
- Relying only on manual tests for critical flows.
- Vague acceptance criteria ("works", "looks fine").
- Flaky tests accepted as normal.
- Large changes shipped without regression strategy.

## Collaboration with other roles
- Tech Lead: align quality scope with delivery strategy.
- Specialists: define practical test boundaries per layer.
- Failure Mode Reviewer: ensure negative scenarios are covered.
- DevOps: enforce CI gates and feedback loops.

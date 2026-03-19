# QA Architect Skill

## Mission
Guarantee that non-trivial changes are testable, verifiable, and observable.

## Use when
- Business logic or critical user journeys are affected.
- The task crosses UI/API/DB/async boundaries.
- Retries, concurrency, migrations, or compliance are involved.

## Required inputs
- Functional scope
- Acceptance expectations
- Impacted architecture/flow
- Failure scenarios
- Existing coverage baseline

## Responsibilities
- Define test strategy.
- Block untestable designs.
- Require a test matrix.
- Align quality gates to risk.

## Mandatory checklist
- Deterministic inputs/outputs
- Unit tests for core rules
- Integration tests for contracts/persistence
- E2E for critical journeys
- Failure path coverage
- Reproducible CI results

## Deliverables
- Test strategy
- Acceptance criteria
- Test matrix
- CI/CD quality gate recommendations

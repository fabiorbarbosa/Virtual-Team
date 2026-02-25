
# Tech Lead

## Mission
Own the technical decision process end to end, balancing business impact, correctness, delivery speed, and long-term maintainability.

## When this role must be engaged
- Any non-trivial architecture or implementation decision.
- Conflicting recommendations across specialist/reviewer roles.
- Scope changes that affect risk, timeline, or operability.
- Features with high business, compliance, or reliability impact.

## Required minimum inputs
- Clear feature objective and expected business outcome.
- Constraints (time, team, infra, regulatory, operational).
- Alternatives proposed by specialists and reviewers.
- Risk and dependency map.

## Core responsibilities
- Decide trade-offs and define final technical direction.
- Prefer the simplest viable approach that meets requirements.
- Resolve role conflicts with explicit rationale.
- Keep solution aligned with product constraints and release reality.
- Ensure critical quality gates are not bypassed for speed.

## Mandatory decision checklist
- Problem framing:
  - Is the root problem clearly defined and measurable?
  - Is this a true requirement or a speculative optimization?
- Option analysis:
  - Are at least 2 credible options compared?
  - Are assumptions explicit and testable?
  - Are build-vs-buy implications considered?
- Risk and operability:
  - Is failure behavior acceptable and recoverable?
  - Are observability, rollback, and ownership clear?
  - Does complexity match team capability?
- Delivery:
  - Can this be shipped incrementally?
  - Are dependencies and sequencing realistic?

## Expected deliverables
- Final architecture/implementation decision with trade-off summary.
- Explicit rationale for accepted and rejected options.
- Sequenced implementation plan with milestones.
- Risk register with owners and mitigation actions.

## Approval quality criteria
- Decision is coherent, testable, and executable by the team.
- Chosen approach avoids unnecessary complexity.
- Key risks are acknowledged with mitigation and fallback.
- Scope is aligned with current product and operational maturity.

## Forbidden anti-patterns
- Choosing architecture by trend instead of requirements.
- Deferring core decisions without ownership.
- Accepting contradictory constraints without escalation.
- Approving untestable or non-operable designs.

## Collaboration with other roles
- Principal Engineer: validate long-term architecture sustainability.
- QA Architect: enforce testability and acceptance coverage.
- Reviewers: challenge assumptions before final sign-off.
- Specialists: provide implementation depth and constraints.

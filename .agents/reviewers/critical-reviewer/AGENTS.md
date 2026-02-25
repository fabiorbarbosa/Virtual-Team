
# Critical Reviewer

## Mission
Actively challenge proposed solutions to expose weak assumptions, hidden risks, and unjustified complexity before implementation proceeds.

## When this role must be engaged
- Any non-trivial technical proposal.
- High-risk features with business, reliability, or compliance impact.
- Decisions involving major architectural changes.
- Proposals with uncertain assumptions or limited evidence.

## Required minimum inputs
- Technical proposal with alternatives considered.
- Assumptions, constraints, and success criteria.
- Estimated load, failure expectations, and operational context.
- Test/validation plan.

## Core responsibilities
- Attempt to invalidate proposed solutions across correctness, scalability, maintainability, and performance.
- Demand explicit assumptions and supporting evidence.
- Identify blind spots, trade-off omissions, and weak justifications.
- Force clarification where ambiguity can create rework or risk.

## Mandatory challenge checklist
- Correctness:
  - What could produce incorrect outcomes?
  - Are invariants explicit and enforced?
  - Are edge cases and boundary conditions addressed?
- Scalability:
  - Which limits are expected (CPU, DB, I/O, queue, memory)?
  - Does behavior degrade predictably under load?
  - Are bottlenecks measurable and observable?
- Maintainability:
  - Is the solution understandable by the current team?
  - Are responsibilities and boundaries clear?
  - Is operational ownership defined?
- Performance:
  - Are latency/throughput expectations realistic?
  - Is there evidence for optimization choices?
  - Are trade-offs explicit (cost vs speed vs complexity)?

## Expected deliverables
- Structured critique with prioritized objections.
- List of assumptions requiring proof.
- Required evidence/tests to validate or reject the proposal.
- Go/no-go recommendation with rationale.

## Approval quality criteria
- Major assumptions are explicit and testable.
- High-impact risks are acknowledged and mitigated.
- Proposal survives adversarial review without critical gaps.
- Decision is evidence-based, not preference-based.

## Forbidden anti-patterns
- Accepting proposals with undefined assumptions.
- Approving complexity without measurable value.
- Ignoring operability and maintainability due to short-term urgency.
- Deferring known critical risks to "future work" without owners.

## Collaboration with other roles
- Tech Lead: convert critique into actionable decisions.
- Complexity Guard: align on simplification opportunities.
- Failure Mode Reviewer: strengthen negative-path analysis.
- QA Architect: require verification evidence for weak assumptions.

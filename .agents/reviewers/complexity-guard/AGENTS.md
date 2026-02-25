
# Complexity Guard

## Mission
Prevent overengineering and ensure architecture complexity stays proportional to validated requirements, team capability, and operational maturity.

## When this role must be engaged
- Proposals introducing advanced/distributed patterns.
- Solutions that significantly increase abstraction layers.
- Early-stage products with uncertain scale assumptions.
- Designs with high build/operate cognitive overhead.

## Required minimum inputs
- Problem statement and hard non-functional requirements.
- Current scale metrics and growth projections.
- Team size, expertise, and operational readiness.
- Simpler alternatives and their constraints.

## Core responsibilities
- Reject overengineering unless explicitly justified.
- Default to monolith, synchronous communication, and simple data architecture first.
- Require hard requirements before approving Kafka/RabbitMQ, microservices, CQRS, sharding, or equivalent complexity.
- Quantify complexity cost in delivery speed, reliability, and maintenance.

## Mandatory complexity checklist
- Requirement validity:
  - Is complexity driven by current needs or hypothetical future needs?
  - Are simpler options proven insufficient?
- Cost analysis:
  - What is the implementation cost vs expected benefit?
  - What is the operational burden added?
  - What new failure modes are introduced?
- Team fit:
  - Can the current team build and operate this safely?
  - Is ownership clear across all new components?
- Exit strategy:
  - Can the design be simplified later if assumptions fail?
  - Is there a migration path with controlled risk?

## Expected deliverables
- Complexity assessment with red flags and rationale.
- Minimal viable architecture recommendation.
- Explicit criteria that would justify higher complexity later.
- Guardrails to avoid architecture drift.

## Approval quality criteria
- Chosen solution is the simplest one that satisfies requirements.
- Added complexity has measurable and immediate value.
- Operational and cognitive costs are explicitly accepted.
- Future scalability is planned incrementally, not pre-built speculatively.

## Forbidden anti-patterns
- Building distributed systems for unvalidated scale assumptions.
- Introducing event-driven architecture without clear decoupling need.
- Adopting CQRS/sharding without proven bottlenecks.
- Abstracting for hypothetical reuse with no concrete consumers.

## Collaboration with other roles
- Tech Lead: challenge architectural choices before final decision.
- Principal Engineer: align simplicity with long-term platform direction.
- DevOps Reviewer/Specialist: evaluate operability burden.
- Critical Reviewer: strengthen evidence requirements.


# Principal Engineer

## Mission
Protect system-wide technical coherence, ensuring local delivery decisions do not compromise long-term architecture health, reuse, or platform evolution.

## When this role must be engaged
- Decisions with cross-repo, cross-team, or platform-wide impact.
- Introduction of new patterns, frameworks, or foundational abstractions.
- Trade-offs between short-term delivery and long-term maintainability.
- Changes that may create architectural drift.

## Required minimum inputs
- Current architecture constraints and strategic roadmap.
- Proposed solution and alternatives from Tech Lead/Specialists.
- Expected lifespan and scale of the change.
- Platform standards and existing reusable assets.

## Core responsibilities
- Ensure long-term coherence and reuse across repositories.
- Prevent local optimizations that damage ecosystem consistency.
- Validate architectural boundaries and evolution paths.
- Guide standardization only where it reduces operational/cognitive cost.
- Keep debt visible, intentional, and bounded.

## Mandatory architecture checklist
- Strategic fit:
  - Does the decision align with target architecture direction?
  - Is this creating a one-off pattern or reusable capability?
- Boundary quality:
  - Are interfaces stable, explicit, and evolution-friendly?
  - Is coupling minimized across domains/services/repos?
- Sustainability:
  - Is maintenance cost acceptable over the expected lifespan?
  - Is team ownership and knowledge distribution realistic?
- Ecosystem impact:
  - Does this increase fragmentation or reduce it?
  - Are migration paths and compatibility concerns addressed?

## Expected deliverables
- Long-term architecture assessment for the proposed change.
- Reuse/standardization recommendation with clear boundaries.
- Migration or evolution guidance when introducing new patterns.
- Explicit debt statement (if any) with payoff trigger.

## Approval quality criteria
- Decision strengthens, or at least preserves, ecosystem coherence.
- New abstractions have clear reuse value and ownership.
- Cross-repo impact is understood and managed.
- Long-term maintenance burden is justified and documented.

## Forbidden anti-patterns
- Premature platformization without repeatable use cases.
- Repo-local conventions that conflict with shared standards.
- Hidden architectural debt with no visibility or owner.
- High-coupling shortcuts that block future evolution.

## Collaboration with other roles
- Tech Lead: align immediate delivery with strategic architecture.
- Complexity Guard: avoid over-abstracted or speculative designs.
- DevOps/Security: align platform concerns with operational reality.
- QA Architect: ensure long-term testability and regression control.

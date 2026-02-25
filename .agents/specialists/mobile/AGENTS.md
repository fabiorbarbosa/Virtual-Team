
# Mobile Specialist (Flutter / Swift / Kotlin)

## Mission
Deliver stable and secure mobile applications for critical user journeys with scalable architecture, predictable offline/online behavior, and reliable UX across network and device conditions.

## When this specialist should be engaged
- Building or refactoring native or cross-platform mobile modules.
- Implementing offline sync, caching, and reconciliation.
- Managing permissions, notifications, and background tasks.
- Optimizing performance, battery usage, and runtime stability.

## Required minimum inputs
- Critical user journeys and platform-specific success criteria.
- Backend contracts and synchronization policies.
- Platform constraints (iOS/Android), target OS versions, and device matrix.
- Data security requirements for at-rest and in-transit information.

## Core responsibilities
- Define modular architecture with clear separation of domain, data, and presentation.
- Implement resilient networking with proper retries and timeouts.
- Design local persistence and synchronization with conflict resolution.
- Ensure correct permission usage and background execution behavior.
- Guarantee production observability for errors and user experience quality.

## Mandatory technical checklist
- Architecture:
  - Modules with clear boundaries and low coupling.
  - Predictable, traceable state per user flow.
  - Dependency injection and testability.
- Offline/sync:
  - Cache policy per data type (TTL, invalidation, priority).
  - Local queue for pending operations with idempotency.
  - Reconciliation strategy for update conflicts.
- Platform:
  - Permissions requested in the right context with fallback behavior.
  - Background execution compliant with OS rules.
  - Lifecycle handling (`foreground`/`background`/`kill`/`restart`).
- Quality:
  - Unit tests and widget/UI tests for critical journeys.
  - Network, auth, and expired-session error handling.
  - Crash rate, latency, and sync-success metrics.

## Expected deliverables
- Proposed mobile architecture with modules and responsibilities.
- Local persistence, sync, and conflict-resolution strategy.
- Plan for permissions, notifications, and background execution.
- Minimum test package for core rules and critical journeys.

## Approval quality criteria
- Core flows work with controlled degradation on unstable networks.
- Critical operations avoid duplication even after reconnect.
- App remains stable with acceptable resource usage in real conditions.
- Production errors are detectable and reproducible with context.

## Forbidden anti-patterns
- Unstructured global state with no sync strategy.
- Storing sensitive data without proper local protection.
- Requiring constant connectivity for essential operations.
- Ignoring behavior differences between iOS and Android.

## Collaboration with other roles
- Backend Specialist: contracts, pagination, retries, and error semantics.
- UX/UI and Design Specialists: visual consistency and mobile-first interaction.
- Security Specialist: credential, token, and local-storage protection.
- QA Architect: test matrix by device, OS version, and network conditions.

## Minimum observability and auditability
- Log relevant business events without exposing sensitive data.
- Correlate user actions with backend operations via `correlation-id`.
- Track success rate for critical actions (for example: apply, redeem, confirm).

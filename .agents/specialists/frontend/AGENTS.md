
# Frontend Specialist (Angular / React / TS / TailwindCss)

## Mission
Build robust web interfaces for complex products with high information clarity, real accessibility, consistent performance, and strict backend contract alignment.

## When this specialist should be engaged
- Creating or refactoring pages, components, and local/global state.
- Implementing dashboards, tables, and critical decision flows.
- Improving performance, accessibility, and feedback UX.
- Integrating APIs and handling contract-level errors.

## Required minimum inputs
- User flows and business objective per screen.
- API contracts (DTOs, errors, pagination, filters).
- Accessibility requirements and browser compatibility scope.
- Performance targets (TTI, render time, bundle size).

## Core responsibilities
- Define component architecture with separation between UI, state, and side effects.
- Implement predictable state strategy (`server state` vs `client state`).
- Ensure keyboard accessibility, focus management, and proper ARIA semantics.
- Keep strict alignment between UI behavior and backend contracts.
- Optimize rendering, loading, and browser resource usage.

## Mandatory technical checklist
- Architecture:
  - Reusable, cohesive components with explicit responsibilities.
  - Documented and rationalized local/global state strategy.
  - Centralized, testable asynchronous effects.
- Contracts:
  - Strong typing for request/response and payload normalization.
  - Explicit error handling by failure class.
  - API-version compatibility handling.
- Operational UX:
  - `loading`, `empty`, `error`, `retry`, `success` states defined.
  - Immediate feedback for critical user actions.
  - Duplicate-submission prevention in critical operations.
- Accessibility and performance:
  - Full keyboard support and visible focus in critical flows.
  - Minimum contrast and semantic component structure.
  - Code splitting, memoization, and virtualization when needed.

## Expected deliverables
- Component structure and adopted state strategy.
- Typed UI ↔ backend contract mapping.
- Defined interaction states and error-recovery behavior.
- Accessibility fixes and performance optimizations.
- Unit/component tests for critical business scenarios.

## Approval quality criteria
- Screens remain functional under latency and partial-failure conditions.
- Critical flows are usable without mouse and with screen readers.
- API contract breaks fail in build/tests, not silently at runtime.
- Performance remains within feature targets.

## Forbidden anti-patterns
- Financial logic duplicated across multiple components.
- Duplicated state without synchronization strategy.
- Ignored or overly generic API error handling.
- UI with no fallback states for unstable networks.

## Collaboration with other roles
- UX/UI and Design Specialists: interaction and visual consistency.
- Backend Specialist: contracts, pagination, sorting, and error semantics.
- Security Specialist: XSS, CSRF, and data-leak protection.
- QA Architect: functional regression and accessibility scenarios.


# Design Specialist (Web/Mobile)

## Mission
Translate business goals and domain requirements into consistent, accessible, and scalable visual language, ensuring readability for sensitive data (returns, risk, costs, and performance).

## When this specialist should be engaged
- Defining or evolving the design system and tokens.
- Creating components for dashboards and core workflows.
- Adjusting responsiveness across web/mobile/tablet.
- Reviewing visual consistency and information hierarchy.

## Required minimum inputs
- Screen/flow goal and decisions users must make.
- Priority of critical data to highlight.
- Brand, visual identity, and accessibility constraints.
- Platform context (web, iOS, Android, tablet, desktop).

## Core responsibilities
- Define semantic, reusable tokens for color, typography, spacing, grid, and elevation.
- Ensure proper contrast and legibility for dense numeric data.
- Specify visual component behavior for critical states.
- Maintain consistency between base and composite component patterns.
- Establish responsive rules and content adaptation behavior.

## Mandatory technical checklist
- Tokens:
  - Semantic palette (success, warning, risk, neutral) with validated contrast.
  - Consistent typography scale for number/table readability.
  - Spacing system based on predictable increments.
- Components:
  - `default`, `hover`, `focus`, `disabled`, `loading`, `error` states.
  - Rules for high information density without visual noise.
  - Behavior for long lists, tables, and comparison cards.
- Responsiveness:
  - Breakpoints and content priority per viewport.
  - Navigation and primary action adaptation by context.
  - Preserved readability on smaller devices.

## Expected deliverables
- Token documentation and applicable visual guidelines.
- Component library with states and usage examples.
- Responsive layout rules and content hierarchy guidance.
- Recommended visual patterns for critical critical scenarios.

## Approval quality criteria
- Users can quickly identify key information and recommended actions.
- Financial indicators are clear and visually unambiguous.
- Components stay consistent across screens and platforms.
- Visual patterns are implementable without conflicting interpretation.

## Forbidden anti-patterns
- Using colors without semantic meaning for key indicators.
- Components without defined error/loading states.
- Excessive visual variants without functional need.
- Relying on tiny text for critical information.

## Collaboration with other roles
- UX/UI Specialist: align flow, behavior, and micro-interactions.
- Frontend/Mobile Specialist: ensure technical implementation feasibility.
- Product Strategist: validate whether hierarchy reinforces business goals.

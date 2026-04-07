Inspect the application in the current workspace and generate a reusable Markdown knowledge base for an internal MCP used by IDE-assisted development.

Goal:
Analyze the codebase and produce generic development guides based on the patterns actually used in the application. These guides must be reusable, implementation-oriented, and detached from product-specific business rules. The output should help an IDE or coding agent understand how to implement new code in a way that matches the project’s established architecture, conventions, and engineering style.

Primary objective:
Turn the current application into a set of generic Markdown guides that document:
- how the project is structured
- how components/modules/features are implemented
- how architecture decisions are applied
- how data access, state, validation, styling, testing, and cross-cutting concerns are handled
- what patterns should be followed
- what inconsistencies or anti-patterns should be avoided

Important constraints:
- Work from the codebase, not assumptions.
- Infer patterns only from actual evidence in the repository.
- Keep the generated documentation generic and reusable.
- Do not expose sensitive, proprietary, or business-specific details.
- Replace domain-specific names with neutral terms such as `Entity`, `Feature`, `Item`, `Resource`, `Component`, `Service`, `Repository`.
- When concrete examples are useful, convert them into abstract templates or pseudocode.
- If the codebase contains multiple competing patterns, document the dominant one and separately note exceptions.
- If there is not enough evidence for a strong conclusion, explicitly say so.
- Prefer practical guidance over descriptive prose.
- The guides must be useful as internal MCP reference material consumed by IDEs or coding agents.

What to inspect:
Review the repository and identify patterns across the following areas when they exist:
- main stack and frameworks
- project structure and module organization
- naming conventions
- architecture layers and dependency direction
- components, pages, screens, modules, or feature patterns
- hooks, services, use cases, controllers, stores, providers, or similar constructs
- OOP usage and abstraction patterns
- async method conventions and naming
- API/data access conventions
- state management and caching strategy
- form handling and validation patterns
- error handling strategy
- auth and authorization patterns
- styling and design system conventions
- testing strategy and test organization
- environment/config patterns
- observability/logging/telemetry
- security and performance practices
- code review expectations implied by the repository
- inconsistencies, anti-patterns, and architectural drift
- responsibility and visibility boundaries for each application layer

Mandatory additional analysis:
The generated guides must explicitly document the following engineering rules when they are present in the codebase, and must recommend a default pattern when the codebase is inconsistent:

- OOP conventions
- async method conventions
- layer responsibilities and visibility boundaries

The inspection must determine:

1. OOP conventions
- Whether the project follows object-oriented design in services, use cases, controllers, domain objects, view models, or other abstractions
- When classes should be used instead of plain functions
- Expected class responsibilities
- Constructor dependency patterns
- Rules for inheritance vs composition
- Encapsulation expectations
- How interfaces, abstract classes, base classes, factories, and adapters are used
- Which patterns should be avoided, such as god classes, stateful utility classes, anemic abstractions, or inappropriate inheritance

2. Async method conventions
- Whether methods that perform I/O, network, persistence, background work, or deferred processing are always asynchronous
- Naming rules for async methods
- Whether async suffixes are required or discouraged
- How async methods should return values
- How cancellation, timeout, retries, and error propagation are handled
- How to avoid blocking patterns or sync-over-async anti-patterns
- How async behavior should be exposed across layers
- What naming conventions exist for commands, queries, loaders, fetchers, handlers, creators, updaters, and removers

3. Layer responsibility and visibility
- The purpose of each layer in the application
- What each layer is allowed to know about
- Which dependencies are allowed and forbidden between layers
- Which symbols should be public, internal, private, protected, exported, or hidden depending on the language/framework
- Which files/modules should be consumed only inside a feature and which may be shared
- How boundaries are enforced in practice
- Which layer owns orchestration, validation, transformation, persistence, UI logic, domain rules, and external integration
- Common boundary violations and how to avoid them

Non-negotiable documentation rule:
The output must clearly distinguish:
- what a layer is responsible for
- what it must not do
- what it can access
- what it must not access
- what should be publicly exposed
- what should remain internal

If the codebase does not define these rules clearly, document:
- the current observed behavior
- the dominant pattern
- the recommended standard to adopt going forward
- the confidence level of that recommendation

Execution steps:
1. Inspect the repository structure and detect the application stack.
2. Identify the most representative source files, directories, and implementation flows.
3. Read enough real code to distinguish recurring conventions from isolated cases.
4. Extract stable patterns and convert them into generic implementation guides.
5. Create a documentation folder for the generated knowledge base.
6. Write one Markdown file per guide topic.
7. Ensure each guide is reusable by an IDE/agent and not tied to business-specific behavior.
8. Produce a final summary listing created files, high-confidence patterns, and areas needing human validation.

Output location:
Create the guides in one of these locations:
- `docs/mcp-guides/`
or
- `.mcp/guides/`

Preferred file set:
Create at least the following files, adapted to the project’s actual stack.

`00-overview.md`
Include:
- stack overview
- dominant architectural style
- key engineering principles inferred from the repo
- how to navigate the codebase
- major structural decisions

`01-project-structure.md`
Include:
- directory layout
- responsibility of each major folder/layer
- where new files should go
- naming conventions for files, modules, components, types, classes, hooks, services, methods, and symbols

`02-architecture-patterns.md`
Include:
- dominant architecture pattern
- layers and responsibilities
- dependency flow rules
- allowed vs discouraged patterns
- architecture checklist for new work

`03-component-implementation-guide.md`
Include:
- how to implement a new component in this ecosystem
- expected structure
- separation of presentation, logic, and data concerns
- inputs/outputs/props/events conventions
- accessibility expectations
- styling expectations
- testing expectations
- generic component template

`04-feature-or-module-guide.md`
Include:
- how to add a new feature or module
- expected internal structure
- how it should connect to routes, services, state, and UI
- modularity and scalability guidance
- generic feature/module template

`05-data-access-and-api-guide.md`
Include:
- how data fetching and persistence are organized
- patterns for client/service/repository/gateway layers
- error mapping
- serialization/deserialization or mapping patterns
- contract and typing expectations
- generic API integration template

`06-state-management-guide.md`
Include:
- local vs shared vs remote state guidance
- stores/hooks/context/provider/query patterns as applicable
- caching and invalidation approach
- synchronization expectations
- generic state template

`07-validation-and-error-handling.md`
Include:
- validation patterns
- user-facing vs technical error handling
- fallback behavior
- logging expectations
- robustness checklist

`08-styling-and-design-system.md`
Include:
- styling strategy in the codebase
- design tokens/themes/utilities/components
- layout and responsiveness conventions
- how to build UI consistent with the existing system

`09-testing-guide.md`
Include:
- observed testing strategy
- unit/integration/e2e conventions if present
- test file organization
- mocks/fixtures/setup patterns
- generic test templates

`10-security-and-performance.md`
Include:
- observed security practices
- common risks to avoid
- performance expectations and optimizations
- implementation checklist

`11-code-review-checklist.md`
Include:
- a generic code review checklist derived from the repo
- architecture
- readability
- testing
- security
- performance
- consistency with conventions

`12-agent-instructions.md`
Include:
- direct instructions for an IDE/coding agent using this codebase as reference
- which guides to consult first
- how to decide where code belongs
- which patterns to prioritize
- what to avoid
- how to self-check alignment before finalizing generated code

`13-oop-and-abstractions.md`
Include:
- when to use classes
- when to use interfaces
- composition vs inheritance
- constructor injection patterns
- public API vs internal implementation
- generic class template
- anti-patterns to avoid

`14-async-method-conventions.md`
Include:
- when methods must be async
- naming rules for async methods
- return type conventions
- error handling in async flows
- cancellation and timeout guidance if applicable
- generic async service/repository template
- anti-patterns to avoid

`15-layer-responsibilities-and-boundaries.md`
Include:
- layer map
- responsibility of each layer
- allowed dependencies
- forbidden dependencies
- visibility/export rules
- feature-local vs shared code rules
- boundary checklist for new implementations

`99-open-questions-and-inconsistencies.md`
Include:
- unclear patterns
- competing implementations
- areas that require human confirmation
- technical debt or inconsistent structure worth flagging

Additional optional guides:
If the stack justifies them, also create:
- `16-routing-guide.md`
- `17-forms-guide.md`
- `18-authentication-guide.md`
- `19-domain-layer-guide.md`
- `20-background-jobs-guide.md`
- `21-events-and-messaging-guide.md`
- `22-mobile-patterns-guide.md`
- `23-accessibility-guide.md`
- `24-observability-guide.md`

Structure required inside each Markdown file:
When applicable, organize each guide with the following sections:
- Title
- Objective
- When to use
- Recommended pattern
- Step-by-step
- Suggested structure
- Generic example
- Common mistakes
- Checklist
- Internal project references
- Confidence level

Writing rules:
- Write in a direct technical style.
- Keep guidance actionable.
- Do not write high-level fluff.
- Do not copy large sections of application code.
- Use actual project files as references only to justify the inferred pattern.
- Make the documentation generic enough for reuse in similar codebases.
- If the project lacks a mature pattern in some area, state that clearly instead of inventing one.
- Be explicit about naming conventions for classes, methods, interfaces, async operations, services, repositories, handlers, and feature modules whenever the repository provides enough evidence.
- Be explicit about layer visibility and consumption rules whenever the repository provides enough evidence.

Example rules:
- Use short generic pseudocode where useful.
- Avoid business-specific entity names.
- Prefer concise templates and implementation heuristics over long explanations.
- Replace real domain names with neutral terms.
- If needed, convert concrete code examples into minimal generic templates.

Confidence rules:
For each guide, indicate whether the conclusions are:
- high confidence
- medium confidence
- low confidence

Use confidence based on the amount and consistency of evidence found in the repository.

Final deliverable:
After generating the files, provide a concise summary containing:
1. the list of created Markdown files
2. the main patterns inferred from the codebase
3. the most important inconsistencies or gaps
4. which guides have lower confidence and why
5. the suggested reading order for an IDE/agent starting work in this repository

Behavior requirements:
- Do not ask for confirmation unless blocked by missing repository access.
- Be thorough in inspection before writing.
- Prefer evidence-backed guidance over generic best-practice advice.
- The final guides must function as internal MCP reference material for IDE-assisted development.

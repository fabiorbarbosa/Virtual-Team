Inspect the application in the current workspace and generate a complete operational Markdown knowledge base for an internal MCP used in daily IDE-assisted development.

Core mission:
Analyze the repository and convert the real engineering patterns found in the codebase into a reusable, generic, operational knowledge base in Markdown.

This is not simple project documentation.
This knowledge base must be structured so an IDE or coding agent can use it every day to:
- understand the project quickly
- decide where new code belongs
- choose the correct implementation pattern
- respect architecture and layer boundaries
- apply naming, async, OOP, and visibility conventions correctly
- distinguish hard rules from soft conventions
- handle legacy and inconsistency safely
- self-review generated code before completion

Primary outcome:
Generate a deterministic, ordered, indexable set of Markdown files that function as MCP reference material for:
- implementation
- refactoring
- code review
- architectural alignment
- conflict resolution
- long-term maintenance of engineering standards

High-level principles:
- Work from actual repository evidence, not assumptions.
- Extract dominant patterns from real code.
- Keep the output generic and reusable.
- Do not expose business-sensitive or domain-specific details.
- Replace domain-specific names with neutral placeholders such as `Entity`, `Feature`, `Item`, `Resource`, `Component`, `Service`, `Repository`, `Handler`, `Controller`.
- Convert concrete implementations into abstract templates, pseudocode, signatures, folder skeletons, and structural examples.
- Distinguish clearly between observed current behavior and recommended future standard.
- Prefer operational rules over descriptive commentary.
- If evidence is weak or inconsistent, say so explicitly and downgrade confidence.
- The final result must be usable as a daily MCP knowledge base, not just as static documentation.

Non-negotiable output requirements:
The knowledge base must explicitly distinguish:
- mandatory rules
- recommended conventions
- allowed exceptions
- observed legacy patterns
- unresolved decisions
- areas requiring human validation

The knowledge base must also explicitly distinguish:
- what each layer is responsible for
- what each layer must not do
- what each layer can access
- what each layer must not access
- what should be publicly exposed
- what should remain internal

Normative language requirement:
Use normative language when appropriate:
- MUST
- SHOULD
- MAY
- MUST NOT

This is required so an IDE or coding agent can distinguish hard constraints from soft guidance.

Deterministic indexing requirement:
Because these files will be indexed by an internal MCP server, the output must be deterministic and ordered for reliable retrieval.

Indexing rules:
- Preserve the exact filenames defined in this prompt whenever the corresponding topic is relevant.
- Use zero-padded numeric prefixes to enforce lexicographic ordering.
- Do not rename required files.
- Do not reorder numeric prefixes.
- If evidence is weak, still create the file and mark it as partial or low confidence instead of omitting it.
- The order of files must reflect intended reading and retrieval order for IDE/agent consumption.

Precedence model requirement:
The knowledge base must define document precedence so retrieval conflicts are resolvable.

At minimum, the output must make clear that:
- mandatory engineering rules override illustrative examples
- source-of-truth and conflict-resolution guidance override local ambiguity
- layer-boundary rules override convenience-based implementation shortcuts
- agent usage instructions guide retrieval order but do not override mandatory engineering rules
- legacy examples must not be treated as preferred standards unless explicitly marked as such

Repository inspection scope:
Inspect and infer patterns across the following areas when present:

1. Foundation
- main stack and frameworks
- language ecosystem
- runtime and build system
- project structure and module organization
- naming conventions
- environment/config organization

2. Architecture
- dominant architectural style
- layering model
- dependency direction
- module boundaries
- shared vs feature-local code
- orchestration patterns
- extension points and integration points

3. Engineering design conventions
- OOP usage and abstraction style
- class vs function usage
- interfaces, base classes, factories, adapters
- composition vs inheritance
- constructor dependency patterns
- async method rules and naming
- cancellation, timeout, retries, and error propagation patterns
- visibility/export/access rules across the codebase

4. UI and feature implementation
- components, screens, pages, features, modules
- separation between presentation, logic, orchestration, and data
- styling and design system conventions
- accessibility patterns
- routing/navigation conventions
- forms and validation patterns

5. Data and integration
- API/data access conventions
- repository/service/client/gateway patterns
- DTO/contract/mapping conventions
- persistence patterns
- serialization/deserialization rules
- dependency injection/composition root patterns
- events/messaging/background work if present

6. Reliability and operations
- error handling patterns
- logging/observability/telemetry
- security practices
- performance practices
- resilience patterns
- test strategy and test structure

7. Team-scale development behavior
- code review expectations implied by the repository
- consistency rules
- common anti-patterns
- areas with architectural drift
- recurring sources of technical debt

Mandatory additional analysis:
The generated guides must explicitly analyze and document the following engineering topics:

1. OOP conventions
Determine:
- whether the codebase relies on object-oriented design in services, use cases, controllers, domain models, view models, or related abstractions
- when classes are preferred over plain functions
- expected class responsibilities
- constructor injection patterns
- public API design expectations
- encapsulation rules
- composition vs inheritance rules
- how interfaces, abstract classes, factories, adapters, and base types are used
- which OOP anti-patterns are present or should be avoided

2. Async method conventions
Determine:
- whether all methods involving I/O, persistence, networking, background work, or deferred execution are asynchronous
- whether async naming suffixes are required, discouraged, or context-dependent
- return type conventions
- how async methods should propagate errors
- how cancellation, timeout, retries, and idempotency are handled if applicable
- how async behavior should be exposed across architectural layers
- how to avoid sync-over-async or blocking anti-patterns
- naming conventions for loaders, fetchers, handlers, commands, queries, creators, updaters, removers, and processors

3. Layer responsibilities and visibility
Determine:
- the purpose of each layer
- what each layer owns
- what each layer must never do
- which dependencies are allowed between layers
- which dependencies are forbidden
- which modules/symbols should be public, internal, protected, private, exported, or hidden depending on the language/framework
- which files are feature-local and which are truly shared
- how boundaries are enforced in practice
- common boundary violations and how to avoid them

4. Operational daily-development rules
Determine:
- what an IDE/agent should read before implementing code
- how to choose the correct pattern when multiple similar implementations exist
- when to follow local consistency vs recommended standard
- when to preserve a legacy pattern
- when to propose refactoring instead of reproducing an existing anti-pattern
- what the default implementation workflow should be for daily development

Conflict-resolution requirement:
If the codebase is inconsistent, do not flatten everything into a fake standard.
Instead, explicitly document:
- current observed behavior
- dominant pattern
- recommended future standard
- confidence level
- whether a human decision is still needed

Output location:
Create the knowledge base in one of these locations:
- `docs/mcp-guides/`
or
- `.mcp/guides/`

Required manifest and retrieval files:
Create these files first and use them to anchor the rest of the knowledge base:

`00-index.md`
Include:
- the full ordered list of generated guides
- the purpose of each guide
- the recommended reading order
- which guides are mandatory before code generation
- which guides are mandatory before modifying existing code
- which guides are mandatory before refactoring
- which guides are reference-only
- which guides have normative precedence when guidance conflicts

`00-overview.md`
Include:
- stack overview
- dominant architectural style
- key engineering principles inferred from the repo
- how to navigate the codebase
- major structural decisions
- overall confidence level

`00a-how-to-use-this-knowledge-base.md`
Include:
- how an IDE/agent should use the knowledge base during daily development
- reading order
- how to choose which guide to consult
- what to do before generating code
- what to do before editing existing code
- what to do before refactoring
- what to do before finalizing code
- how to self-check alignment with project standards

`00b-engineering-rules.md`
Include:
- mandatory rules
- recommended conventions
- prohibited patterns
- naming rules
- async rules
- OOP rules
- layering rules
- visibility rules
- rules that must never be violated

`00c-source-of-truth-and-conflict-resolution.md`
Include:
- what is the source of truth when guides and existing code differ
- how to handle legacy code
- when to preserve local consistency
- when to align with the recommended standard
- when to recommend refactoring
- when to escalate to human review
- conflict resolution examples

`00d-retrieval-and-precedence.md`
Include:
- document precedence model
- retrieval priority model
- which documents are normative
- which documents are operational
- which documents are reference-only
- which documents are advisory
- how an IDE/agent should resolve conflicting guidance

`00e-coverage-matrix.md`
Include:
- covered areas
- partially covered areas
- low-confidence areas
- unclear areas
- areas requiring human validation
- suggested future documentation gaps to fill

Core guide set:
Create at least the following files, adapted to actual stack and repository evidence.

`01-project-structure.md`
Include:
- directory layout
- responsibility of each major folder/layer
- where new files should go
- naming conventions for files, modules, components, types, classes, hooks, services, methods, and symbols
- feature-local vs shared structure rules

`02-architecture-patterns.md`
Include:
- dominant architecture pattern
- layers and responsibilities
- dependency flow rules
- allowed vs discouraged patterns
- architecture checklist for new work
- known architectural exceptions

`03-component-implementation-guide.md`
Include:
- how to implement a new component in this ecosystem
- expected structure
- separation of presentation, behavior, orchestration, and data concerns
- props/inputs/outputs/events conventions
- accessibility expectations
- styling expectations
- testing expectations
- generic component template

`04-feature-or-module-guide.md`
Include:
- how to add a new feature or module
- expected internal structure
- how it connects to routes, services, state, and UI
- modularity and scalability guidance
- generic feature/module template

`05-data-access-and-api-guide.md`
Include:
- how data fetching and persistence are organized
- patterns for client/service/repository/gateway layers
- DTO/contract/mapping rules
- error mapping
- serialization/deserialization or transformation rules
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
- anti-patterns to avoid

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
- test expectations by layer if inferable

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
- boundary compliance
- async/OOP/naming compliance

`12-agent-instructions.md`
Include:
- direct instructions for an IDE/coding agent using this codebase as reference
- which guides to consult first
- how to decide where code belongs
- which patterns to prioritize
- what to avoid
- how to self-check before finalizing generated code
- how to handle uncertainty or conflicting evidence

`13-oop-and-abstractions.md`
Include:
- when to use classes
- when to use interfaces
- composition vs inheritance
- constructor injection patterns
- public API vs internal implementation
- encapsulation expectations
- generic class template
- anti-patterns to avoid

`14-async-method-conventions.md`
Include:
- when methods must be async
- naming rules for async methods
- return type conventions
- error handling in async flows
- cancellation and timeout guidance if applicable
- retries and resilience guidance if applicable
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

`16-implementation-workflow.md`
Include:
- default workflow for daily development
- how to implement a small bug fix
- how to implement a new component
- how to implement a new feature/module
- how to change an existing integration
- how to approach refactors
- pre-delivery checklist

`17-task-playbooks.md`
Include:
- operational playbooks for common daily tasks
- bug fix playbook
- new component playbook
- new feature playbook
- integration change playbook
- refactor playbook
- code review playbook
- decision checkpoints for each playbook

`18-dependency-injection-and-composition.md`
Include:
- dependency registration patterns
- composition root conventions
- service lifetime/scope rules if applicable
- construction boundaries
- where object graphs should be assembled
- anti-patterns to avoid

`19-contracts-mapping-and-dto-guide.md`
Include:
- DTO and contract conventions
- request/response or command/query shapes
- mapping/transformation rules
- where mapping belongs
- anti-patterns to avoid
- generic templates

`20-legacy-and-migration-rules.md`
Include:
- how to work safely in legacy areas
- when to preserve legacy patterns
- when to migrate incrementally
- when to isolate new code from old patterns
- migration heuristics
- what requires human approval

`21-agent-self-review-checklist.md`
Include:
- final self-review checklist for an IDE/agent before considering a task complete
- structure
- naming
- async usage
- boundary compliance
- tests
- error handling
- logging
- security
- performance
- consistency with local code and documented standards

`98-decision-records.md`
Include:
- important inferred decisions
- recommended standards not yet fully enforced
- tradeoffs
- areas where a human architecture decision is still needed
- short ADR-style entries where useful

`99-open-questions-and-inconsistencies.md`
Include:
- unclear patterns
- competing implementations
- areas that require human confirmation
- technical debt or inconsistent structure worth flagging
- low-confidence conclusions
- unresolved architecture decisions

Optional guides:
If justified by the stack, also create:
- `22-routing-guide.md`
- `23-forms-guide.md`
- `24-authentication-guide.md`
- `25-domain-layer-guide.md`
- `26-background-jobs-guide.md`
- `27-events-and-messaging-guide.md`
- `28-mobile-patterns-guide.md`
- `29-accessibility-guide.md`
- `30-observability-guide.md`
- `31-configuration-and-environment-guide.md`
- `32-persistence-and-migrations-guide.md`

Required metadata at the top of every Markdown file:
Each file must begin with a compact metadata section containing:
- `title`
- `purpose`
- `scope`
- `applies_to`
- `doc_type`
- `audience`
- `task_types`
- `layer_scope`
- `language_scope`
- `framework_scope`
- `keywords`
- `priority`
- `retrieval_priority`
- `status`
- `confidence`
- `evidence_type`
- `source_of_truth`
- `order`
- `canonical_id`
- `depends_on`
- `must_read_before`
- `last_review_basis`

Recommended metadata value conventions:
- `doc_type`: `normative` | `operational` | `reference` | `advisory`
- `audience`: `agent` | `human` | `both`
- `priority`: `critical` | `high` | `medium` | `low`
- `retrieval_priority`: `critical` | `high` | `medium` | `low`
- `status`: `draft` | `proposed` | `approved` | `legacy`
- `confidence`: `high` | `medium` | `low`
- `evidence_type`: `observed` | `inferred` | `recommended`
- `source_of_truth`: `repository evidence` | `recommended standard` | `mixed`

Required internal structure for each Markdown file:
When applicable, each guide should include:
- Title
- Objective
- Why this matters for daily development
- When to use
- Mandatory rules
- Recommended conventions
- Allowed exceptions
- Legacy considerations
- Recommended pattern
- Step-by-step
- Suggested structure
- Generic example
- Common mistakes
- Checklist
- Internal project references
- Confidence notes
- Open questions, if any

Task usability requirement:
For high-frequency development tasks, provide:
- short actionable templates
- naming examples
- folder/file skeletons
- signature examples
- implementation heuristics
- validation checklists

Evidence model requirement:
Each guide must identify whether its guidance is:
- observed in code
- inferred from dominant patterns
- recommended as future standard

Each guide must briefly list the repository evidence used to support the guidance.

Coverage model requirement:
The knowledge base must explicitly identify:
- fully covered areas
- partially covered areas
- weak-evidence areas
- no-evidence areas
- areas requiring human validation

Maintenance model requirement:
Document how the knowledge base should evolve when:
- the codebase changes
- a new dominant pattern emerges
- a legacy pattern is deprecated
- a guide becomes outdated
- a previously recommended standard becomes enforced

Do not treat recommendations as already enforced unless repository evidence supports that claim.

Execution procedure:
1. Inspect the repository structure and detect the stack.
2. Identify the most representative files, modules, and implementation flows.
3. Read enough code to distinguish dominant patterns from exceptions.
4. Infer rules only where there is evidence.
5. Separate observed reality from recommended standard where needed.
6. Create the retrieval and manifest files first.
7. Generate the rest of the Markdown knowledge base in the selected output folder.
8. Ensure the guides are operational for daily MCP usage.
9. Ensure deterministic naming and ordering.
10. Summarize the result at the end.

Final deliverable:
After generating the files, provide a concise summary containing:
1. the list of created Markdown files in retrieval order
2. the main patterns inferred from the codebase
3. the mandatory rules extracted
4. the precedence model
5. the most important inconsistencies or gaps
6. which guides have lower confidence and why
7. the suggested reading order for an IDE/agent starting work in this repository
8. any areas that should be validated by a human before the MCP is treated as authoritative

Behavior requirements:
- Do not ask for confirmation unless blocked by missing repository access.
- Be thorough in inspection before writing.
- Prefer repository-backed guidance over generic best-practice advice.
- Do not fabricate certainty.
- Do not omit required files just because evidence is weak; create them and mark them appropriately.
- The final guides must function as internal MCP reference material for daily development.

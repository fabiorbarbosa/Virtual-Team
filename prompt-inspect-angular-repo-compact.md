Inspect the Angular/TypeScript application in the current workspace and generate an operational Markdown knowledge base for an internal MCP used in daily IDE-assisted development.

Goal:
Analyze the repository and transform actual Angular/TypeScript engineering patterns into a generic, reusable Markdown knowledge base that guides IDEs and coding agents during daily implementation, refactoring, review, and architecture-aligned development.

Core principles:
- Work from repository evidence only.
- Keep the documentation generic and reusable.
- Do not expose business-specific details.
- Replace domain-specific names with neutral placeholders such as `Feature`, `Component`, `Container`, `Service`, `Facade`, `Store`, `Repository`, `Model`, `Dto`.
- Distinguish:
  - mandatory rules
  - recommended conventions
  - allowed exceptions
  - legacy patterns
  - unresolved decisions
- Use normative language:
  - MUST
  - SHOULD
  - MAY
  - MUST NOT

Mandatory Angular/TypeScript analysis:
Inspect and document the following explicitly:

1. Project structure
- workspace structure
- app vs shared vs core vs feature organization
- standalone components vs NgModules
- library boundaries if monorepo exists
- where new components/services/models/routes should go
- naming conventions for files, classes, selectors, inputs, outputs, stores, facades, and utilities

2. Architecture and layering
- feature-based vs layered structure
- smart/container vs dumb/presentational components
- service/facade/store responsibilities
- domain/application/infrastructure separation if present
- shared vs feature-local code
- forbidden cross-feature dependencies
- orchestration ownership

3. Angular component conventions
- standalone component usage
- template/style file organization
- component responsibility limits
- input/output conventions
- change detection strategy
- signals, RxJS, or both
- accessibility expectations
- styling and composition rules
- component anti-patterns

4. TypeScript and OOP conventions
- when to use classes vs functions
- interface/type alias usage
- service abstraction patterns
- inheritance vs composition
- public/private/protected usage
- readonly conventions
- anti-patterns such as over-inheritance, utility dumping, stateful singleton misuse

5. Async conventions in Angular/TypeScript
Document explicitly:
- whether async I/O methods MUST return `Observable`, `Promise`, or both depending on layer
- naming conventions for async methods
- whether `Async` suffix is used or avoided
- when to use `Observable` vs `Promise`
- subscription ownership rules
- cancellation/unsubscription patterns
- `takeUntil`, `async` pipe, signals interop, effects, resource cleanup
- error propagation and retry patterns
- sync-over-async anti-patterns to avoid

6. State management
- local component state
- shared state
- RxJS service state
- NgRx / signals / signal stores / facades if present
- selectors/effects/actions patterns if present
- caching and invalidation
- when state belongs in component vs service vs store

7. Data access and HTTP
- HttpClient usage
- API service/facade/repository layering
- DTO/mapping conventions
- interceptors
- error handling
- auth token handling
- query parameter and request model patterns

8. Forms and validation
- reactive forms vs template-driven forms
- typed forms conventions
- validator organization
- error display patterns
- submit flow patterns
- form state management

9. Routing
- route organization
- lazy loading
- guards
- resolvers
- feature routing boundaries
- navigation conventions

10. Testing
- unit/component/integration patterns
- TestBed usage
- mocking strategy
- harnesses if present
- async testing conventions
- service/component/store test boundaries

11. Operational concerns
- logging and observability
- security practices
- performance practices
- bundle and rendering concerns
- accessibility
- anti-patterns to avoid

Output location:
Create the knowledge base in:
- `docs/mcp-guides/`
or
- `.mcp/guides/`

Required files:
- `00-index.md`
- `00-overview.md`
- `00a-how-to-use-this-knowledge-base.md`
- `00b-engineering-rules.md`
- `00c-source-of-truth-and-conflict-resolution.md`
- `00d-retrieval-and-precedence.md`
- `01-project-structure.md`
- `02-architecture-patterns.md`
- `03-component-implementation-guide.md`
- `04-feature-or-module-guide.md`
- `05-data-access-and-api-guide.md`
- `06-state-management-guide.md`
- `07-validation-and-error-handling.md`
- `08-styling-and-design-system.md`
- `09-testing-guide.md`
- `10-security-and-performance.md`
- `11-code-review-checklist.md`
- `12-agent-instructions.md`
- `13-oop-and-abstractions.md`
- `14-async-method-conventions.md`
- `15-layer-responsibilities-and-boundaries.md`
- `16-implementation-workflow.md`
- `17-task-playbooks.md`
- `19-contracts-mapping-and-dto-guide.md`
- `20-legacy-and-migration-rules.md`
- `21-agent-self-review-checklist.md`
- `99-open-questions-and-inconsistencies.md`

Optional Angular-specific files if evidence exists:
- `22-routing-guide.md`
- `23-forms-guide.md`
- `24-rxjs-and-signals-guide.md`
- `25-state-management-patterns-guide.md`
- `26-authentication-and-authorization-guide.md`
- `27-http-interceptors-and-api-errors-guide.md`
- `28-accessibility-guide.md`
- `29-performance-and-rendering-guide.md`

Required metadata in every file:
- `title`
- `doc_type`
- `audience`
- `task_types`
- `layer_scope`
- `language_scope`
- `framework_scope`
- `priority`
- `retrieval_priority`
- `status`
- `confidence`
- `evidence_type`
- `order`
- `canonical_id`
- `depends_on`
- `source_of_truth`

Special Angular/TypeScript requirements:
- Be explicit about standalone components vs NgModules.
- Be explicit about when to use `Observable`, `Promise`, signals, facades, and stores.
- Be explicit about component boundaries and when logic belongs in component, service, facade, or store.
- Be explicit about subscription ownership and cleanup rules.
- Be explicit about typed forms and validation conventions if present.
- Be explicit about shared vs feature-local code.
- If the repository is inconsistent, distinguish current state from recommended standard.

Final summary:
Provide:
1. created files in retrieval order
2. dominant Angular/TypeScript patterns found
3. mandatory engineering rules
4. async/state/component conventions
5. layer boundary rules
6. major inconsistencies
7. low-confidence guides
8. reading order for IDE/agent consumption

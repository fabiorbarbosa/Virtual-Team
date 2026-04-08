Inspect the .NET/C# application in the current workspace and generate an operational Markdown knowledge base for an internal MCP used in daily IDE-assisted development.

Goal:
Analyze the repository and transform actual .NET/C# engineering patterns into a generic, reusable Markdown knowledge base that guides IDEs and coding agents during implementation, refactoring, review, and architecture-aligned development.

Core principles:
- Work from repository evidence only.
- Keep the documentation generic and reusable.
- Do not expose business-specific details.
- Replace domain-specific names with neutral placeholders such as `Entity`, `Feature`, `ApplicationService`, `Repository`, `Command`, `Query`, `Handler`.
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

Mandatory .NET/C# analysis:
Inspect and document the following explicitly:

1. Solution and project structure
- `.sln` organization
- project boundaries
- class library responsibilities
- Web/API/Application/Domain/Infrastructure/Test project separation
- shared kernel or common project usage
- where new projects/files should be added

2. Architecture and layering
- Clean Architecture, layered architecture, modular monolith, vertical slices, or hybrid structure
- allowed references between projects
- forbidden project dependencies
- application vs domain vs infrastructure responsibilities
- orchestration ownership
- feature-local vs shared code

3. OOP conventions
- where classes are preferred
- interface usage conventions
- abstract classes vs composition
- service design rules
- constructor injection patterns
- encapsulation and visibility
- entity/value object/domain service/application service distinctions
- anti-patterns such as god services, anemic abstractions, utility dumping

4. Async conventions in C#
Document explicitly:
- whether I/O methods MUST be async
- whether async suffixes MUST be used for async methods
- naming conventions for:
  - `GetAsync`
  - `ListAsync`
  - `CreateAsync`
  - `UpdateAsync`
  - `DeleteAsync`
  - `HandleAsync`
  - query/command handlers
- `Task` vs `Task<T>` vs `ValueTask`
- cancellation token conventions
- timeout and retry patterns
- how exceptions are propagated in async flows
- sync-over-async anti-patterns to avoid
- whether controller/service/repository methods are async end-to-end

5. Dependency Injection and composition
- service registration patterns
- composition root location
- service lifetimes
- options/configuration binding
- factory patterns
- boundaries for manual object construction

6. ASP.NET Core or API conventions if present
- controllers vs minimal APIs
- route organization
- request/response DTO patterns
- model binding and validation
- filters/middleware/pipeline behaviors
- authentication and authorization patterns
- exception handling middleware
- API versioning if present

7. Data access conventions
- EF Core / Dapper / ADO.NET / repositories / unit of work patterns
- DbContext usage
- query separation
- mapping conventions
- transaction boundaries
- migrations
- persistence responsibilities
- anti-patterns to avoid

8. Testing
- unit/integration/architecture tests
- test naming conventions
- fixture setup
- fake/mock strategy
- WebApplicationFactory patterns if present
- how tests map to layers

9. Operational concerns
- logging and telemetry
- security practices
- performance practices
- resilience patterns
- background jobs/hosted services if present

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
- `05-data-access-and-api-guide.md`
- `07-validation-and-error-handling.md`
- `09-testing-guide.md`
- `10-security-and-performance.md`
- `11-code-review-checklist.md`
- `12-agent-instructions.md`
- `13-oop-and-abstractions.md`
- `14-async-method-conventions.md`
- `15-layer-responsibilities-and-boundaries.md`
- `16-implementation-workflow.md`
- `17-task-playbooks.md`
- `18-dependency-injection-and-composition.md`
- `19-contracts-mapping-and-dto-guide.md`
- `20-legacy-and-migration-rules.md`
- `21-agent-self-review-checklist.md`
- `98-decision-records.md`
- `99-open-questions-and-inconsistencies.md`

Optional .NET-specific files if evidence exists:
- `22-routing-and-endpoints-guide.md`
- `23-aspnetcore-pipeline-guide.md`
- `24-efcore-and-migrations-guide.md`
- `25-background-jobs-and-hosted-services.md`
- `26-authentication-and-authorization-guide.md`
- `27-configuration-and-options-guide.md`

Required metadata in every file:
- `title`
- `doc_type`
- `audience`
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

Special .NET/C# requirements:
- Be explicit about `public`, `internal`, `private`, `protected` usage.
- Be explicit about project references and forbidden dependencies.
- Be explicit about `async` suffix rules.
- Be explicit about DI registration and service lifetime rules.
- Be explicit about where DTOs, commands, queries, validators, handlers, controllers, repositories, and domain entities belong.
- If the codebase is inconsistent, distinguish current state from recommended standard.

Final summary:
Provide:
1. created files in retrieval order
2. dominant .NET/C# patterns found
3. mandatory engineering rules
4. async and OOP conventions
5. layer boundary rules
6. major inconsistencies
7. low-confidence guides
8. reading order for IDE/agent consumption

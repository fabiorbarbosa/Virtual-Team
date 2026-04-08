Inspect the application in the current workspace and generate an operational Markdown knowledge base for an internal MCP used in daily IDE-assisted development.

Goal:
Turn the real patterns found in the repository into a generic, reusable, deterministic set of Markdown guides that help an IDE or coding agent implement, refactor, review, and maintain code consistently.

Core rules:
- Work from repository evidence, not assumptions.
- Keep the guides generic and reusable.
- Do not expose business-specific details.
- Replace domain names with neutral terms such as `Entity`, `Feature`, `Component`, `Service`, `Repository`.
- Distinguish clearly between:
  - mandatory rules
  - recommended conventions
  - allowed exceptions
  - legacy patterns
  - unresolved decisions
- Use normative language where appropriate:
  - MUST
  - SHOULD
  - MAY
  - MUST NOT
- If evidence is weak, still create the guide and mark it as low confidence or partial.

Inspect:
- stack and framework
- project structure
- architecture and layer boundaries
- naming conventions
- OOP patterns
- async method conventions
- visibility and dependency rules
- components/modules/features
- state management
- data access and API integration
- validation and error handling
- testing
- styling/design system
- security and performance
- code review expectations
- inconsistencies and technical debt

Output requirements:
Create the knowledge base in:
- `docs/mcp-guides/`
or
- `.mcp/guides/`

Use deterministic, ordered filenames with zero-padded prefixes.

Create at minimum:
- `00-index.md`
- `00-overview.md`
- `00a-how-to-use-this-knowledge-base.md`
- `00b-engineering-rules.md`
- `00c-source-of-truth-and-conflict-resolution.md`
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
- `21-agent-self-review-checklist.md`
- `99-open-questions-and-inconsistencies.md`

Required metadata at the top of every file:
- `title`
- `doc_type`
- `priority`
- `retrieval_priority`
- `status`
- `confidence`
- `evidence_type`
- `order`
- `canonical_id`
- `depends_on`
- `source_of_truth`

Each guide should include when applicable:
- Objective
- When to use
- Mandatory rules
- Recommended conventions
- Allowed exceptions
- Recommended pattern
- Step-by-step
- Generic example
- Common mistakes
- Checklist
- Internal project references
- Confidence notes

Special requirements:
- Explicitly document OOP conventions.
- Explicitly document async method naming and behavior.
- Explicitly document layer responsibilities, forbidden dependencies, and visibility boundaries.
- Explicitly define document precedence for MCP retrieval.
- Create `00-index.md` as the manifest for ordered retrieval and reading.

Final summary:
After generating the files, provide:
1. created files in retrieval order
2. main patterns found
3. mandatory rules extracted
4. major inconsistencies
5. low-confidence guides
6. suggested reading order for an IDE/agent

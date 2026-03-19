# Agents Skills Package

This package translates the uploaded agents catalog into reusable Cursor skills.

## Included skills
- `orchestrator.md`
- `governance/tech-lead.md`
- `governance/principal-engineer.md`
- `governance/qa-architect.md`
- `reviewers/critical-reviewer.md`
- `reviewers/complexity-guard.md`
- `reviewers/failure-mode.md`
- `specialists/backend.md`
- `specialists/database.md`
- `specialists/design.md`
- `specialists/devops.md`
- `specialists/frontend.md`
- `specialists/mobile.md`
- `specialists/security.md`
- `specialists/uxui.md`

## Suggested use
1. Extract this zip at the root of your repository.
2. In Cursor, call the orchestrator first for non-trivial tasks.
3. Load specialist skills according to the repository type and task.
4. Use reviewer skills to challenge proposals before implementation.

## Example prompts
- `Use the orchestrator skill to plan this change`
- `Load specialists/frontend and specialists/backend for this feature`
- `Run reviewers/critical-reviewer and reviewers/failure-mode against the proposal`

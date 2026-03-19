# Orchestrator Skill

## Mission
Act as the central coordinator for non-trivial engineering tasks, using governance, reviewers, and specialists in a deliberate sequence before implementation.

## Mandatory flow
1. Read repository context first:
   - `README.md`
   - `docs/**`
   - service-level READMEs
   - manifests and config files (`package.json`, `.csproj`, `Dockerfile`, CI files)
2. Detect repository type:
   - backend/API
   - frontend/web
   - mobile
   - worker/jobs
   - data pipeline
   - infra/devops
   - monorepo
3. Load governance roles:
   - `governance/tech-lead`
   - `governance/principal-engineer`
   - `governance/qa-architect`
4. Load reviewers:
   - `reviewers/critical-reviewer`
   - `reviewers/complexity-guard`
   - `reviewers/failure-mode`
5. Load specialists based on task/repository evidence.
6. Consolidate one coherent plan before implementation.
7. Implement incrementally.
8. Harden with tests, logging, idempotency, and rollback awareness.
9. Provide verification steps and risks.

## Specialist routing
- Backend / API / jobs / messaging → `specialists/backend`
- Angular / React / web UI / TS / JS → `specialists/frontend`, `specialists/uxui`, `specialists/design`
- Flutter / Swift / Kotlin → `specialists/mobile`
- Oracle / Postgres / SQL / NoSQL / Redis → `specialists/database`
- Docker / CI / CD / infra → `specialists/devops`
- Auth / permissions / secrets / PII → `specialists/security`

## Output format
- Repository context summary
- Summary
- Proposal
- Loaded roles
- Challenge findings
- Decision
- Implementation steps
- Verification
- Risks & mitigations

## Guardrails
- Determinism over cleverness
- Auditability is mandatory
- Do not guess behavior without evidence
- Prefer repository evidence over assumptions

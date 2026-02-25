
# DevOps Specialist

## Mission
Ensure the platform operates with reliability, delivery safety, and rapid recovery capability, with focus on software services that require auditability and high predictability.

## When this specialist should be engaged
- Creating or improving CI/CD pipelines.
- Containerizing applications and standardizing environments.
- Defining observability, SLO/SLA targets, and alerting.
- Planning progressive deployment, rollback, and continuity.

## Required minimum inputs
- Service topology and critical dependencies.
- Availability, RTO, and RPO requirements.
- Target environments (`dev`/`staging`/`prod`) and promotion strategy.
- Security, compliance, and access-segregation constraints.

## Core responsibilities
- Standardize build/runtime with secure, minimal images.
- Build pipelines with quality gates (tests, lint, security).
- Define deployment strategy (rolling, blue-green, canary) based on risk.
- Ensure both business and infrastructure observability with correlation.
- Plan rollback, recovery, and incident response operations.

## Mandatory technical checklist
- Containers:
  - Lean `Dockerfile`, pinned dependencies, non-root user when feasible.
  - Multi-stage builds to reduce size and attack surface.
  - Vulnerability scanning in build pipeline.
- CI/CD:
  - Deterministic stages with controlled cache and versioned artifacts.
  - Mandatory gates for testing and security policies.
  - Environment promotion with release traceability.
- Operations:
  - Proper `liveness`/`readiness`/`startup` health checks.
  - Error, latency, saturation, and throughput metrics.
  - Actionable, low-noise alerting.
- Continuity:
  - Incident runbooks and rollback procedures.
  - Backup/restore with periodic validation.
  - Feature-flag strategy to reduce release risk.

## Expected deliverables
- CI/CD pipeline blueprint with gates and promotion criteria.
- Container/runtime standards for project services.
- Observability plan (logs, metrics, traces, dashboards, alerts).
- Documented rollback and operational continuity strategy.

## Approval quality criteria
- Deployments are reproducible and auditable end to end.
- Production failures are quickly detectable and attributable.
- Rollback is low-friction with controlled impact.
- Operational setup minimizes silent-regression risk.

## Forbidden anti-patterns
- Pipeline without minimum quality/security gates.
- Secrets hardcoded in variables, images, or logs.
- Infra-only monitoring without business signals.
- All-at-once deploys for high-risk changes without mitigation.

## Collaboration with other roles
- Backend/Frontend/Mobile: align build artifacts and runtime variables.
- Security Specialist: pipeline hardening, secrets, and access controls.
- QA Architect: test automation and promotion criteria.

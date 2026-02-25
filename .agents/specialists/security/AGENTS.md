
# Security Specialist

## Mission
Protect critical assets, sensitive data, and product attack surfaces by ensuring architecture and implementation follow secure-by-default, traceability, and compliance principles.

## When this specialist should be engaged
- Introducing authentication, authorization, or session management.
- Changing sensitive data handling, PII, credentials, or secrets.
- Exposing new endpoints, external integrations, or webhooks.
- Reviewing risk in high high-impact features.

## Required minimum inputs
- Data flows and sensitivity classification per field.
- Trust boundaries between services, users, and third parties.
- Regulatory requirements and internal security policies.
- Dependency and technology inventory.

## Core responsibilities
- Perform threat modeling (STRIDE) per critical flow.
- Define AuthN/AuthZ strategy using least privilege.
- Establish in-transit and at-rest data protection standards.
- Review secrets lifecycle, rotation, and environment isolation.
- Ensure logs/audit trails without sensitive data leakage.

## Mandatory technical checklist
- Threat modeling:
  - Main vectors by asset and attack surface.
  - Likelihood, impact, and mitigation prioritization.
  - Preventive, detective, and corrective controls.
- Identity and access:
  - Secure token/session expiration and renewal.
  - RBAC/ABAC with explicit scopes and periodic review.
  - Controls against privilege escalation and indirect access.
- Data protection:
  - Encryption in transit (TLS) and at rest when required.
  - PII masking/redaction in logs and telemetry.
  - Data retention and secure disposal policy.
- Supply chain:
  - Dependency/image scanning with blocking on critical CVEs.
  - Version pinning and package-source validation.
  - Secure defaults hardening (headers, CORS, CSP, etc.).

## Expected deliverables
- Concise threat model with prioritized risks and mitigations.
- AuthN/AuthZ strategy and domain-level access controls.
- Secrets, encryption, and data-protection guidance.
- Secure audit/logging recommendations for investigations.

## Approval quality criteria
- Critical risks have verifiable technical mitigations.
- Resource access follows least privilege by default.
- No secrets/PII exposure in code, logs, or error outputs.
- Security controls are testable and monitorable in production.

## Forbidden anti-patterns
- Secrets hardcoded in code, pipeline, or versioned config.
- Implicit authorization relying only on client-side checks.
- Logging tokens, documents, sensitive business data, or raw PII.
- Accepting dependencies without risk and maintenance validation.

## Collaboration with other roles
- Backend/Frontend/Mobile: session control, authorization, and sanitization.
- DevOps Specialist: secrets, IAM, runtime hardening, and CI/CD security.
- Compliance Officer: regulatory adherence and control evidence.
- QA Architect: security tests and abuse-case scenarios.

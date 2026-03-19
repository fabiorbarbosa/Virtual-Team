# Failure Mode Analyst Skill

## Mission
Stress-test failure behavior so the system fails safely, recovers predictably, and preserves integrity.

## Use when
- External dependencies exist.
- Async flows, retries, transactions, or concurrency are involved.
- Ordering, idempotency, or finalization matters.

## Required inputs
- End-to-end flow
- Error handling strategy
- Retry and timeout proposal
- Consistency guarantees
- Observability and incident plan

## Checklist
- What if dependencies are slow/down/inconsistent?
- Are timeout and retry policies bounded?
- Can duplicate processing occur?
- Are idempotency and dedup strategies defined?
- Is blast radius contained during partial outage?
- Can stuck operations be detected and recovered?

## Deliverables
- Failure scenario matrix
- Mitigation recommendations
- Recovery expectations
- Observability requirements for incident response

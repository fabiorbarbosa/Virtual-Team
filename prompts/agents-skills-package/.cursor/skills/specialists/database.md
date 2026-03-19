# Database Specialist Skill

## Mission
Protect data integrity, evolution safety, and query performance.

## Use when
- Schema, migrations, indexing, or persistence models change.
- Concurrency, consistency, or performance-sensitive queries matter.

## Required inputs
- Domain model
- Access patterns
- Load expectations
- Migration constraints
- Backup/restore requirements

## Checklist
- Are invariants enforced by schema where appropriate?
- Are types correct for precision-sensitive values?
- Is migration backward compatible in phases?
- Are indexes justified by real query patterns?
- Is rollback feasible?
- Are integrity and performance validations defined?

## Deliverables
- Logical/physical model notes
- Migration plan
- Index strategy
- Post-migration validation plan

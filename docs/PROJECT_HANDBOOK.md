# IntelliHRMS — Lean V1 Variant — Complete Project Guide

**Repository:** `vaishnavsawant1994-stack/IntelliHRMS` · **Review:** 15 November 2026  
**Evidence level:** current README, repository layout and manifest where available; no fresh deployed-end-to-end certification.

## Product identity and problem
Related human-resource application implementing employees, departments, attendance, leave, payroll and role-scoped dashboards.

**Primary users:** HRMS developers and product evaluators.

## Functional areas and intended user journeys
1. Frontend and backend HRMS modules.
2. JWT authentication and a PostgreSQL/Prisma data layer.
3. Build, lint and frontend/backend test scripts.
4. Role-focused HR user experiences.

Features above describe documented capability areas, source/UI surfaces or product intents. A listed module is not necessarily a functioning integrated feature.

## System design and codebase
Root `frontend/`, `backend/`, `docs/`, `package.json`. React/Express workspace with Prisma/PostgreSQL and tests. Smaller repository shape than `HRMS-NEW`.

## Implementation status
Related implementation, not confirmed as canonical. The mere existence of payroll and role views does not prove policy correctness or production readiness.

**Do not conflate:** planned scope, code existence, passing old CI, live production deployment and independent release acceptance. They require separate evidence.

## Development and testing
`npm install`, then use `npm run dev:backend`, `npm run dev:frontend`, `npm run build`, `npm run lint`, `npm test` with isolated DB access.

Before using any environment: examine .env examples and source code, use test accounts, protect secrets, and inspect the target database prior to migrations/seed commands.

## Data security, privacy and operations
- Prevent cross-employee access to payslips/leave details.
- Verify approval and payroll calculations with test fixtures.
- Require migration consistency and backup policies.
Additionally validate backup/restore, audit logs, staging isolation, access reviews, monitoring and release rollback before production use.

## Priority development plan
1. Diff this repository against `HRMS-NEW`.
2. Document unique functionality and regressions.
3. Decide owner-maintained variant/archival.
4. Run audited integration tests before consolidation.

## Where to read more
- [`README.md`](../README.md)
- [`package.json`](../package.json)
- [`backend/`](../backend/)
- [`frontend/`](../frontend/)
- [`docs/`](../docs/)

This guide should be revised after verified code, architecture, data schema, deployment or product-scope changes. The underlying source and gated engineering documents remain authoritative.

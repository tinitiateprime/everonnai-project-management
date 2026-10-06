# 21. Customer repositories and client project delivery documentation

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `PJM`. Proposed accountable roles: Product Owner + Backend/Frontend Leads; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-PJM-101](tickets/EVN-PJM-101.md) | Share a customer's own GitHub project documentation safely | Implemented | Extension |
| [EVN-PJM-102](tickets/EVN-PJM-102.md) | Give the client a traceable project/module/ticket delivery checklist | Implemented | Extension |

## Current project capability

**EVN-PJM-101:** Tenant-scoped public/private GitHub connections, read-only Markdown/Mermaid/images, search/sync, role checks and encrypted tokens are implemented.

**EVN-PJM-102:** This Markdown pack provides the project/module/ticket hierarchy, requirement mapping, current-state evidence and acceptance checklists.

Current persistence: everonn.project_repositories; additive migration applied to configured PostgreSQL on 2026-10-06. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 0 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: None; scope and architecture review is the entry point.

## Existing code and verification

- `app/workspace/page.tsx` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `app/api/project-workspace/route.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/project-workspace/github.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/project-workspace/repositories.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `lib/project-repository-store.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `components/project-workspace/project-workspace.tsx` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/project-workspace.test.ts`, `scripts/smoke-project-workspace.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

Customer GitHub Markdown is read-only documentation; it does not execute platform skills. Hosted UI deployment and real private-repository access still require verification.

## Module completion gate

- [ ] Ticket scope, priority and accountable people agreed.
- [ ] Business outcomes demonstrated with authorised tenant data.
- [ ] Applicable source requirements and acceptance scenarios passed with evidence.
- [ ] Database, contracts, role boundaries and failure handling reviewed.
- [ ] AI quality/safety and provider cost validated where applicable.
- [ ] UI accessibility and responsive behaviour reviewed.
- [ ] Hosted rollout, monitoring, recovery and operational ownership verified.
- [ ] Client signs the released version; deferred items have explicit written disposition.

An implemented slice or a passing unit suite does not close this module. See [current status](../../CURRENT_STATE.md) and [the phase plan](../../DELIVERY_PLAN.md).

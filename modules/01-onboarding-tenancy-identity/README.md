# 01. Onboarding, identity and tenant lifecycle

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `ONB`. Proposed accountable roles: Backend Lead + Frontend Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-ONB-015](tickets/EVN-ONB-015.md) | Verify ownership before anything is public | Partial | P1 |
| [EVN-ONB-022](tickets/EVN-ONB-022.md) | Test before going live | Partial | P1 |
| [EVN-ONB-101](tickets/EVN-ONB-101.md) | Deliver account access that satisfies production identity requirements | Partial | P1 |
| [EVN-ONB-102](tickets/EVN-ONB-102.md) | Preserve tenant data while preparing brands, locations and cells | Partial | P0 schema decision / P1 completion |

## Current project capability

**EVN-ONB-015:** Server publishing transitions and role/tenant guards exist.

**EVN-ONB-022:** Dashboard text and browser voice tests exist.

**EVN-ONB-101:** Owner/customer signup, invitations, scrypt sessions, password change and lockouts work.

**EVN-ONB-102:** Scoped relational stores and optimistic revisions are implemented.

Current persistence: workspaces, business_profiles, users, auth_sessions, invitations, team_members, record_revisions. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 39 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-FND-101](../00-foundations-governance/tickets/EVN-FND-101.md).

## Existing code and verification

- `features/auth/rbac.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/auth/session.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/auth/password.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `lib/auth-store.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `lib/json-workspace-store.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/everonn/starter-workspace.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `app/api/auth/register/route.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/auth.test.ts`, `tests/workspace-security.test.ts`, `tests/app-records.test.ts`, `tests/everonn-relational.test.ts`, `scripts/smoke-auth-database.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

A boolean verified state does not establish independent business ownership; MFA/recovery and operator/brand identities remain incomplete.

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

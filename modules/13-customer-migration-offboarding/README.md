# 13. Authorised migration, service continuity and offboarding

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `MIG`. Proposed accountable roles: Migration Specialist + Operations Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-MIG-056](tickets/EVN-MIG-056.md) | Managed migration without service loss | Planned | P1 basic, P2 advanced |
| [EVN-MIG-057](tickets/EVN-MIG-057.md) | Respect the customer's contract and ownership | Planned | P1 |

## Current project capability

**EVN-MIG-056:** Website rollback is not a business migration toolkit.

**EVN-MIG-057:** No contract/asset-rights workflow exists.

Current persistence: Website snapshot rollback only; no whole-business migration inventory/rights/cutover model. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 22 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-FND-101](../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-OPS-103](../18-reliability-deployment-scale/tickets/EVN-OPS-103.md).

## Existing code and verification

- `features/website-studio/releases.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/website-code.test.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

Website rollback does not preserve registrar/mail/phone contracts or provide authorised import, parallel run, hypercare and business offboarding.

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

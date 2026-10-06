# 00. Foundations, scope and architecture decisions

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `FND`. Proposed accountable roles: Product Owner + Technical Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-FND-101](tickets/EVN-FND-101.md) | Approve the delivery scope and architecture baseline | Decision required | P0 |

## Current project capability

**EVN-FND-101:** Current Next.js/Supabase/Amplify is documented and functioning locally.

Current persistence: Private everonn schema, guarded migrations and shape-preserving stores. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 132 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: None; scope and architecture review is the entry point.

## Existing code and verification

- `CODE_PROFILE.md` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `PROJECT_DATA_FLOW.md` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `CLIENT_TECHNICAL_QA.md` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `README.md` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).

## Main delivery risk

Unapproved divergence from the RHEL/Podman/MariaDB baseline and undefined acceptance ownership.

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

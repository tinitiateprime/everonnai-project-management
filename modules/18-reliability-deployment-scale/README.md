# 18. Infrastructure, durable workflows, reliability and scale

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `OPS`. Proposed accountable roles: SRE/Platform Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-OPS-068](tickets/EVN-OPS-068.md) | Reliability during outages | Partial | P1 |
| [EVN-OPS-069](tickets/EVN-OPS-069.md) | Zero-downtime releases | Partial | P1 |
| [EVN-OPS-072](tickets/EVN-OPS-072.md) | Scale by adding capacity | Planned | P2 |
| [EVN-OPS-101](tickets/EVN-OPS-101.md) | Keep business events and delayed work reliable across retries | Partial | P0 foundation / P1 completion |
| [EVN-OPS-102](tickets/EVN-OPS-102.md) | Deploy repeatably with a reviewed rollback and secure supply chain | Partial | P0 |
| [EVN-OPS-103](tickets/EVN-OPS-103.md) | Recover customer service within agreed outage and restore targets | Planned | P1 |
| [EVN-OPS-104](tickets/EVN-OPS-104.md) | Measure latency, capacity and cost before promising scale | Partial | P1 |

## Current project capability

**EVN-OPS-068:** Model fallback, failed-booking safety, worker recovery and metering reconciliation exist.

**EVN-OPS-069:** Amplify build and server environment configuration exist.

**EVN-OPS-072:** Batching bounds one request; target scale has not been proven.

**EVN-OPS-101:** A specialised durable usage outbox and worker exist.

**EVN-OPS-102:** Amplify build/environment adapters and production build scripts exist.

**EVN-OPS-103:** No full restore/PITR/media-failover drill has been demonstrated.

**EVN-OPS-104:** Usage worker heartbeat and some provider/job status exist.

Current persistence: Guarded migrations and usage-worker infrastructure; no general domain bus/cells/media drain. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 44 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-AIQ-103](../03-ai-governance-evaluation/tickets/EVN-AIQ-103.md), [EVN-FND-101](../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-VOX-101](../04-telephone-voice-language/tickets/EVN-VOX-101.md).

## Existing code and verification

- `amplify.yml` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `scripts/write-amplify-env.mjs` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `scripts/migrate-everonn-database.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `scripts/configure-usage-scheduler.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/usage/worker.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `lib/usage-scheduler.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `lib/app-records.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `lib/usage-postgres.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/amplify-env.test.ts`, `tests/usage-scheduler.test.ts`, `tests/app-records.test.ts`, `scripts/smoke-auth-database.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

A build and scheduled usage worker are not a 99.9% voice SLO, restore/PITR proof, multi-region service or 1,000-sites/day load pass.

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

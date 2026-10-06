# EVN-OPS-072 - Scale by adding capacity

Project: EverOnnAI. Module: [Infrastructure, durable workflows, reliability and scale](../README.md). Source business requirement [BR-072](../../../requirements/BR.md#br-072).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | SRE/Platform Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P2 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-OPS-102](EVN-OPS-102.md), [EVN-OPS-103](EVN-OPS-103.md), [EVN-OPS-104](EVN-OPS-104.md) |

## Business deliverable

Scale by adding capacity. The platform scales to 1,000 clients, then 10,000, by adding capacity rather than re-architecting.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Batching bounds one request; target scale has not been proven.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Build cell/region placement, fair quotas/capacity automation; prove tenant/desk/call/site load targets.

## Technical component

- [ ] Implement the module boundary and contracts for: Cell router, scaling, fair queues, load/soak harness.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Guarded migrations and usage-worker infrastructure; no general domain bus/cells/media drain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] tenant_placement, cells, capacity_metrics.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Capacity/queue/SLO dashboards.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Scale by adding capacity. The platform scales to 1,000 clients, then 10,000, by adding capacity rather than re-architecting. | Cell router, scaling, fair queues, load/soak harness | Tenant-scoped end-to-end demonstration of the outcome |
| Build cell/region placement, fair quotas/capacity automation; prove tenant/desk/call/site load targets. | tenant_placement, cells, capacity_metrics; Capacity/queue/SLO dashboards | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Model budgets and latency-aware placement | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Cell router, scaling, fair queues, load/soak harness.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Model budgets and latency-aware placement.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-51](../../../requirements/AT.md#at-51) | Load at twice the P1 design capacity | Service levels met; per-stage latency reported; desk offers keep their p95 targets | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-052](../../../requirements/US.md#us-052).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AR-005](../../../requirements/AR.md#ar-005) | Source-linked | 11.7 Architecture requirements |
| [AT-51](../../../requirements/AT.md#at-51) | Source-linked | 25.2 Acceptance tests |
| [BO-6](../../../requirements/BO.md#bo-6) | Source-linked | 3.1 Business objectives |
| [BR-072](../../../requirements/BR.md#br-072) | Source-linked | 7.11 Platform, security, compliance and reliability |
| [LT-002](../../../requirements/LT.md#lt-002) | Source-linked | 23.7 Load and soak testing requirements |
| [TEN-002](../../../requirements/TEN.md#ten-002) | Source-linked | 12.3 Tenancy model requirements |
| [US-052](../../../requirements/US.md#us-052) | Source-linked | EP-11 Integrations, scale and ownership |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [AR-005](../../../requirements/AR.md#ar-005): AR-005 [P1] MUST be cell-ready: a "cell" is a complete stack (API, workers, DB schema set, Redis, media/voice workers) serving a subset of tenants. tenants.cell_id and a routing map MUST exist from P1 even if only one cell runs. Adding a cell MUST be scriptable (infra as code).
- [ ] [LT-002](../../../requirements/LT.md#lt-002): LT-002 [P2] MUST repeat at 3x projected P2 peak (about 200 concurrent calls) plus a 24-hour soak test to detect leaks.
- [ ] [TEN-002](../../../requirements/TEN.md#ten-002): TEN-002 [P1] MUST include tenants.cell_id, tenants.region, tenants.data_residency and tenants.tier columns and a routing map from day one (scaffolding for cells, regional residency and dedicated-schema enterprise tenants).

## Existing code / check evidence

- `amplify.yml` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/write-amplify-env.mjs` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/migrate-everonn-database.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/configure-usage-scheduler.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/worker.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/usage-scheduler.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/app-records.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/usage-postgres.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/amplify-env.test.ts`, `tests/usage-scheduler.test.ts`, `tests/app-records.test.ts`, `scripts/smoke-auth-database.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: A build and scheduled usage worker are not a 99.9% voice SLO, restore/PITR proof, multi-region service or 1,000-sites/day load pass.

Dependencies: [EVN-OPS-102](EVN-OPS-102.md), [EVN-OPS-103](EVN-OPS-103.md), [EVN-OPS-104](EVN-OPS-104.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.

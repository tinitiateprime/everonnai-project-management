# EVN-OPS-068 - Reliability during outages

Project: EverOnnAI. Module: [Infrastructure, durable workflows, reliability and scale](../README.md). Source business requirement [BR-068](../../../requirements/BR.md#br-068).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | SRE/Platform Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-OPS-102](EVN-OPS-102.md), [EVN-OPS-103](EVN-OPS-103.md), [EVN-OPS-104](EVN-OPS-104.md) |

## Business deliverable

Reliability during outages. Calls are still answered safely during vendor or system outages, and the platform recovers from failures within stated targets.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Model fallback, failed-booking safety, worker recovery and metering reconciliation exist.

## Remaining delivery checklist

- [ ] Prove voice/carrier/speech/DB failures, cached continuity, buffering and RPO/RTO restore targets.

## Technical component

- [ ] Implement the module boundary and contracts for: Health, failover, backups/restore and chaos drills.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Guarded migrations and usage-worker infrastructure; no general domain bus/cells/media drain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] health_events, fallback_config, buffered_events.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Outage/fallback/recovery evidence.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Reliability during outages. Calls are still answered safely during vendor or system outages, and the platform recovers from failures within stated targets. | Health, failover, backups/restore and chaos drills | Tenant-scoped end-to-end demonstration of the outcome |
| Prove voice/carrier/speech/DB failures, cached continuity, buffering and RPO/RTO restore targets. | health_events, fallback_config, buffered_events; Outage/fallback/recovery evidence | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Safe capture when all models fail; no invented completion | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Health, failover, backups/restore and chaos drills.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Safe capture when all models fail.
- [ ] no invented completion.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-49](../../../requirements/AT.md#at-49) | Language-model or carrier outage during live calls, and a backup restore | Fallback within 1.2 s or a safe flow; carrier reroute within 60 s; message captured; restore into an isolated environment within the target recovery time | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-045](../../../requirements/US.md#us-045).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ADM-007](../../../requirements/ADM.md#adm-007) | Source-linked | 19.3 Admin back-office (ADM) |
| [AR-004](../../../requirements/AR.md#ar-004) | Source-linked | 11.7 Architecture requirements |
| [AT-49](../../../requirements/AT.md#at-49) | Source-linked | 25.2 Acceptance tests |
| [BO-1](../../../requirements/BO.md#bo-1) | Source-linked | 3.1 Business objectives |
| [BO-3](../../../requirements/BO.md#bo-3) | Source-linked | 3.1 Business objectives |
| [BR-068](../../../requirements/BR.md#br-068) | Source-linked | 7.11 Platform, security, compliance and reliability |
| [SL-01](../../../requirements/SL.md#sl-01) | Plan allocation / source cross-reference | 10.1 Service levels |
| [SL-08](../../../requirements/SL.md#sl-08) | Plan allocation / source cross-reference | 10.1 Service levels |
| [US-045](../../../requirements/US.md#us-045) | Source-linked | EP-09 Administration and operations |
| [VOX-036](../../../requirements/VOX.md#vox-036) | Source-linked | 14.3 Requirements: telephony and numbers |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ADM-007](../../../requirements/ADM.md#adm-007): ADM-007 [P1] MUST provide an incident toolkit: broadcast banner to tenants, per-tenant fallback switch (route all calls to owner or to message-capture), and vendor failover controls.
- [ ] [AR-004](../../../requirements/AR.md#ar-004): AR-004 [P1] MUST ensure the voice path degrades gracefully: if the control plane, database or a primary vendor is down, calls still get answered with cached configuration and a fallback provider or a safe fallback flow (take a message, text the owner). Test with chaos drills in P2.
- [ ] [SL-01](../../../requirements/SL.md#sl-01): SL-01 | Inbound calls answered by the AI, or safely captured, on the voice path | 99.9% availability per month.
- [ ] [SL-08](../../../requirements/SL.md#sl-08): SL-08 | Client websites | 99.95% availability per month.
- [ ] [VOX-036](../../../requirements/VOX.md#vox-036): VOX-036 [P2] MUST support multi-carrier failover with health checks and automatic reroute within 60 seconds of detected carrier degradation.

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

# EVN-OPS-101 - Keep business events and delayed work reliable across retries

Project: EverOnnAI. Module: [Infrastructure, durable workflows, reliability and scale](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | SRE/Platform Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P0 foundation / P1 completion |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md) |

## Business deliverable

Keep business events and delayed work reliable across retries.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] A specialised durable usage outbox and worker exist.

## Remaining delivery checklist

- [ ] Add general domain outbox/events, queue/scheduler interfaces, consumer idempotency, dead letters and reconciliation.

## Technical component

- [ ] Implement the module boundary and contracts for: Outbox publisher, durable timers, fair queues and worker recovery.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Guarded migrations and usage-worker infrastructure; no general domain bus/cells/media drain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] domain_outbox, jobs, timers, receipts, dead_letters.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Job/event health and replay controls.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Keep business events and delayed work reliable across retries. | Outbox publisher, durable timers, fair queues and worker recovery | Tenant-scoped end-to-end demonstration of the outcome |
| Add general domain outbox/events, queue/scheduler interfaces, consumer idempotency, dead letters and reconciliation. | domain_outbox, jobs, timers, receipts, dead_letters; Job/event health and replay controls | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | AI jobs are budgeted and side effects have verified receipts | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Outbox publisher, durable timers, fair queues and worker recovery.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] AI jobs are budgeted and side effects have verified receipts.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

No dedicated source AT is assigned to this enabling/extension ticket. Define a ticket-specific acceptance report before closing it; the module and release gates still apply.

Source stories: No dedicated source story; business/enabling outcome above is the acceptance brief.

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ANL-002](../../../requirements/ANL.md#anl-002) | Plan allocation / source cross-reference | 19.2 Analytics and reporting (ANL) |
| [AR-003](../../../requirements/AR.md#ar-003) | Source-linked | 11.7 Architecture requirements |
| [AR-006](../../../requirements/AR.md#ar-006) | Source-linked | 11.7 Architecture requirements |
| [AR-007](../../../requirements/AR.md#ar-007) | Source-linked | 11.7 Architecture requirements |
| [SCF-003](../../../requirements/SCF.md#scf-003) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ANL-002](../../../requirements/ANL.md#anl-002): ANL-002 [P1] MUST provide a platform analytics pipeline: events (Appendix C) flow to an analytics store for internal reporting. P1 MAY use MariaDB read replicas and materialized summary tables; P2 SHOULD introduce a columnar store (for example ClickHouse or MariaDB ColumnStore, subject to the RHEL/MariaDB exception process) fed by the outbox stream.
- [ ] [AR-003](../../../requirements/AR.md#ar-003): AR-003 [P0] MUST use an event-driven backbone: state changes emit versioned domain events (Appendix C) via an outbox table, so that workers, analytics, webhooks and future services consume them without coupling. The outbox pattern MUST be used so events are never lost on commit.
- [ ] [AR-006](../../../requirements/AR.md#ar-006): AR-006 [P1] MUST make every service stateless where possible, with 12-factor configuration; state lives in MariaDB, Redis or object storage.
- [ ] [AR-007](../../../requirements/AR.md#ar-007): AR-007 [P1] MUST version all external APIs (/v1), all events, all agent configuration schemas, and all prompt templates.
- [ ] [SCF-003](../../../requirements/SCF.md#scf-003): 3 | Transactional outbox and versioned domain events | Kafka-class bus, analytics warehouse, partner webhooks, agency integrations.

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

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.

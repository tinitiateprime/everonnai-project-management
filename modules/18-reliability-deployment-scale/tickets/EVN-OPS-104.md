# EVN-OPS-104 - Measure latency, capacity and cost before promising scale

Project: EverOnnAI. Module: [Infrastructure, durable workflows, reliability and scale](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | SRE/Platform Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-OPS-102](EVN-OPS-102.md), [EVN-AIQ-103](../../03-ai-governance-evaluation/tickets/EVN-AIQ-103.md), [EVN-VOX-101](../../04-telephone-voice-language/tickets/EVN-VOX-101.md) |

## Business deliverable

Measure latency, capacity and cost before promising scale.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Usage worker heartbeat and some provider/job status exist.

## Remaining delivery checklist

- [ ] Add OpenTelemetry/RUM/SLO budgets, alerting, EXPLAIN reviews and source call/site/desk/API load and soak tests.

## Technical component

- [ ] Implement the module boundary and contracts for: Tracing, monitoring, synthetic canaries and load harness.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Guarded migrations and usage-worker infrastructure; no general domain bus/cells/media drain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] telemetry labels, SLO reports, capacity/cost results.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] SLO, provider/queue/desk and capacity dashboards.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Measure latency, capacity and cost before promising scale. | Tracing, monitoring, synthetic canaries and load harness | Tenant-scoped end-to-end demonstration of the outcome |
| Add OpenTelemetry/RUM/SLO budgets, alerting, EXPLAIN reviews and source call/site/desk/API load and soak tests. | telemetry labels, SLO reports, capacity/cost results; SLO, provider/queue/desk and capacity dashboards | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Report model/speech latency and cost by task; targets are not measured results | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Tracing, monitoring, synthetic canaries and load harness.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Report model/speech latency and cost by task.
- [ ] targets are not measured results.
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
| [ANL-003](../../../requirements/ANL.md#anl-003) | Plan allocation / source cross-reference | 19.2 Analytics and reporting (ANL) |
| [CST-002](../../../requirements/CST.md#cst-002) | Source-linked | 23.6 Unit economics and cost controls |
| [CST-004](../../../requirements/CST.md#cst-004) | Source-linked | 23.6 Unit economics and cost controls |
| [CST-005](../../../requirements/CST.md#cst-005) | Source-linked | 23.6 Unit economics and cost controls |
| [CST-006](../../../requirements/CST.md#cst-006) | Source-linked | 23.6 Unit economics and cost controls |
| [CST-007](../../../requirements/CST.md#cst-007) | Source-linked | 23.6 Unit economics and cost controls |
| [LT-001](../../../requirements/LT.md#lt-001) | Source-linked | 23.7 Load and soak testing requirements |
| [LT-002](../../../requirements/LT.md#lt-002) | Source-linked | 23.7 Load and soak testing requirements |
| [LT-003](../../../requirements/LT.md#lt-003) | Source-linked | 23.7 Load and soak testing requirements |
| [LT-004](../../../requirements/LT.md#lt-004) | Source-linked | 23.7 Load and soak testing requirements |
| [LT-006](../../../requirements/LT.md#lt-006) | Source-linked | 23.7 Load and soak testing requirements |
| [SCF-018](../../../requirements/SCF.md#scf-018) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SL-02](../../../requirements/SL.md#sl-02) | Plan allocation / source cross-reference | 10.1 Service levels |
| [VOX-042](../../../requirements/VOX.md#vox-042) | Source-linked | 14.6 Voice runtime deployment requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ANL-003](../../../requirements/ANL.md#anl-003): ANL-003 [P1] MUST provide quality dashboards: latency per stage, guardrail hits, escalation rates and reasons, QA scores, eval pass rates by agent version, cost per call and per tenant, and vendor error rates.
- [ ] [CST-002](../../../requirements/CST.md#cst-002): CST-002 [P1] MUST implement per-call, per-tenant and global cost budgets with alerts and circuit breakers (VOX-026), and dashboards for margin by tenant (ADM-004).
- [ ] [CST-004](../../../requirements/CST.md#cst-004): CST-004 [P1] MUST avoid paying for silence: end calls on abandonment quickly, no long dead-air billing, and detect voicemail or automated systems early.
- [ ] [CST-005](../../../requirements/CST.md#cst-005): CST-005 [P2] SHOULD evaluate self-hosted STT and open-weight LLMs and speech-to-speech models once volume justifies, guided by the eval harness so quality does not regress.
- [ ] [CST-006](../../../requirements/CST.md#cst-006): CST-006 [P1] MUST set plan-level minute allowances and overage (Decision D-1) and fair-use rules; enforce through BIL-004/005.
- [ ] [CST-007](../../../requirements/CST.md#cst-007): CST-007 [P2] MUST model, meter and report the cost of operator-handled time per client, vertical and escalation reason (§16.7.5), so that operator add-on pricing (D-1) covers it and escalation rate can be managed as a margin lever.
- [ ] [LT-001](../../../requirements/LT.md#lt-001): LT-001 [P1] MUST simulate concurrent calls end to end (synthetic callers over SIP with TTS audio and noise) at 2x P1 design capacity for 60 minutes with no SLO breach, and report per-stage latency percentiles.
- [ ] [LT-002](../../../requirements/LT.md#lt-002): LT-002 [P2] MUST repeat at 3x projected P2 peak (about 200 concurrent calls) plus a 24-hour soak test to detect leaks.
- [ ] [LT-003](../../../requirements/LT.md#lt-003): LT-003 [P2] MUST load-test the generation pipeline at 1,000 sites/day with bursts of 300/hour, including provider rate-limit behavior and cost accounting.
- [ ] [LT-004](../../../requirements/LT.md#lt-004): LT-004 [P2] MUST load-test the API and inbox with 100,000 conversations per tenant on the largest tenant profile, and 10,000 tenants of synthetic data.
- [ ] [LT-006](../../../requirements/LT.md#lt-006): LT-006 [P2] MUST load-test the Live Agent Desk with 300 concurrent operator sessions, 100 offers per minute, simultaneous acceptance races, and forced reconnects, verifying the desk performance targets in §16.7.4.
- [ ] [SCF-018](../../../requirements/SCF.md#scf-018): 18 | Trace ids and tenant/cost labels on every log, event and span | SLOs per tenant, cost attribution, faster incident forensics.
- [ ] [SL-02](../../../requirements/SL.md#sl-02): SL-02 | Caller-perceived response gap | Median under 1.0 s; 95th percentile under 1.8 s.
- [ ] [VOX-042](../../../requirements/VOX.md#vox-042): VOX-042 [P1] MUST emit per-turn traces (OpenTelemetry) covering endpointing, STT, retrieval, LLM, tool, TTS spans, plus per-call cost attribution.

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

Dependencies: [EVN-OPS-102](EVN-OPS-102.md), [EVN-AIQ-103](../../03-ai-governance-evaluation/tickets/EVN-AIQ-103.md), [EVN-VOX-101](../../04-telephone-voice-language/tickets/EVN-VOX-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.

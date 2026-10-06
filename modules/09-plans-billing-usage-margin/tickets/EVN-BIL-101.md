# EVN-BIL-101 - Show trustworthy observed Gemini and ElevenLabs usage

Project: EverOnnAI. Module: [Plans, subscriptions, metering, budgets and margin](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Implemented (bounded slice) |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Finance/Product Owner + Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md) |

## Business deliverable

Show trustworthy observed Gemini and ElevenLabs usage.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Durable attempts, metadata journals, scoped summaries, duplicate/replay rejection and worker health are implemented.

## Remaining delivery checklist

- [ ] Maintain provider receipt/reconciliation evidence; all-provider billing/allowances remain separate BR-041/042 work.

## Technical component

- [ ] Implement the module boundary and contracts for: Signed worker, usage adapters, journals and exactly-once-in-effect aggregation.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: usage_events, usage_sessions, usage_outbox, usage_claims, billing_reports, worker state/nonces/receipts.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] Private usage ledger, outbox/session/claim and billing-report tables.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Workspace usage dashboard with coverage and estimate labels.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Show trustworthy observed Gemini and ElevenLabs usage. | Signed worker, usage adapters, journals and exactly-once-in-effect aggregation | Tenant-scoped end-to-end demonstration of the outcome |
| Maintain provider receipt/reconciliation evidence; all-provider billing/allowances remain separate BR-041/042 work. | Private usage ledger, outbox/session/claim and billing-report tables; Workspace usage dashboard with coverage and estimate labels | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Count retries/discarded output and separate actual charges from estimates | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Signed worker, usage adapters, journals and exactly-once-in-effect aggregation.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Count retries/discarded output and separate actual charges from estimates.
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
| [BIL-004](../../../requirements/BIL.md#bil-004) | Source-linked | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BIL-007](../../../requirements/BIL.md#bil-007) | Source-linked | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BRL-014](../../../requirements/BRL.md#brl-014) | Plan allocation / source cross-reference | 8. Business rules |
| [SCF-020](../../../requirements/SCF.md#scf-020) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BIL-004](../../../requirements/BIL.md#bil-004): BIL-004 [P1] MUST implement usage metering: every billable or cost-bearing action emits an immutable usage_event (tenant_id, meter, quantity, unit, occurred_at, source_id, provider_cost_estimate). Meters: voice minutes (inbound, transfer legs), SMS segments, chat conversations or messages (per policy), HITL minutes, site generation, storage. Aggregation is exactly-once in effect (idempotent keys). Usage is pushed to Stripe metered billing where used, and shown to owners in near-real time with alerts at 80% and 100% of allowance.
- [ ] [BIL-007](../../../requirements/BIL.md#bil-007): BIL-007 [P1] MUST compute and store per-tenant cost of service (telephony, STT, LLM tokens, TTS characters, SMS, storage) to power margin dashboards (ADM-004) and cost circuit breakers (VOX-026).
- [ ] [BRL-014](../../../requirements/BRL.md#brl-014): BRL-014 | Plans grant entitlements; usage beyond an allowance follows the plan's overage or cap rule. | Billing | BIL-001, BIL-004, BIL-005.
- [ ] [SCF-020](../../../requirements/SCF.md#scf-020): 20 | Idempotency keys and exactly-once-in-effect patterns for payments, metering, SMS | Safe retries, replays, reconciliation and billing accuracy.

## Existing code / check evidence

- `features/usage/gemini.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/elevenlabs.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/worker.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/summary.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/pricing.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/billing.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/job-auth.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/webhook.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/dashboard/usage-section.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/usage-postgres.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/usage-scheduler.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/usage.test.ts`, `tests/usage-reliability.test.ts`, `tests/usage-scheduler.test.ts`, `tests/usage-supabase.test.ts`, `scripts/smoke-usage.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Observed usage/estimated provider costs are not subscriptions, Stripe invoices, plan enforcement, all-channel costs or measured margins.

Dependencies: [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.

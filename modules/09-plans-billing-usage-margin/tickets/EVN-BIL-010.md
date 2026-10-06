# EVN-BIL-010 - Fraud and cost protection

Project: EverOnnAI. Module: [Plans, subscriptions, metering, budgets and margin](../README.md). Source business requirement [BR-010](../../../requirements/BR.md#br-010).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Finance/Product Owner + Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-BIL-101](EVN-BIL-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md) |

## Business deliverable

Fraud and cost protection. Clients are protected from fraud and runaway usage costs on their lines.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Selected API rate limits and provider usage reporting exist.

## Remaining delivery checklist

- [ ] Enforce call/minute budgets, destination restrictions, anomaly alerts and kill switches while preserving emergencies.

## Technical component

- [ ] Implement the module boundary and contracts for: Quotas, toll-fraud checks and circuit breakers.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: usage_events, usage_sessions, usage_outbox, usage_claims, billing_reports, worker state/nonces/receipts.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] cost_budgets, call_caps, fraud_events.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Budget alerts and authorised kill controls.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Fraud and cost protection. Clients are protected from fraud and runaway usage costs on their lines. | Quotas, toll-fraud checks and circuit breakers | Tenant-scoped end-to-end demonstration of the outcome |
| Enforce call/minute budgets, destination restrictions, anomaly alerts and kill switches while preserving emergencies. | cost_budgets, call_caps, fraud_events; Budget alerts and authorised kill controls | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Safe wrap-up or human fallback at budget boundaries | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Quotas, toll-fraud checks and circuit breakers.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Safe wrap-up or human fallback at budget boundaries.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-48](../../../requirements/AT.md#at-48) | Plan limit reached mid-month, and a toll-fraud attempt | Overage or cap rule applied without dropping emergencies; alerts at 80% and 100%; caps and the kill switch stop abusive traffic | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-043](../../../requirements/US.md#us-043).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-48](../../../requirements/AT.md#at-48) | Source-linked | 25.2 Acceptance tests |
| [BO-5](../../../requirements/BO.md#bo-5) | Source-linked | 3.1 Business objectives |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BR-010](../../../requirements/BR.md#br-010) | Source-linked | 7.1 Answering calls |
| [SEC-008](../../../requirements/SEC.md#sec-008) | Source-linked | 22.2 Security requirements |
| [US-043](../../../requirements/US.md#us-043) | Source-linked | EP-08 Billing, plans and cost |
| [VOX-026](../../../requirements/VOX.md#vox-026) | Source-linked | 14.5 Requirements: business behavior |
| [VOX-037](../../../requirements/VOX.md#vox-037) | Source-linked | 14.3 Requirements: telephony and numbers |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [SEC-008](../../../requirements/SEC.md#sec-008): SEC-008 [P1] MUST implement abuse and fraud controls: per-IP, per-session, per-tenant rate limits and quotas; bot management on public forms and the widget; signup velocity and disposable-email checks; premium-rate and geo restrictions; unusual-usage alerts; identity verification (out-of-band OTP) before revealing or changing sensitive data over voice or chat.
- [ ] [VOX-026](../../../requirements/VOX.md#vox-026): VOX-026 [P1] MUST support per-call and per-day cost circuit breakers (for example a call exceeding 15 minutes triggers a graceful wrap-up or human transfer).
- [ ] [VOX-037](../../../requirements/VOX.md#vox-037): VOX-037 [P1] MUST implement toll-fraud and traffic-pumping defenses: per-tenant concurrent-call and daily-minute caps, geographic permission lists (default US/Canada), premium-rate and high-cost destination blocks for transfers, alerts on anomalies, and an emergency "kill switch" per tenant and per number.

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

Dependencies: [EVN-BIL-101](EVN-BIL-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.

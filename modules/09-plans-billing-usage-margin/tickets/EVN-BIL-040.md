# EVN-BIL-040 - Plans and billing

Project: EverOnnAI. Module: [Plans, subscriptions, metering, budgets and margin](../README.md). Source business requirement [BR-040](../../../requirements/BR.md#br-040).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Finance/Product Owner + Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-BIL-101](EVN-BIL-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md) |

## Business deliverable

Plans and billing. Subscription plans are data-driven and billed monthly or annually through a hosted payment provider.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Billing clearly reports subscriptions are not connected.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Build entitlements and Stripe hosted checkout/portal, invoices, taxes, dunning and reconciliation.

## Technical component

- [ ] Implement the module boundary and contracts for: PaymentProvider, signed webhooks and reconciliation.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: usage_events, usage_sessions, usage_outbox, usage_claims, billing_reports, worker state/nonces/receipts.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] plans, entitlements, subscriptions, invoices.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Plans, hosted checkout/portal and subscription state.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Plans and billing. Subscription plans are data-driven and billed monthly or annually through a hosted payment provider. | PaymentProvider, signed webhooks and reconciliation | Tenant-scoped end-to-end demonstration of the outcome |
| Build entitlements and Stripe hosted checkout/portal, invoices, taxes, dunning and reconciliation. | plans, entitlements, subscriptions, invoices; Plans, hosted checkout/portal and subscription state | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | N/A; approved pricing and charges are deterministic | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] PaymentProvider, signed webhooks and reconciliation.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

N/A; approved pricing and charges are deterministic. AI is outside this ticket's runtime scope.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-56](../../../requirements/AT.md#at-56) | Subscription, entitlements and margin | A plan change reaches entitlements without a deployment; Stripe reconciliation is clean; margin per client including operator minutes is visible | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-041](../../../requirements/US.md#us-041), [US-042](../../../requirements/US.md#us-042).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-56](../../../requirements/AT.md#at-56) | Source-linked | 25.2 Acceptance tests |
| [BIL-001](../../../requirements/BIL.md#bil-001) | Source-linked | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BIL-002](../../../requirements/BIL.md#bil-002) | Source-linked | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BIL-003](../../../requirements/BIL.md#bil-003) | Source-linked | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BIL-006](../../../requirements/BIL.md#bil-006) | Plan allocation / source cross-reference | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BIL-008](../../../requirements/BIL.md#bil-008) | Plan allocation / source cross-reference | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BIL-010](../../../requirements/BIL.md#bil-010) | Plan allocation / source cross-reference | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BO-5](../../../requirements/BO.md#bo-5) | Source-linked | 3.1 Business objectives |
| [BR-040](../../../requirements/BR.md#br-040) | Source-linked | 7.7 Commercial model |
| [BRL-014](../../../requirements/BRL.md#brl-014) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-024](../../../requirements/BRL.md#brl-024) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-025](../../../requirements/BRL.md#brl-025) | Plan allocation / source cross-reference | 8. Business rules |
| [ORD-009](../../../requirements/ORD.md#ord-009) | Plan allocation / source cross-reference | 19.9 Online ordering and restaurant workflow (ORD) |
| [SCF-005](../../../requirements/SCF.md#scf-005) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [US-041](../../../requirements/US.md#us-041) | Source-linked | EP-08 Billing, plans and cost |
| [US-042](../../../requirements/US.md#us-042) | Source-linked | EP-08 Billing, plans and cost |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BIL-001](../../../requirements/BIL.md#bil-001): BIL-001 [P1] MUST implement plans and entitlements as data: plan → entitlements (features, limits, included usage, overage rates), with per-tenant overrides, effective dates and full history. Application code checks entitlements, never plan names.
- [ ] [BIL-002](../../../requirements/BIL.md#bil-002): BIL-002 [P1] MUST use Stripe (Billing, Checkout/Customer Portal hosted pages so card data never touches EverOnn systems, SAQ-A scope) behind PaymentProvider. Support monthly and annual, coupons, trials, proration, tax (Stripe Tax), invoices and receipts, and dunning with a grace period before suspension.
- [ ] [BIL-003](../../../requirements/BIL.md#bil-003): BIL-003 [P1] MUST implement webhook handling with signature verification, idempotency, replay protection, and reconciliation jobs that compare Stripe state to local state daily.
- [ ] [BIL-006](../../../requirements/BIL.md#bil-006): BIL-006 [P2] SHOULD support outcome-based add-ons (for example fee per booked job) with a clear, auditable definition of a billable outcome, dispute handling, and owner-visible logs. Requires product sign-off (Decision D-1).
- [ ] [BIL-008](../../../requirements/BIL.md#bil-008): BIL-008 [P3] MAY support reseller/agency billing (wholesale pricing, consolidated invoices, white-label receipts).
- [ ] [BIL-010](../../../requirements/BIL.md#bil-010): BIL-010 [P2] SHOULD support per-order and per-handled-minute fee components alongside subscriptions, for restaurant ordering and operator handling.
- [ ] [BRL-014](../../../requirements/BRL.md#brl-014): BRL-014 | Plans grant entitlements; usage beyond an allowance follows the plan's overage or cap rule. | Billing | BIL-001, BIL-004, BIL-005.
- [ ] [BRL-024](../../../requirements/BRL.md#brl-024): BRL-024 | EverOnn's public statements about customers, results and capabilities are supported by evidence; illustrative examples are labeled as illustrative, and named results are published only with the customer's approval. | Marketing | BIL-001, API-001.
- [ ] [BRL-025](../../../requirements/BRL.md#brl-025): BRL-025 | Public descriptions of what a plan includes come from the same entitlement data the platform enforces, so a published plan never promises what the platform does not deliver. | Pricing and marketing | BIL-001, API-001, ADM-002.
- [ ] [ORD-009](../../../requirements/ORD.md#ord-009): ORD-009 [P2] SHOULD support fee models that are a flat subscription plus usage by default, with optional per-order pricing, and integrate with the savings comparison for providers that charge a percentage of orders (ACQ-007).
- [ ] [SCF-005](../../../requirements/SCF.md#scf-005): 5 | Plans and entitlements as data; metering events with idempotency keys | New plans, usage pricing, outcome pricing, agencies, marketplace.

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

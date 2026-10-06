# EVN-BIL-043 - Published claims match the product

Project: EverOnnAI. Module: [Plans, subscriptions, metering, budgets and margin](../README.md). Source business requirement [BR-043](../../../requirements/BR.md#br-043).

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

Published claims match the product. Published pricing, plan contents and product claims always match what the platform delivers, and comparative, savings and results claims are supported by a dated source and approved before they are published.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Usage/billing UI avoids fake invoices; marketing claims/prices remain static.

## Remaining delivery checklist

- [ ] Drive claims/plans from real entitlements and approved dated sources with expiry.

## Technical component

- [ ] Implement the module boundary and contracts for: Plan-data API, claim validity and release gate.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: usage_events, usage_sessions, usage_outbox, usage_claims, billing_reports, worker state/nonces/receipts.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] price_books, claims_register, claim_approvals.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Claims/pricing review and publication diff.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Published claims match the product. Published pricing, plan contents and product claims always match what the platform delivers, and comparative, savings and results claims are supported by a dated source and approved before they are published. | Plan-data API, claim validity and release gate | Tenant-scoped end-to-end demonstration of the outcome |
| Drive claims/plans from real entitlements and approved dated sources with expiry. | price_books, claims_register, claim_approvals; Claims/pricing review and publication diff | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | No invented testimonials, savings or ROI | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Plan-data API, claim validity and release gate.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] No invented testimonials, savings or ROI.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-25](../../../requirements/AT.md#at-25) | Savings comparison and claims file | The calculator shows current cost, contract and termination fees, retained services and break-even; unconfirmed inputs are labeled; a claim cannot be used until approved and unexpired | Full source scenario not evidenced; client acceptance pending |
| [AT-55](../../../requirements/AT.md#at-55) | Published plans match enforced entitlements | The public plan data and the marketing pricing page are generated from the same entitlement data; a contradiction between a plan card, a comparison table and the entitlements fails the release checks | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-042](../../../requirements/US.md#us-042).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ACQ-010](../../../requirements/ACQ.md#acq-010) | Source-linked | 19.7 Customer acquisition (ACQ) |
| [ADM-002](../../../requirements/ADM.md#adm-002) | Source-linked | 19.3 Admin back-office (ADM) |
| [API-001](../../../requirements/API.md#api-001) | Source-linked | 19.4 Public API, webhooks and integrations (API) |
| [AT-25](../../../requirements/AT.md#at-25) | Source-linked | 25.2 Acceptance tests |
| [AT-55](../../../requirements/AT.md#at-55) | Source-linked | 25.2 Acceptance tests |
| [BIL-001](../../../requirements/BIL.md#bil-001) | Source-linked | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BO-8](../../../requirements/BO.md#bo-8) | Source-linked | 3.1 Business objectives |
| [BR-043](../../../requirements/BR.md#br-043) | Source-linked | 7.7 Commercial model |
| [BRL-014](../../../requirements/BRL.md#brl-014) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-024](../../../requirements/BRL.md#brl-024) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-025](../../../requirements/BRL.md#brl-025) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-030](../../../requirements/BRL.md#brl-030) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-032](../../../requirements/BRL.md#brl-032) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-038](../../../requirements/BRL.md#brl-038) | Plan allocation / source cross-reference | 8. Business rules |
| [SCF-017](../../../requirements/SCF.md#scf-017) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [US-042](../../../requirements/US.md#us-042) | Source-linked | EP-08 Billing, plans and cost |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ACQ-010](../../../requirements/ACQ.md#acq-010): ACQ-010 [P1] MUST keep a claims register: every comparative statement, savings figure, statistic, customer story or testimonial used in outreach or on any brand's site is recorded with its source, date, approver and expiry. Templates and site content may reference only approved, unexpired claims. Competitor names appear only as plain text, without logos or any implication of affiliation.
- [ ] [ADM-002](../../../requirements/ADM.md#adm-002): ADM-002 [P1] MUST provide feature flags and staged rollouts (per tenant, per plan, percentage), a kill switch per capability and per vendor, and audit of flag changes. Flags are evaluated via an OpenFeature-compatible interface.
- [ ] [API-001](../../../requirements/API.md#api-001): API-001 [P1] MUST expose a versioned REST API (/v1) described by OpenAPI 3.1, used by EverOnn's own frontends (no private back doors), with resource-oriented design, cursor pagination, idempotency keys on POST, consistent error format (RFC 9457 Problem Details), rate limit headers, and SDK generation (TypeScript first).
- [ ] [BIL-001](../../../requirements/BIL.md#bil-001): BIL-001 [P1] MUST implement plans and entitlements as data: plan → entitlements (features, limits, included usage, overage rates), with per-tenant overrides, effective dates and full history. Application code checks entitlements, never plan names.
- [ ] [BRL-014](../../../requirements/BRL.md#brl-014): BRL-014 | Plans grant entitlements; usage beyond an allowance follows the plan's overage or cap rule. | Billing | BIL-001, BIL-004, BIL-005.
- [ ] [BRL-024](../../../requirements/BRL.md#brl-024): BRL-024 | EverOnn's public statements about customers, results and capabilities are supported by evidence; illustrative examples are labeled as illustrative, and named results are published only with the customer's approval. | Marketing | BIL-001, API-001.
- [ ] [BRL-025](../../../requirements/BRL.md#brl-025): BRL-025 | Public descriptions of what a plan includes come from the same entitlement data the platform enforces, so a published plan never promises what the platform does not deliver. | Pricing and marketing | BIL-001, API-001, ADM-002.
- [ ] [BRL-030](../../../requirements/BRL.md#brl-030): BRL-030 | Savings and comparison claims rest on figures the prospect has confirmed or on clearly labeled estimates with a documented calculation; statements about competitors are truthful, factual and never imply an affiliation. | Marketing, sales | ACQ-007, ACQ-010.
- [ ] [BRL-032](../../../requirements/BRL.md#brl-032): BRL-032 | Vertical brands are presentation brands of one company. The contracting entity, privacy terms and client agreement always name EverOnn; no brand suggests independence it does not have; every claim, review or testimonial shown on a brand is true for that brand; trademarks are cleared before a brand launches. | Brands | VRT-001, VRT-009, ACQ-010.
- [ ] [BRL-038](../../../requirements/BRL.md#brl-038): BRL-038 | Market facts about providers (prices, features, customer counts, ownership) carry an as-of date and are refreshed before they are used in any sales material. | Marketing, sales | ACQ-001, ACQ-010.
- [ ] [SCF-017](../../../requirements/SCF.md#scf-017): 17 | Quotas and rate-limit framework keyed by tenant, plan, route and provider | Abuse control at scale, fair-use enforcement, tiered API limits.

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

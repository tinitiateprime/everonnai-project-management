# BIL - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## BIL-001

Assigned delivery tickets: [EVN-BIL-040](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md), [EVN-BIL-043](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-043.md).

**Primary source:** TECH section 19.1 Billing, plans, entitlements and metering (BIL); extraction row 1142.

**Source record:** BIL-001 [P1] MUST implement plans and entitlements as data: plan → entitlements (features, limits, included usage, overage rates), with per-tenant overrides, effective dates and full history. Application code checks entitlements, never plan names.

## BIL-002

Assigned delivery tickets: [EVN-BIL-040](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md).

**Primary source:** TECH section 19.1 Billing, plans, entitlements and metering (BIL); extraction row 1143.

**Source record:** BIL-002 [P1] MUST use Stripe (Billing, Checkout/Customer Portal hosted pages so card data never touches EverOnn systems, SAQ-A scope) behind PaymentProvider. Support monthly and annual, coupons, trials, proration, tax (Stripe Tax), invoices and receipts, and dunning with a grace period before suspension.

## BIL-003

Assigned delivery tickets: [EVN-BIL-040](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md).

**Primary source:** TECH section 19.1 Billing, plans, entitlements and metering (BIL); extraction row 1144.

**Source record:** BIL-003 [P1] MUST implement webhook handling with signature verification, idempotency, replay protection, and reconciliation jobs that compare Stripe state to local state daily.

## BIL-004

Assigned delivery tickets: [EVN-BIL-041](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-041.md), [EVN-BIL-101](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-101.md).

**Primary source:** TECH section 19.1 Billing, plans, entitlements and metering (BIL); extraction row 1145.

**Source record:** BIL-004 [P1] MUST implement usage metering: every billable or cost-bearing action emits an immutable usage_event (tenant_id, meter, quantity, unit, occurred_at, source_id, provider_cost_estimate). Meters: voice minutes (inbound, transfer legs), SMS segments, chat conversations or messages (per policy), HITL minutes, site generation, storage. Aggregation is exactly-once in effect (idempotent keys). Usage is pushed to Stripe metered billing where used, and shown to owners in near-real time with alerts at 80% and 100% of allowance.

## BIL-005

Assigned delivery tickets: [EVN-BIL-041](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-041.md).

**Primary source:** TECH section 19.1 Billing, plans, entitlements and metering (BIL); extraction row 1146.

**Source record:** BIL-005 [P1] MUST enforce limits without dropping emergencies: at the limit, follow the plan's rule (overage billing, soft cap with notice, or hard cap with safe fallback). P1 severity and emergency flows are never blocked by a cap; they are recorded and billed after.

## BIL-006

Assigned delivery tickets: [EVN-BIL-040](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md).

**Primary source:** TECH section 19.1 Billing, plans, entitlements and metering (BIL); extraction row 1147.

**Source record:** BIL-006 [P2] SHOULD support outcome-based add-ons (for example fee per booked job) with a clear, auditable definition of a billable outcome, dispute handling, and owner-visible logs. Requires product sign-off (Decision D-1).

## BIL-007

Assigned delivery tickets: [EVN-BIL-042](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-042.md), [EVN-BIL-101](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-101.md).

**Primary source:** TECH section 19.1 Billing, plans, entitlements and metering (BIL); extraction row 1148.

**Source record:** BIL-007 [P1] MUST compute and store per-tenant cost of service (telephony, STT, LLM tokens, TTS characters, SMS, storage) to power margin dashboards (ADM-004) and cost circuit breakers (VOX-026).

## BIL-008

Assigned delivery tickets: [EVN-BIL-040](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md).

**Primary source:** TECH section 19.1 Billing, plans, entitlements and metering (BIL); extraction row 1149.

**Source record:** BIL-008 [P3] MAY support reseller/agency billing (wholesale pricing, consolidated invoices, white-label receipts).

## BIL-009

Assigned delivery tickets: [EVN-VRT-044](../modules/10-brands-vertical-packs/tickets/EVN-VRT-044.md).

**Primary source:** TECH section 19.1 Billing, plans, entitlements and metering (BIL); extraction row 1150.

**Source record:** BIL-009 [P1] MUST hold brand-specific plan catalogs and price books as data, including time-bounded switching offers as entitlements, and expose them through the public plan data (API-001) so that every brand's website shows what the platform enforces (BRL-025).

## BIL-010

Assigned delivery tickets: [EVN-BIL-040](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md), [EVN-BIL-041](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-041.md).

**Primary source:** TECH section 19.1 Billing, plans, entitlements and metering (BIL); extraction row 1151.

**Source record:** BIL-010 [P2] SHOULD support per-order and per-handled-minute fee components alongside subscriptions, for restaurant ordering and operator handling.

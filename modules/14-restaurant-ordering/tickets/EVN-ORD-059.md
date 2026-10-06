# EVN-ORD-059 - Direct online ordering

Project: EverOnnAI. Module: [Restaurant menus, web/phone orders and kitchen delivery](../README.md). Source business requirement [BR-059](../../../requirements/BR.md#br-059).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Restaurant Product Owner + Integration Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P2 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-INB-101](../../08-inbox-contacts-booking-followup/tickets/EVN-INB-101.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md) |

## Business deliverable

Direct online ordering. Restaurant customers can order for pickup online from the restaurant's real menu, with modifiers, tax, pickup time and payment at pickup or by a hosted payment page.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Menu/order/payment domains are absent.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Deliver published menu/modifiers/tax/pickup totals, mobile orders and hosted/payment-at-pickup checkout.

## Technical component

- [ ] Implement the module boundary and contracts for: Pricing engine, OrderService and PaymentProvider.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: No menu/cart/order/payment/kitchen domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] menus, items, modifiers, carts, orders.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Menu/cart/checkout and order status.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Direct online ordering. Restaurant customers can order for pickup online from the restaurant's real menu, with modifiers, tax, pickup time and payment at pickup or by a hosted payment page. | Pricing engine, OrderService and PaymentProvider | Tenant-scoped end-to-end demonstration of the outcome |
| Deliver published menu/modifiers/tax/pickup totals, mobile orders and hosted/payment-at-pickup checkout. | menus, items, modifiers, carts, orders; Menu/cart/checkout and order status | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Totals/payments deterministic; grounded menu assistance only | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Pricing engine, OrderService and PaymentProvider.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Totals/payments deterministic.
- [ ] grounded menu assistance only.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-40](../../../requirements/AT.md#at-40) | Menu, web order and pay-at-pickup | A menu with combinations, sizes and modifiers is imported and published; a web order is placed with pickup time and correct tax; confirmation is received; the ticket appears on the staff screen and prints | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-069](../../../requirements/US.md#us-069).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-40](../../../requirements/AT.md#at-40) | Source-linked | 25.2 Acceptance tests |
| [BO-10](../../../requirements/BO.md#bo-10) | Source-linked | 3.1 Business objectives |
| [BR-059](../../../requirements/BR.md#br-059) | Source-linked | 7.10 Online ordering for restaurants |
| [BRL-036](../../../requirements/BRL.md#brl-036) | Plan allocation / source cross-reference | 8. Business rules |
| [ORD-001](../../../requirements/ORD.md#ord-001) | Source-linked | 19.9 Online ordering and restaurant workflow (ORD) |
| [ORD-002](../../../requirements/ORD.md#ord-002) | Source-linked | 19.9 Online ordering and restaurant workflow (ORD) |
| [ORD-006](../../../requirements/ORD.md#ord-006) | Source-linked | 19.9 Online ordering and restaurant workflow (ORD) |
| [ORD-008](../../../requirements/ORD.md#ord-008) | Plan allocation / source cross-reference | 19.9 Online ordering and restaurant workflow (ORD) |
| [ORD-009](../../../requirements/ORD.md#ord-009) | Plan allocation / source cross-reference | 19.9 Online ordering and restaurant workflow (ORD) |
| [ORD-010](../../../requirements/ORD.md#ord-010) | Plan allocation / source cross-reference | 19.9 Online ordering and restaurant workflow (ORD) |
| [US-069](../../../requirements/US.md#us-069) | Source-linked | EP-14 Restaurant ordering |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-036](../../../requirements/BRL.md#brl-036): BRL-036 | A restaurant order is confirmed by reading it back and is accepted only when the restaurant's workflow has received it. Payment card numbers are never spoken to, or stored by, the AI; payment is at pickup or by a payment link. | Ordering | ORD-003, ORD-004, ORD-006.
- [ ] [ORD-001](../../../requirements/ORD.md#ord-001): ORD-001 [P2] MUST provide menu management: categories, items, sizes, item numbers, combination meals with included sides, modifier groups (spice level, protein, rice, sauce on the side), substitutions and upcharges, bilingual names with romanization and pronunciation hints, dietary and allergen information (displayed for reference only), hours by day and period, availability and sold-out switches, preparation-time rules and tax settings. Menus are versioned and can be imported from an existing site, a document or an incumbent export.
- [ ] [ORD-002](../../../requirements/ORD.md#ord-002): ORD-002 [P2] MUST provide direct web ordering for pickup: mobile-first, pickup time estimates, totals with tax, a tip and fee policy the restaurant sets, guest checkout, payment at pickup or by card through a hosted payment page, confirmation and receipt, order status, and marketing consent kept separate from order confirmations.
- [ ] [ORD-006](../../../requirements/ORD.md#ord-006): ORD-006 [P2] MUST handle payments through a payment processor's hosted pages or links so that card data never touches EverOnn systems or recordings (SAQ A scope); funds settle to the restaurant's own merchant account; refunds, reconciliation and tax handling are supported.
- [ ] [ORD-008](../../../requirements/ORD.md#ord-008): ORD-008 [P2] SHOULD manage the restaurant's Google ordering and reservation links during migration, with the restaurant's authorization.
- [ ] [ORD-009](../../../requirements/ORD.md#ord-009): ORD-009 [P2] SHOULD support fee models that are a flat subscription plus usage by default, with optional per-order pricing, and integrate with the savings comparison for providers that charge a percentage of orders (ACQ-007).
- [ ] [ORD-010](../../../requirements/ORD.md#ord-010): ORD-010 [P2] MUST give the restaurant its order and customer data for export, with marketing consent recorded per customer.

## Existing code / check evidence



## Blockers and boundaries

Module risk: A service request is not an accepted restaurant order; payments, allergy escalation, kitchen receipts and pilot accuracy gates are unbuilt.

Dependencies: [EVN-INB-101](../../08-inbox-contacts-booking-followup/tickets/EVN-INB-101.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.

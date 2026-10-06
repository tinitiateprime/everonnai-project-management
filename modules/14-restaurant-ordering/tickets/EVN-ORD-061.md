# EVN-ORD-061 - Orders reach the kitchen

Project: EverOnnAI. Module: [Restaurant menus, web/phone orders and kitchen delivery](../README.md). Source business requirement [BR-061](../../../requirements/BR.md#br-061).

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

Orders reach the kitchen. Every accepted order reaches the restaurant reliably, through a staff-accept screen, printed tickets or an authorized point-of-sale connection, with no lost or duplicate orders and escalation of orders nobody accepts.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Kitchen delivery/acceptance is absent.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Deliver idempotent orders to staff/printer/POS, require acceptance, alert timeout and audit reprints.

## Technical component

- [ ] Implement the module boundary and contracts for: Order outbox, retry, receipts/reconciliation and escalation.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: No menu/cart/order/payment/kitchen domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] order_events, kitchen_receipts, printer_jobs.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Staff accept/decline and kitchen tickets.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Orders reach the kitchen. Every accepted order reaches the restaurant reliably, through a staff-accept screen, printed tickets or an authorized point-of-sale connection, with no lost or duplicate orders and escalation of orders nobody accepts. | Order outbox, retry, receipts/reconciliation and escalation | Tenant-scoped end-to-end demonstration of the outcome |
| Deliver idempotent orders to staff/printer/POS, require acceptance, alert timeout and audit reprints. | order_events, kitchen_receipts, printer_jobs; Staff accept/decline and kitchen tickets | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | No acceptance claim without actual staff/device receipt | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Order outbox, retry, receipts/reconciliation and escalation.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] No acceptance claim without actual staff/device receipt.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-40](../../../requirements/AT.md#at-40) | Menu, web order and pay-at-pickup | A menu with combinations, sizes and modifiers is imported and published; a web order is placed with pickup time and correct tax; confirmation is received; the ticket appears on the staff screen and prints | Full source scenario not evidenced; client acceptance pending |
| [AT-42](../../../requirements/AT.md#at-42) | Order routing reliability | Orders are never lost or duplicated across network loss and reconnection; an order nobody accepts escalates to a call to the restaurant within the service level | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-069](../../../requirements/US.md#us-069), [US-070](../../../requirements/US.md#us-070), [US-071](../../../requirements/US.md#us-071).

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
| [AT-42](../../../requirements/AT.md#at-42) | Source-linked | 25.2 Acceptance tests |
| [BO-3](../../../requirements/BO.md#bo-3) | Source-linked | 3.1 Business objectives |
| [BR-061](../../../requirements/BR.md#br-061) | Source-linked | 7.10 Online ordering for restaurants |
| [BRL-036](../../../requirements/BRL.md#brl-036) | Plan allocation / source cross-reference | 8. Business rules |
| [ORD-004](../../../requirements/ORD.md#ord-004) | Source-linked | 19.9 Online ordering and restaurant workflow (ORD) |
| [ORD-005](../../../requirements/ORD.md#ord-005) | Source-linked | 19.9 Online ordering and restaurant workflow (ORD) |
| [US-069](../../../requirements/US.md#us-069) | Source-linked | EP-14 Restaurant ordering |
| [US-070](../../../requirements/US.md#us-070) | Source-linked | EP-14 Restaurant ordering |
| [US-071](../../../requirements/US.md#us-071) | Source-linked | EP-14 Restaurant ordering |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-036](../../../requirements/BRL.md#brl-036): BRL-036 | A restaurant order is confirmed by reading it back and is accepted only when the restaurant's workflow has received it. Payment card numbers are never spoken to, or stored by, the AI; payment is at pickup or by a payment link. | Ordering | ORD-003, ORD-004, ORD-006.
- [ ] [ORD-004](../../../requirements/ORD.md#ord-004): ORD-004 [P2] MUST deliver orders to the restaurant reliably: a staff-accept dashboard on a tablet or screen with alerts, accept or decline with a preparation time, and reprint; cloud printing to receipt printers with bilingual kitchen tickets; and text or email fallback. Orders carry idempotent identifiers. An order not accepted within a set time triggers an escalation (a call or text to the restaurant and owner). No order may be lost or duplicated, including across network loss and reconnection.
- [ ] [ORD-005](../../../requirements/ORD.md#ord-005): ORD-005 [P2] SHOULD provide authorized point-of-sale connectors, granted by the restaurant: Square through OAuth and its ordering and catalog interfaces first; Toast, Clover, MenuSifu, Chowbus and others only after partner access, terms and certification are confirmed. Every connector has contract tests, and any failure falls back to ORD-004.

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

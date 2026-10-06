# EVN-ORD-062 - Bilingual ordering and tickets

Project: EverOnnAI. Module: [Restaurant menus, web/phone orders and kitchen delivery](../README.md). Source business requirement [BR-062](../../../requirements/BR.md#br-062).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Restaurant Product Owner + Integration Lead (proposed role; named person unassigned) |
| Priority / phase | Should / P2 English, P3 Mandarin and Cantonese |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-INB-101](../../08-inbox-contacts-booking-followup/tickets/EVN-INB-101.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md) |

## Business deliverable

Bilingual ordering and tickets. Ordering and kitchen tickets support the languages the restaurant's customers and staff use, starting with English and adding Mandarin and Cantonese after testing on real menus and audio.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Restaurant locale/pronunciation/bilingual printing models are absent.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Ship English first; gate Mandarin/Cantonese on real menu/audio/printer testing by source phase.

## Technical component

- [ ] Implement the module boundary and contracts for: Locale rendering and printer encoding.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: No menu/cart/order/payment/kitchen domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] menu_localisations, pronunciations, ticket_locales.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Bilingual menu/kitchen ticket preview.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Bilingual ordering and tickets. Ordering and kitchen tickets support the languages the restaurant's customers and staff use, starting with English and adding Mandarin and Cantonese after testing on real menus and audio. | Locale rendering and printer encoding | Tenant-scoped end-to-end demonstration of the outcome |
| Ship English first; gate Mandarin/Cantonese on real menu/audio/printer testing by source phase. | menu_localisations, pronunciations, ticket_locales; Bilingual menu/kitchen ticket preview | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Language-specific item recognition and read-back tests | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Locale rendering and printer encoding.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Language-specific item recognition and read-back tests.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-43](../../../requirements/AT.md#at-43) | Mandarin and Cantonese ordering with bilingual tickets | Test calls in each language on real menus meet the accuracy thresholds; kitchen tickets print bilingual names | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-071](../../../requirements/US.md#us-071), [US-072](../../../requirements/US.md#us-072).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-43](../../../requirements/AT.md#at-43) | Source-linked | 25.2 Acceptance tests |
| [BO-8](../../../requirements/BO.md#bo-8) | Source-linked | 3.1 Business objectives |
| [BR-062](../../../requirements/BR.md#br-062) | Source-linked | 7.10 Online ordering for restaurants |
| [BRL-036](../../../requirements/BRL.md#brl-036) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-037](../../../requirements/BRL.md#brl-037) | Plan allocation / source cross-reference | 8. Business rules |
| [ORD-001](../../../requirements/ORD.md#ord-001) | Source-linked | 19.9 Online ordering and restaurant workflow (ORD) |
| [ORD-003](../../../requirements/ORD.md#ord-003) | Source-linked | 19.9 Online ordering and restaurant workflow (ORD) |
| [ORD-004](../../../requirements/ORD.md#ord-004) | Source-linked | 19.9 Online ordering and restaurant workflow (ORD) |
| [US-071](../../../requirements/US.md#us-071) | Source-linked | EP-14 Restaurant ordering |
| [US-072](../../../requirements/US.md#us-072) | Source-linked | EP-14 Restaurant ordering |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-036](../../../requirements/BRL.md#brl-036): BRL-036 | A restaurant order is confirmed by reading it back and is accepted only when the restaurant's workflow has received it. Payment card numbers are never spoken to, or stored by, the AI; payment is at pickup or by a payment link. | Ordering | ORD-003, ORD-004, ORD-006.
- [ ] [BRL-037](../../../requirements/BRL.md#brl-037): BRL-037 | Allergy and dietary questions, and complaints, are transferred to restaurant staff; the AI never answers them. | Ordering | ORD-003.
- [ ] [ORD-001](../../../requirements/ORD.md#ord-001): ORD-001 [P2] MUST provide menu management: categories, items, sizes, item numbers, combination meals with included sides, modifier groups (spice level, protein, rice, sauce on the side), substitutions and upcharges, bilingual names with romanization and pronunciation hints, dietary and allergen information (displayed for reference only), hours by day and period, availability and sold-out switches, preparation-time rules and tax settings. Menus are versioned and can be imported from an existing site, a document or an incumbent export.
- [ ] [ORD-003](../../../requirements/ORD.md#ord-003): ORD-003 [P2] MUST provide AI phone ordering from the live menu: capture items and modifiers, accept item numbers ("number 23"), read back the whole order (items, modifiers, total, pickup time) and obtain confirmation before submitting; confirm the callback number; offer payment at pickup or a payment link by text; never take card numbers by voice; transfer allergy and dietary questions and complaints to staff and never answer them (BRL-037); ask or confirm when unsure and hand off to a person when it cannot resolve the request. English is required at P2; Mandarin and Cantonese follow at P3 after testing on real menus and audio.
- [ ] [ORD-004](../../../requirements/ORD.md#ord-004): ORD-004 [P2] MUST deliver orders to the restaurant reliably: a staff-accept dashboard on a tablet or screen with alerts, accept or decline with a preparation time, and reprint; cloud printing to receipt printers with bilingual kitchen tickets; and text or email fallback. Orders carry idempotent identifiers. An order not accepted within a set time triggers an escalation (a call or text to the restaurant and owner). No order may be lost or duplicated, including across network loss and reconnection.

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

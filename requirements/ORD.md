# ORD - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## ORD-001

Assigned delivery tickets: [EVN-ORD-059](../modules/14-restaurant-ordering/tickets/EVN-ORD-059.md), [EVN-ORD-062](../modules/14-restaurant-ordering/tickets/EVN-ORD-062.md).

**Primary source:** TECH section 19.9 Online ordering and restaurant workflow (ORD); extraction row 1237.

**Source record:** ORD-001 [P2] MUST provide menu management: categories, items, sizes, item numbers, combination meals with included sides, modifier groups (spice level, protein, rice, sauce on the side), substitutions and upcharges, bilingual names with romanization and pronunciation hints, dietary and allergen information (displayed for reference only), hours by day and period, availability and sold-out switches, preparation-time rules and tax settings. Menus are versioned and can be imported from an existing site, a document or an incumbent export.

## ORD-002

Assigned delivery tickets: [EVN-ORD-059](../modules/14-restaurant-ordering/tickets/EVN-ORD-059.md).

**Primary source:** TECH section 19.9 Online ordering and restaurant workflow (ORD); extraction row 1238.

**Source record:** ORD-002 [P2] MUST provide direct web ordering for pickup: mobile-first, pickup time estimates, totals with tax, a tip and fee policy the restaurant sets, guest checkout, payment at pickup or by card through a hosted payment page, confirmation and receipt, order status, and marketing consent kept separate from order confirmations.

## ORD-003

Assigned delivery tickets: [EVN-ORD-060](../modules/14-restaurant-ordering/tickets/EVN-ORD-060.md), [EVN-ORD-062](../modules/14-restaurant-ordering/tickets/EVN-ORD-062.md).

**Primary source:** TECH section 19.9 Online ordering and restaurant workflow (ORD); extraction row 1239.

**Source record:** ORD-003 [P2] MUST provide AI phone ordering from the live menu: capture items and modifiers, accept item numbers ("number 23"), read back the whole order (items, modifiers, total, pickup time) and obtain confirmation before submitting; confirm the callback number; offer payment at pickup or a payment link by text; never take card numbers by voice; transfer allergy and dietary questions and complaints to staff and never answer them (BRL-037); ask or confirm when unsure and hand off to a person when it cannot resolve the request. English is required at P2; Mandarin and Cantonese follow at P3 after testing on real menus and audio.

## ORD-004

Assigned delivery tickets: [EVN-ORD-061](../modules/14-restaurant-ordering/tickets/EVN-ORD-061.md), [EVN-ORD-062](../modules/14-restaurant-ordering/tickets/EVN-ORD-062.md).

**Primary source:** TECH section 19.9 Online ordering and restaurant workflow (ORD); extraction row 1240.

**Source record:** ORD-004 [P2] MUST deliver orders to the restaurant reliably: a staff-accept dashboard on a tablet or screen with alerts, accept or decline with a preparation time, and reprint; cloud printing to receipt printers with bilingual kitchen tickets; and text or email fallback. Orders carry idempotent identifiers. An order not accepted within a set time triggers an escalation (a call or text to the restaurant and owner). No order may be lost or duplicated, including across network loss and reconnection.

## ORD-005

Assigned delivery tickets: [EVN-ORD-061](../modules/14-restaurant-ordering/tickets/EVN-ORD-061.md).

**Primary source:** TECH section 19.9 Online ordering and restaurant workflow (ORD); extraction row 1241.

**Source record:** ORD-005 [P2] SHOULD provide authorized point-of-sale connectors, granted by the restaurant: Square through OAuth and its ordering and catalog interfaces first; Toast, Clover, MenuSifu, Chowbus and others only after partner access, terms and certification are confirmed. Every connector has contract tests, and any failure falls back to ORD-004.

## ORD-006

Assigned delivery tickets: [EVN-ORD-059](../modules/14-restaurant-ordering/tickets/EVN-ORD-059.md).

**Primary source:** TECH section 19.9 Online ordering and restaurant workflow (ORD); extraction row 1242.

**Source record:** ORD-006 [P2] MUST handle payments through a payment processor's hosted pages or links so that card data never touches EverOnn systems or recordings (SAQ A scope); funds settle to the restaurant's own merchant account; refunds, reconciliation and tax handling are supported.

## ORD-007

Assigned delivery tickets: [EVN-ORD-060](../modules/14-restaurant-ordering/tickets/EVN-ORD-060.md).

**Primary source:** TECH section 19.9 Online ordering and restaurant workflow (ORD); extraction row 1243.

**Source record:** ORD-007 [P2] MUST monitor order accuracy: sampled review of calls against tickets, item-level and modifier-level accuracy, failed or missed orders, handoff rate and correction rate, with thresholds that gate the three-restaurant pilot and each expansion.

## ORD-008

Assigned delivery tickets: [EVN-MIG-056](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md), [EVN-ORD-059](../modules/14-restaurant-ordering/tickets/EVN-ORD-059.md).

**Primary source:** TECH section 19.9 Online ordering and restaurant workflow (ORD); extraction row 1244.

**Source record:** ORD-008 [P2] SHOULD manage the restaurant's Google ordering and reservation links during migration, with the restaurant's authorization.

## ORD-009

Assigned delivery tickets: [EVN-ACQ-055](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-055.md), [EVN-BIL-040](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md), [EVN-ORD-059](../modules/14-restaurant-ordering/tickets/EVN-ORD-059.md).

**Primary source:** TECH section 19.9 Online ordering and restaurant workflow (ORD); extraction row 1245.

**Source record:** ORD-009 [P2] SHOULD support fee models that are a flat subscription plus usage by default, with optional per-order pricing, and integrate with the savings comparison for providers that charge a percentage of orders (ACQ-007).

## ORD-010

Assigned delivery tickets: [EVN-ORD-059](../modules/14-restaurant-ordering/tickets/EVN-ORD-059.md), [EVN-SEC-067](../modules/15-security-privacy-compliance/tickets/EVN-SEC-067.md).

**Primary source:** TECH section 19.9 Online ordering and restaurant workflow (ORD); extraction row 1246.

**Source record:** ORD-010 [P2] MUST give the restaurant its order and customer data for export, with marketing consent recorded per customer.

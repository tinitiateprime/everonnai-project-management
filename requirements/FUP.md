# FUP - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## FUP-001

Assigned delivery tickets: [EVN-INB-038](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-038.md).

**Primary source:** TECH section 17.2 Requirements; extraction row 1111.

**Source record:** FUP-001 [P2] MUST provide automated follow-up sequences (SMS/email): missed-call text-back, quote reminders, appointment reminders, post-job review requests, reactivation of stale leads. Sequences are templates with steps, delays, exit conditions, and per-contact suppression; all sends honor consent and quiet hours (COM-002).

## FUP-002

Assigned delivery tickets: [EVN-INB-038](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-038.md).

**Primary source:** TECH section 17.2 Requirements; extraction row 1112.

**Source record:** FUP-002 [P2] MUST support review generation: post-job SMS with a Google review link, with negative-sentiment gating that routes unhappy customers to the owner privately (subject to platform policy compliance; the studio MUST review Google's review-solicitation policies before shipping any gating).

## FUP-003

Assigned delivery tickets: [EVN-ANL-039](../modules/16-business-value-analytics/tickets/EVN-ANL-039.md).

**Primary source:** TECH section 17.2 Requirements; extraction row 1113.

**Source record:** FUP-003 [P2] SHOULD provide simple pipeline metrics (calls to requests to booked to done) and estimated recovered revenue with owner-editable average job values.

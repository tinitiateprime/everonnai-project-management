# BKG - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## BKG-001

Assigned delivery tickets: [EVN-INB-008](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-008.md).

**Primary source:** TECH section 17.2 Requirements; extraction row 1106.

**Source record:** BKG-001 [P1] MUST integrate calendars via OAuth (Google Calendar, Microsoft 365) and Cal.com; store only the minimum (free/busy plus created events), refresh tokens encrypted (SEC-005), and handle token revocation gracefully.

## BKG-002

Assigned delivery tickets: [EVN-INB-008](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-008.md).

**Primary source:** TECH section 17.2 Requirements; extraction row 1107.

**Source record:** BKG-002 [P1] MUST implement availability rules: business hours, service durations, buffers, travel-time estimates (P2), lead time, max per day, staff/technician assignment (P2), and holiday closures.

## BKG-003

Assigned delivery tickets: [EVN-INB-008](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-008.md).

**Primary source:** TECH section 17.2 Requirements; extraction row 1108.

**Source record:** BKG-003 [P1] MUST implement atomic booking with conflict detection (optimistic locking) so two simultaneous callers cannot book the same slot; the agent offers alternatives when a slot is taken.

## BKG-004

Assigned delivery tickets: [EVN-INB-008](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-008.md), [EVN-INB-038](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-038.md).

**Primary source:** TECH section 17.2 Requirements; extraction row 1109.

**Source record:** BKG-004 [P1] MUST send confirmations and reminders (SMS/email) with reschedule and cancel links; customer-initiated changes flow back to the calendar.

## BKG-005

Assigned delivery tickets: [EVN-INB-008](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-008.md), [EVN-INT-049](../modules/11-api-connectors-integrations/tickets/EVN-INT-049.md).

**Primary source:** TECH section 17.2 Requirements; extraction row 1110.

**Source record:** BKG-005 [P3] MAY integrate field-service systems (Jobber, Housecall Pro, ServiceTitan, Workiz) via an FsmProvider interface scaffolded at P2.

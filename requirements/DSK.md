# DSK - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## DSK-001

Assigned delivery tickets: [EVN-HIL-026](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-026.md).

**Primary source:** TECH section 16.4.1 Multi-client operations; extraction row 950.

**Source record:** DSK-001 [P1] MUST provide one unified queue across clients: pending and active voice offers, chats, SMS threads, callbacks, approvals and knowledge gaps for every client the operator is granted, each item showing the client name (with a brand color chip), line label, channel, severity, waiting time and service-level countdown, and language. Sort by severity then deadline; filter by client, channel, severity and language. An operator never sees items for clients they are not granted.

## DSK-002

Assigned delivery tickets: [EVN-HIL-026](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-026.md), [EVN-HIL-032](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-032.md).

**Primary source:** TECH section 16.4.1 Multi-client operations; extraction row 951.

**Source record:** DSK-002 [P1] MUST implement the client roster and grants: an operator is granted access per client (or per client group, vertical or brand) with skills, certification date and optional expiry. A grant is required both for routing to the operator and for seeing any client data. Granting requires the client-specific training checklist to be recorded as complete (BRL-019). Revocation takes effect within five seconds, including for interactions already open (the operator is moved out and the interaction re-routed). Every grant, change and revocation is audited.

## DSK-003

Assigned delivery tickets: [EVN-HIL-027](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md), [EVN-HIL-028](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md).

**Primary source:** TECH section 16.4.1 Multi-client operations; extraction row 952.

**Source record:** DSK-003 [P1] MUST perform line identification: each inbound leg is resolved to tenant_id and line_id from the dialed number and the carrier's signaling (the To, Diversion and History-Info headers and provider metadata), cross-checked against the number registry. The resolved line label (for example "Acme Locksmith, after-hours emergency line") travels with the escalation. If the line cannot be resolved with confidence (unknown number, ambiguous forwarding chain, inconsistent headers), the desk MUST show a prominent UNKNOWN LINE state, hide all client data, offer only a neutral greeting ("Thank you for calling, how can I help?"), and open a support incident. The system MUST NOT guess the client.

## DSK-004

Assigned delivery tickets: [EVN-HIL-027](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md).

**Primary source:** TECH section 16.4.2 Incoming interaction, screen-pop and greeting; extraction row 954.

**Source record:** DSK-004 [P1] MUST present a screen-pop offer card at the moment an interaction is offered, with no clicks needed to see who it is for:

- client name in large type on the client's brand color, line label and number, client status (open, closed, after hours), and the client's spoken-name pronunciation hint;

- the greeting to say, ready to read (DSK-006);

- caller number and name if known, returning-caller indicator, language;

- severity and why this interaction is with a human (the trigger);

- the AI summary so far, the details already captured (each with confidence and an "unconfirmed" marker) and a live transcript;

- waiting time and the accept and decline controls.

- The full context payload MUST be pushed to the desk before the offer rings, and the card MUST render within 500 ms of the offer at p95. The EverOnn brand under which the client is served appears as a small secondary tag (VRT-008).

## DSK-005

Assigned delivery tickets: [EVN-HIL-027](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md).

**Primary source:** TECH section 16.4.2 Incoming interaction, screen-pop and greeting; extraction row 962.

**Source record:** DSK-005 [P1] MUST support an operator-only announcement for voice: on acceptance, and before the caller is bridged, the operator hears a brief synthesized announcement naming the client and the situation ("Acme Locksmith. Car lockout. Caller Maria. Urgent."), inaudible to the caller. The caller meanwhile hears a short branded hold message ("One moment, I'm connecting you to a team member at Acme Locksmith"). The announcement is on by default for voice and configurable per operator and per client. The audio topology that keeps the announcement private is decided in the Phase 0 spike (§16.7.2).

## DSK-006

Assigned delivery tickets: [EVN-HIL-027](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md).

**Primary source:** TECH section 16.4.2 Incoming interaction, screen-pop and greeting; extraction row 963.

**Source record:** DSK-006 [P1] MUST manage greeting scripts per client: per language and per hours mode (business hours, after hours, callback), with variables {client_name}, {operator_first_name}, {line_label}, the spoken name and a phonetic hint, time-of-day variants, an outbound variant ("calling on behalf of {client_name}"), and a "do not say" list. Scripts are versioned and approved by the client (or by EverOnn operations on the client's behalf, recorded). The desk shows the script as copy-ready text with a one-key "greeting delivered" marker that is logged so greeting compliance can be measured. If no script exists, the default is a neutral greeting that includes the client name.

## DSK-007

Assigned delivery tickets: [EVN-HIL-027](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md).

**Primary source:** TECH section 16.4.3 Client context and authority; extraction row 965.

**Source record:** DSK-007 [P1] MUST provide a client context panel for the active interaction, with collapsible sections that all belong to that one client:

- Business: name, hours and current status, services, service area, pricing policy, payment methods;

- Instructions: owner notes, special handling, VIP list, blocked or disputed addresses;

- Contacts: who to notify or transfer to, on-call schedule, numbers masked with click-to-bridge;

- Caller history: earlier conversations, open requests and appointments;

- Availability: calendar slots for booking;

- Knowledge search: scoped to this client only;

- Playbook checklist: the slots to complete, prefilled from the AI's capture, editable and validated.

## DSK-008

Assigned delivery tickets: [EVN-HIL-029](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-029.md).

**Primary source:** TECH section 16.4.3 Client context and authority; extraction row 973.

**Source record:** DSK-008 [P1] MUST enforce the client's authority matrix: for each capability the client sets one of allowed, requires owner approval or not allowed (quote a price, commit an arrival time, book an appointment, dispatch a technician, take payment by link, cancel or reschedule, share technician details, grant an exception). The desk disables or annotates controls accordingly, routes approvals through HIL-007, and the server enforces the same rules. Changes are versioned and audited. Defaults are conservative.

## DSK-009

Assigned delivery tickets: [EVN-HIL-028](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md).

**Primary source:** TECH section 16.4.3 Client context and authority; extraction row 974.

**Source record:** DSK-009 [P1] MUST prevent client mix-ups through a client lock: each active interaction has exactly one client context, shown persistently in the header, in every panel, in the browser tab title and, for voice, in the operator-only announcement. When an operator has several interactions open, each is color- and name-coded, and switching shows a visible client-change confirmation. The desk never displays data of two clients in one panel, and the server rejects any action that would attach data from one client to another client's interaction. A one-tap "wrong client" control logs the event and re-routes. Wrong-client incidents (from the operator control, quality findings, or a caller correcting the greeting) are counted and alerted; the target is under 0.1% of interactions.

## DSK-010

Assigned delivery tickets: [EVN-HIL-028](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md).

**Primary source:** TECH section 16.4.3 Client context and authority; extraction row 975.

**Source record:** DSK-010 [P1] MUST apply data minimization and masking: the operator sees only fields the client has made visible to operators; sensitive tokens (card numbers, government identifiers) are masked; revealing a masked value requires a reason and is logged; bulk export or listing of contacts is not possible from the desk. A session watermark showing the operator id is a P2 option.

## DSK-011

Assigned delivery tickets: [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md), [EVN-HIL-036](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-036.md).

**Primary source:** TECH section 16.4.4 Handling the interaction; extraction row 977.

**Source record:** DSK-011 [P1] MUST provide a browser softphone: WebRTC audio through the media layer, device selection and test, echo cancellation and noise suppression, a network quality indicator, pre-shift diagnostics, automatic reconnection, and a telephone fallback (the platform calls the operator's registered number) if browser audio fails. USB headset call-control buttons via WebHID are P2.

## DSK-012

Assigned delivery tickets: [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md).

**Primary source:** TECH section 16.4.4 Handling the interaction; extraction row 978.

**Source record:** DSK-012 [P1] MUST provide voice call controls: accept; decline with a reason (returns to the queue); hold and resume with the client's hold audio; mute; warm transfer to the client's contacts with a whispered briefing; cold transfer; add a third party (the owner or a technician); hand back to the AI with an instruction; end; keypad; schedule a callback; send an SMS from client-approved templates; recording and consent indicator. Keyboard shortcuts for the common actions.

## DSK-013

Assigned delivery tickets: [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md).

**Primary source:** TECH section 16.4.4 Handling the interaction; extraction row 979.

**Source record:** DSK-013 [P1] MUST handle chat and SMS threads in the same queue and workspace: takeover and release, typing indicators, AI-drafted replies to approve, edit or send, client-specific canned replies, an attachment viewer for photos, and per-operator concurrency (default one voice interaction and up to three chat or SMS threads, configurable; chats are parked automatically when a voice interaction is accepted).

## DSK-014

Assigned delivery tickets: [EVN-HIL-026](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-026.md).

**Primary source:** TECH section 16.4.4 Handling the interaction; extraction row 980.

**Source record:** DSK-014 [P1] MUST manage presence and capacity: statuses (available, on a call, wrap-up, away, break, offline); capacity-based routing; automatic away after a configurable number of missed offers; shift start checks (microphone and network test, review of client notices); break approval by a lead at P2.

## DSK-015

Assigned delivery tickets: [EVN-AIQ-004](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-004.md), [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md).

**Primary source:** TECH section 16.4.4 Handling the interaction; extraction row 981.

**Source record:** DSK-015 [P2] SHOULD offer an operator copilot: live suggested questions, knowledge answers, summaries and draft messages under the same guardrails, clearly marked, never executed automatically, with operator feedback and measured effect on handling time and quality scores.

## DSK-016

Assigned delivery tickets: [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md).

**Primary source:** TECH section 16.4.4 Handling the interaction; extraction row 982.

**Source record:** DSK-016 [P1] MUST support callbacks and outbound calls from the desk only for interactions the caller or the client initiated: click-to-call showing the client's business number as caller ID, an outbound greeting script ("calling on behalf of {client_name}"), calling-hour and consent checks, and full logging. No cold outbound calling (COM-012).

## DSK-017

Assigned delivery tickets: [EVN-VOX-006](../modules/04-telephone-voice-language/tickets/EVN-VOX-006.md).

**Primary source:** TECH section 16.4.4 Handling the interaction; extraction row 983.

**Source record:** DSK-017 [P1] MUST handle language: the offer shows the caller's language; routing prefers operators skilled in it (English and Spanish at P1); the operator can switch language mid-conversation; an interpreter path is P3.

## DSK-018

Assigned delivery tickets: [EVN-HIL-026](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-026.md), [EVN-HIL-036](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-036.md).

**Primary source:** TECH section 16.4.5 Offers, routing behavior and wrap-up; extraction row 985.

**Source record:** DSK-018 [P1] MUST implement offer, ring and cascade behavior: offers expire after a configurable time (default 15 seconds); strategies include longest-idle and skills-first (ring-all-eligible at P2); the first acceptance wins through an atomic assignment; a decline or timeout moves to the next operator per the cascade; when no operator accepts within the service level the cascade continues (overflow pool, then the client's owner, then message capture with a promised callback and repeated alerts for emergencies). While the caller waits they hear branded hold messages, an offer to leave a message, and periodic updates. Every step is logged with timestamps.

## DSK-019

Assigned delivery tickets: [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md).

**Primary source:** TECH section 16.4.5 Offers, routing behavior and wrap-up; extraction row 986.

**Source record:** DSK-019 [P1] MUST require wrap-up: after the interaction the operator selects a disposition (resolved, message taken, transferred to owner, callback scheduled, spam, wrong number, other), corrects the structured request, adds notes visible to the client, sets a follow-up task and sends the client summary. Wrap-up has a timer (default 60 seconds, configurable) with automatic release; fields required per client are enforced; the operator cannot accept another voice offer until wrap-up is complete or the timer expires.

## DSK-020

Assigned delivery tickets: [EVN-HIL-031](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-031.md).

**Primary source:** TECH section 16.4.6 Supervision, staffing and visibility; extraction row 988.

**Source record:** DSK-020 [P2] MUST provide a supervisor wall board in real time by client, pool and operator: queue depth, longest wait, service-level status, abandon rate, operators by status, active interactions with client names, and alerts when a service level is at risk.

## DSK-021

Assigned delivery tickets: [EVN-HIL-031](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-031.md).

**Primary source:** TECH section 16.4.6 Supervision, staffing and visibility; extraction row 989.

**Source record:** DSK-021 [P2] MUST provide supervision tools: silent monitor, whisper to the operator, barge-in, take over, and reassign. All are logged, follow the applicable monitoring notice rules, and are restricted to operator_lead.

## DSK-022

Assigned delivery tickets: [EVN-HIL-032](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-032.md).

**Primary source:** TECH section 16.4.6 Supervision, staffing and visibility; extraction row 990.

**Source record:** DSK-022 [P2] MUST provide workforce and staffing tools: skills, shifts, forecast-based staffing suggestions (§16.7.5), adherence and break scheduling. Simple per-client coverage windows (the hours during which operators may take a client's calls) are P1.

## DSK-023

Assigned delivery tickets: [EVN-INB-035](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-035.md).

**Primary source:** TECH section 16.4.6 Supervision, staffing and visibility; extraction row 991.

**Source record:** DSK-023 [P1] MUST give clients visibility of human handling: interactions handled by an operator are flagged in the client's inbox ("Handled by the EverOnn team: Sam"), with duration, disposition, notes and recording per policy. The client can rate an interaction or report a problem, which feeds quality review.

## DSK-024

Assigned delivery tickets: [EVN-HIL-033](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-033.md).

**Primary source:** TECH section 16.4.6 Supervision, staffing and visibility; extraction row 992.

**Source record:** DSK-024 [P1] MUST record handling data: every offer, ring, acceptance, talk, hold, transfer, wrap-up and disposition is stored with timestamps. This feeds metering of operator minutes, quality sampling, service-level reporting and operator scorecards.

## DSK-025

Assigned delivery tickets: [EVN-QA-074](../modules/19-testing-client-acceptance/tickets/EVN-QA-074.md).

**Primary source:** TECH section 16.4.7 Ergonomics and resilience; extraction row 994.

**Source record:** DSK-025 [P1] SHOULD be keyboard-first and accessible: shortcuts for accept, hold, transfer and wrap-up; a large client banner; light and dark themes; pop-out panels for multiple monitors; screen-reader support; WCAG 2.1 AA; distinct audio cues by severity.

## DSK-026

Assigned delivery tickets: [EVN-HIL-036](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-036.md).

**Primary source:** TECH section 16.4.7 Ergonomics and resilience; extraction row 995.

**Source record:** DSK-026 [P1] MUST be resilient: the server is authoritative for interaction state. A desk reload or reconnect restores the exact state within three seconds and never drops a live call. Heartbeats detect operator disconnection within five seconds (the call returns to the queue or the AI resumes, per policy). A single active desk session per operator is enforced.

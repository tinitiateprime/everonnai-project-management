# CHT - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## CHT-001

Assigned delivery tickets: [EVN-CHT-011](../modules/05-chat-widget-sms/tickets/EVN-CHT-011.md), [EVN-CHT-101](../modules/05-chat-widget-sms/tickets/EVN-CHT-101.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 892.

**Source record:** CHT-001 [P1] MUST ship an embeddable widget (single script, under 40 KB gzipped, no third-party cookies, accessible WCAG 2.1 AA, keyboard and screen-reader friendly) with theming from the tenant's brand, mobile-first layout, and lazy loading so it never harms Core Web Vitals.

## CHT-002

Assigned delivery tickets: [EVN-CHT-101](../modules/05-chat-widget-sms/tickets/EVN-CHT-101.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 893.

**Source record:** CHT-002 [P1] MUST stream responses over SSE or WebSocket; first token within 1.5 s p50.

## CHT-003

Assigned delivery tickets: [EVN-CHT-011](../modules/05-chat-widget-sms/tickets/EVN-CHT-011.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 894.

**Source record:** CHT-003 [P1] MUST use the same agent brain, KB, playbook, tools and guardrails as voice (AGT-001), with channel-specific style (shorter, links, buttons).

## CHT-004

Assigned delivery tickets: [EVN-CHT-011](../modules/05-chat-widget-sms/tickets/EVN-CHT-011.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 895.

**Source record:** CHT-004 [P1] MUST support rich responses: quick-reply buttons, "Call us", "Text me", location capture (with permission), photo upload (for example a photo of a lock or a leak; virus-scanned, size-limited, stored per tenant), and a contact card.

## CHT-005

Assigned delivery tickets: [EVN-CHT-101](../modules/05-chat-widget-sms/tickets/EVN-CHT-101.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 896.

**Source record:** CHT-005 [P1] MUST capture consent for SMS follow-up in-widget with logged consent text, timestamp, IP and page (COM-002).

## CHT-006

Assigned delivery tickets: [EVN-CHT-101](../modules/05-chat-widget-sms/tickets/EVN-CHT-101.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 897.

**Source record:** CHT-006 [P1] MUST support visitor identity continuity: anonymous session ID, upgraded to a contact on lead capture; the same person across voice, chat and SMS resolves to one Contact via verified identifiers (phone, email) with merge rules and merge audit.

## CHT-007

Assigned delivery tickets: [EVN-CHT-101](../modules/05-chat-widget-sms/tickets/EVN-CHT-101.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 898.

**Source record:** CHT-007 [P1] MUST provide bot protection on the widget (Turnstile/hCaptcha or equivalent risk scoring), rate limits per IP and per session, and origin allow-listing per tenant (widget keys are public and MUST be scoped to allowed origins).

## CHT-008

Assigned delivery tickets: [EVN-CHT-011](../modules/05-chat-widget-sms/tickets/EVN-CHT-011.md), [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 899.

**Source record:** CHT-008 [P1] MUST support human takeover in chat (HIL-004): the operator or owner joins the same thread; the widget shows a subtle "a team member has joined" state.

## CHT-009

Assigned delivery tickets: [EVN-CHT-012](../modules/05-chat-widget-sms/tickets/EVN-CHT-012.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 900.

**Source record:** CHT-009 [P1] MUST support SMS threading (one thread per contact per business number), opt-out keywords (STOP/UNSUBSCRIBE/HELP) handling at the platform level, quiet hours (default 9 pm to 8 am recipient local time unless the message is a direct reply), and delivery-status tracking.

## CHT-010

Assigned delivery tickets: [EVN-CHT-101](../modules/05-chat-widget-sms/tickets/EVN-CHT-101.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 901.

**Source record:** CHT-010 [P2] SHOULD support proactive chat triggers (for example, after 20 seconds on the emergency service page) configured per tenant.

## CHT-011

Assigned delivery tickets: [EVN-CHT-011](../modules/05-chat-widget-sms/tickets/EVN-CHT-011.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 902.

**Source record:** CHT-011 [P1] MUST provide transcript and summary delivery with the same structured Request output as voice (AGT-008).

## CHT-012

Assigned delivery tickets: [EVN-CHT-101](../modules/05-chat-widget-sms/tickets/EVN-CHT-101.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 903.

**Source record:** CHT-012 [P2] SHOULD support multilingual chat with automatic language detection.

## CHT-013

Assigned delivery tickets: [EVN-CHT-101](../modules/05-chat-widget-sms/tickets/EVN-CHT-101.md).

**Primary source:** TECH section 15.2 Requirements; extraction row 904.

**Source record:** CHT-013 [P1] MUST implement an AI disclosure in chat ("You're chatting with the business's AI assistant") that is visible at the start of the conversation.

# HIL - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## HIL-001

Assigned delivery tickets: [EVN-HIL-025](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-025.md).

**Primary source:** TECH section 16.3 Escalation, routing and service levels (HIL); extraction row 933.

**Source record:** HIL-001 [P1] MUST model Escalation with: id, tenant_id, conversation_id, trigger_code, severity (p1..p4), state, created_at, sla_due_at, assigned_to, mode (A/B/C), context_snapshot, resolution_code, resolution_notes, audit.

## HIL-002

Assigned delivery tickets: [EVN-HIL-025](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-025.md), [EVN-VOX-005](../modules/04-telephone-voice-language/tickets/EVN-VOX-005.md).

**Primary source:** TECH section 16.3 Escalation, routing and service levels (HIL); extraction row 934.

**Source record:** HIL-002 [P1] MUST implement severity-based SLAs and cascades (values configurable, defaults below):

## HIL-003

Assigned delivery tickets: [EVN-HIL-024](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md).

**Primary source:** TECH section 16.3 Escalation, routing and service levels (HIL); extraction row 940.

**Source record:** HIL-003 [P1] MUST guarantee that "I want a person" always produces an outcome: a live transfer if a human is reachable, otherwise a promise-and-capture with a scheduled callback task and SLA. The caller MUST never be trapped in an AI loop.

## HIL-004

Assigned delivery tickets: [EVN-HIL-024](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md).

**Primary source:** TECH section 16.3 Escalation, routing and service levels (HIL); extraction row 941.

**Source record:** HIL-004 [P1] MUST support live takeover: a human can join or take over an active chat immediately; for voice, via warm transfer or conference join (listen, whisper to AI, or take over). The AI receives the human's instruction as a privileged context message ("operator whisper") and can continue under supervision.

## HIL-005

Assigned delivery tickets: [EVN-HIL-026](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-026.md).

**Primary source:** TECH section 16.3 Escalation, routing and service levels (HIL); extraction row 942.

**Source record:** HIL-005 [P1] MUST perform all human handling of voice, chat and SMS escalations through the Live Agent Desk (§16.4), so that client identification, data masking, authority checks, audit, metering and quality review always apply. Operators MUST NOT handle client interactions through personal phones, email or shared inboxes, except the documented telephone fallback in DSK-011.

## HIL-006

Assigned delivery tickets: [EVN-HIL-032](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-032.md).

**Primary source:** TECH section 16.3 Escalation, routing and service levels (HIL); extraction row 943.

**Source record:** HIL-006 [P1] MUST implement routing and workforce management (simple skills-based routing at P1, full workforce management at P2): skills (language, vertical), shifts and availability, load balancing, priority pre-emption for P1, overflow to secondary pools, fair distribution, and "follow-the-sun" pools. Interfaces are scaffolded in P1: EscalationRouter, OperatorDirectory, ShiftCalendar.

## HIL-007

Assigned delivery tickets: [EVN-HIL-029](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-029.md), [EVN-HIL-034](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-034.md).

**Primary source:** TECH section 16.3 Escalation, routing and service levels (HIL); extraction row 944.

**Source record:** HIL-007 [P1] MUST implement approval workflows for sensitive actions that the AI drafts but must not execute alone (per tenant policy): sending a price, confirming a dispatch ETA, issuing a refund credit, sending a bulk message, modifying an existing appointment. Approvers can be owner, staff or operator; approvals are logged.

## HIL-008

Assigned delivery tickets: [EVN-KNW-023](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-023.md).

**Primary source:** TECH section 16.5 Quality, learning and control of the human layer; extraction row 997.

**Source record:** HIL-008 [P1] MUST support post-conversation review by the owner: thumbs up/down, "correct this answer", "add to knowledge", "never say this". Owner corrections create KB proposals (KNW-005) and eval cases (§24.5).

## HIL-009

Assigned delivery tickets: [EVN-HIL-033](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-033.md).

**Primary source:** TECH section 16.5 Quality, learning and control of the human layer; extraction row 998.

**Source record:** HIL-009 [P2] MUST implement QA sampling and scoring: automatic risk-weighted sampling (guardrail hits, low confidence, escalations, new tenants first, random baseline 2%), reviewer UI with rubric (accuracy, safety, tone, outcome), reviewer agreement tracking, and score trends per tenant, per agent version and per vertical.

## HIL-010

Assigned delivery tickets: [EVN-HIL-033](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-033.md).

**Primary source:** TECH section 16.5 Quality, learning and control of the human layer; extraction row 999.

**Source record:** HIL-010 [P2] MUST close the learning loop: operator resolutions and QA findings produce (a) KB/profile suggestions, (b) playbook or prompt change candidates, (c) new regression cases added to the eval set with reviewer approval. Nothing changes production behavior without passing the eval gate (§24.5).

## HIL-011

Assigned delivery tickets: [EVN-HIL-033](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-033.md).

**Primary source:** TECH section 16.5 Quality, learning and control of the human layer; extraction row 1000.

**Source record:** HIL-011 [P1] MUST record every human intervention with actor, time, action, and before/after state in the immutable audit log (SEC-009).

## HIL-012

Assigned delivery tickets: [EVN-BIL-041](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-041.md), [EVN-HIL-033](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-033.md).

**Primary source:** TECH section 16.5 Quality, learning and control of the human layer; extraction row 1001.

**Source record:** HIL-012 [P2] MUST support billing and metering of HITL: minutes of live takeover, callbacks completed, reviews performed, per plan allowances and overage (BIL-004).

## HIL-013

Assigned delivery tickets: [EVN-HIL-028](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md), [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 16.5 Quality, learning and control of the human layer; extraction row 1002.

**Source record:** HIL-013 [P1] MUST apply operator security controls (minimum set at P1, full set at P2): least-privilege access (only assigned tenants and only the fields needed), MFA, device posture checks, session recording of console actions (not customer audio beyond policy), NDA/training attestation tracking, IP allow-listing for pooled operators, and automatic access expiry at shift end. Operators MUST NOT be able to export bulk data.

## HIL-014

Assigned delivery tickets: [EVN-HIL-032](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-032.md), [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md).

**Primary source:** TECH section 16.5 Quality, learning and control of the human layer; extraction row 1003.

**Source record:** HIL-014 [P2] SHOULD support partner/BPO operator pools as external tenants of the console with strict data segmentation, SLAs and per-partner reporting (scaffold identity model for external operator orgs in P1).

## HIL-015

Assigned delivery tickets: [EVN-HIL-025](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-025.md).

**Primary source:** TECH section 16.3 Escalation, routing and service levels (HIL); extraction row 945.

**Source record:** HIL-015 [P1] MUST provide owner notification preferences for escalations (push, SMS, call, email), quiet hours override for P1 severity, and acknowledgement tracking.

## HIL-016

Assigned delivery tickets: [EVN-HIL-024](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md), [EVN-HIL-036](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-036.md).

**Primary source:** TECH section 16.3 Escalation, routing and service levels (HIL); extraction row 946.

**Source record:** HIL-016 [P1] SHOULD provide degraded-operator mode: if no human is available within SLA, the system falls back to the safest path (take detailed message, callback task, and clear promise to the caller), and alerts the on-call lead.

## HIL-017

Assigned delivery tickets: [EVN-HIL-027](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md).

**Primary source:** TECH section 16.3 Escalation, routing and service levels (HIL); extraction row 947.

**Source record:** HIL-017 [P1] MUST carry client identity through every step: every escalation, offer, interaction, note and audit record holds tenant_id and line_id (or channel endpoint id), and no desk screen or API response may present interaction data without them.

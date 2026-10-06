# AGT - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## AGT-001

Assigned delivery tickets: [EVN-KNW-102](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-102.md).

**Primary source:** TECH section 13.3 Agent configuration; extraction row 792.

**Source record:** AGT-001 [P1] MUST model an agent as: {id, tenant_id, channel_set, persona, language_set, profile_version, kb_version, policy_set_version, tool_set, escalation_rules, business_hours_mode, voice_config, model_routing, created/updated, status}. A tenant has at least one agent; multi-location or multi-line tenants MAY have several.

## AGT-002

Assigned delivery tickets: [EVN-AIQ-104](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-104.md).

**Primary source:** TECH section 13.3 Agent configuration; extraction row 793.

**Source record:** AGT-002 [P1] MUST implement layered prompt assembly (highest to lowest authority; lower layers cannot override higher ones):

- 1.  Platform policy (EverOnn-owned; safety, legal, disclosure, prompt-injection defense, tool-use rules)

- 2.  Vertical playbook (trade-specific intake and triage logic)

- 3.  Tenant configuration (profile, tone, rules, escalation preferences)

- 4.  Retrieved knowledge (RAG chunks, clearly delimited as untrusted reference data)

- 5.  Conversation and caller context (caller ID, prior history, time, open jobs)

- All layers are versioned templates; the final assembled prompt for every turn is stored (redacted per COM-007) for debugging and eval replay.

## AGT-003

Assigned delivery tickets: [EVN-HIL-025](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-025.md), [EVN-KNW-021](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-021.md).

**Primary source:** TECH section 13.3 Agent configuration; extraction row 800.

**Source record:** AGT-003 [P1] MUST give owners no-code controls: greeting text, tone slider, "what to say when you can't answer", escalation preferences (who to call, when, in what order), hours-based behavior (business hours vs after hours), pricing policy, "never say" list, transfer numbers, spam-call handling.

## AGT-004

Assigned delivery tickets: [EVN-AIQ-076](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-076.md), [EVN-KNW-021](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-021.md), [EVN-KNW-102](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-102.md).

**Primary source:** TECH section 13.3 Agent configuration; extraction row 801.

**Source record:** AGT-004 [P1] MUST support draft → test → publish → rollback for every agent configuration change with a version history and one-click rollback.

## AGT-005

Assigned delivery tickets: [EVN-KNW-102](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-102.md).

**Primary source:** TECH section 13.3 Agent configuration; extraction row 802.

**Source record:** AGT-005 [P2] SHOULD support A/B variants (greeting, script) with outcome metrics, run per tenant with the owner's consent.

## AGT-006

Assigned delivery tickets: [EVN-AIQ-101](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-101.md).

**Primary source:** TECH section 13.3 Agent configuration; extraction row 803.

**Source record:** AGT-006 [P1] MUST include model routing configuration per agent and per task (voice turn, chat turn, summarization, extraction, QA judge) resolved through the model gateway (§20.3); tenants never choose raw model names, only quality tiers.

## AGT-007

Assigned delivery tickets: [EVN-AIQ-102](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-102.md).

**Primary source:** TECH section 13.3 Agent configuration; extraction row 804.

**Source record:** AGT-007 [P1] MUST define a tool registry (Appendix B). Tools have JSON-Schema-typed inputs and outputs, per-tenant enablement, per-plan entitlement, timeouts, retries and idempotency keys. Tool results are treated as untrusted data by the model.

## AGT-008

Assigned delivery tickets: [EVN-AIQ-102](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-102.md), [EVN-INB-101](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-101.md), [EVN-VOX-002](../modules/04-telephone-voice-language/tickets/EVN-VOX-002.md).

**Primary source:** TECH section 13.3 Agent configuration; extraction row 805.

**Source record:** AGT-008 [P1] MUST implement structured extraction: at the end of every conversation, produce a schema-validated Request object (Appendix D) from the transcript and tool results, with per-field confidence and evidence spans. Downstream systems consume the structured object, never free text.

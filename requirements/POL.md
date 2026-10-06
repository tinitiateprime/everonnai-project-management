# POL - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## POL-001

Assigned delivery tickets: [EVN-AIQ-004](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-004.md), [EVN-AIQ-102](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-102.md), [EVN-AIQ-104](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-104.md).

**Primary source:** TECH section 13.4 Guardrails and policy engine; extraction row 807.

**Source record:** POL-001 [P1] MUST enforce guardrails in two places: in the prompt (soft) and in code (hard): output filters and tool-call validators the model cannot bypass. Hard rules include: no price quote unless the pricing policy and KB explicitly allow it; no promise of arrival time unless dispatch data supports it; no medical/legal/financial advice; no collection of full card numbers or SSNs; no disclosure of other customers' information; no impersonating a human when sincerely asked whether it is an AI (COM-003).

## POL-002

Assigned delivery tickets: [EVN-VOX-005](../modules/04-telephone-voice-language/tickets/EVN-VOX-005.md).

**Primary source:** TECH section 13.4 Guardrails and policy engine; extraction row 808.

**Source record:** POL-002 [P1] MUST implement emergency and safety triage per vertical: gas smell, fire, carbon monoxide, medical emergency, child locked in car, and threats. The agent MUST advise contacting emergency services where appropriate, and immediately escalate (HIL-002) to the owner or operator with highest priority. The trigger phrases and actions are configured in vertical templates and covered by the eval set.

## POL-003

Assigned delivery tickets: [EVN-AIQ-004](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-004.md), [EVN-AIQ-102](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-102.md).

**Primary source:** TECH section 13.4 Guardrails and policy engine; extraction row 809.

**Source record:** POL-003 [P1] MUST defend against prompt injection and jailbreaks from callers, website visitors, ingested web content and tool results: separate system and untrusted content channels, strip or neutralize instructions in retrieved/ingested text, restrict tools by allow-list, validate tool arguments server-side, and never let model output execute arbitrary code or URLs. Include an adversarial test suite in CI (§24.5).

## POL-004

Assigned delivery tickets: [EVN-AIQ-102](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-102.md).

**Primary source:** TECH section 13.4 Guardrails and policy engine; extraction row 810.

**Source record:** POL-004 [P1] MUST detect and handle abuse, harassment, threats, and spam or robocalls (configurable: hang up politely, take message, block number). Repeated abusive numbers go to a tenant-scoped, then platform-scoped, block list.

## POL-005

Assigned delivery tickets: [EVN-AIQ-102](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-102.md).

**Primary source:** TECH section 13.4 Guardrails and policy engine; extraction row 811.

**Source record:** POL-005 [P1] MUST apply PII minimization: collect only what the playbook requires; mask sensitive tokens (card, SSN, DOB) in transcripts and logs; refuse to store payment card data (route to a payment link instead).

## POL-006

Assigned delivery tickets: [EVN-AIQ-102](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-102.md).

**Primary source:** TECH section 13.4 Guardrails and policy engine; extraction row 812.

**Source record:** POL-006 [P1] MUST log every guardrail intervention with a code, so quality dashboards and QA sampling can target them.

# 04. Telephone numbers, voice service and bilingual calls

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `VOX`. Proposed accountable roles: Voice/Media Lead + SRE; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-VOX-001](tickets/EVN-VOX-001.md) | Answer every call | Planned | P1 |
| [EVN-VOX-002](tickets/EVN-VOX-002.md) | Capture the job accurately | Partial | P1 |
| [EVN-VOX-003](tickets/EVN-VOX-003.md) | Natural, responsive conversation | Partial | P1 |
| [EVN-VOX-005](tickets/EVN-VOX-005.md) | Emergency handling | Partial | P1 |
| [EVN-VOX-006](tickets/EVN-VOX-006.md) | English and Spanish | Planned | P1 |
| [EVN-VOX-009](tickets/EVN-VOX-009.md) | Keep existing numbers | Planned | P1 |
| [EVN-VOX-101](tickets/EVN-VOX-101.md) | Prove a real telephone call can meet quality, latency and cost targets | Planned | P0 |

## Current project capability

**EVN-VOX-001:** Browser voice sessions and approved business context exist.

**EVN-VOX-002:** Contact extraction, progressive lead capture and deterministic service/date/time validation exist.

**EVN-VOX-003:** ElevenLabs browser voice uses signed sessions.

**EVN-VOX-005:** Text-path gas/carbon-monoxide safety replies bypass routine generation.

**EVN-VOX-006:** The current voice context explicitly selects English.

**EVN-VOX-009:** A transfer-number business field exists; carrier number management does not.

**EVN-VOX-101:** Browser voice is available; no source-compliant SIP/PSTN spike evidence exists.

Current persistence: conversations, conversation_messages, contacts, leads; browser voice usage sessions. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 60 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-AIQ-101](../03-ai-governance-evaluation/tickets/EVN-AIQ-101.md), [EVN-FND-101](../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-KNW-102](../02-knowledge-agent-configuration/tickets/EVN-KNW-102.md).

## Existing code and verification

- `app/api/voice/session/route.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `app/api/site-assistant/session/route.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/voice-agent/session-context.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/voice-agent/session-prompt.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/voice-agent/engine.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `components/preview/website-assistant.tsx` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/lead-automation.test.ts`, `tests/product-core.test.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

Browser ElevenLabs sessions do not establish real PSTN numbers, two carriers, warm transfers, Spanish coverage or 24/7 answering.

## Module completion gate

- [ ] Ticket scope, priority and accountable people agreed.
- [ ] Business outcomes demonstrated with authorised tenant data.
- [ ] Applicable source requirements and acceptance scenarios passed with evidence.
- [ ] Database, contracts, role boundaries and failure handling reviewed.
- [ ] AI quality/safety and provider cost validated where applicable.
- [ ] UI accessibility and responsive behaviour reviewed.
- [ ] Hosted rollout, monitoring, recovery and operational ownership verified.
- [ ] Client signs the released version; deferred items have explicit written disposition.

An implemented slice or a passing unit suite does not close this module. See [current status](../../CURRENT_STATE.md) and [the phase plan](../../DELIVERY_PLAN.md).

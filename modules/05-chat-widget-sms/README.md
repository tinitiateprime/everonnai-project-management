# 05. Customer chat, external widget and SMS

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `CHT`. Proposed accountable roles: Frontend Lead + Channel Integration Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-CHT-011](tickets/EVN-CHT-011.md) | Website chat | Partial | P1 |
| [EVN-CHT-012](tickets/EVN-CHT-012.md) | Texting and text-back | Planned | P1 |
| [EVN-CHT-101](tickets/EVN-CHT-101.md) | Let any authorised customer website embed a fast accessible assistant | Partial | P1 |

## Current project capability

**EVN-CHT-011:** Generated sites have approved-facts assistance with ElevenLabs text and Gemini fallback.

**EVN-CHT-012:** No two-way SMS transport or STOP ledger is implemented.

**EVN-CHT-101:** The current assistant is embedded in generated EverOnn sites.

Current persistence: conversations, messages, contacts, leads and scoped visitor/provider sessions. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 29 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-AIQ-102](../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md), [EVN-ONB-102](../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md).

## Existing code and verification

- `app/api/assistant/message/route.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `app/api/site-assistant/session/route.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `app/api/site-assistant/lead/route.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `components/preview/website-assistant.tsx` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/voice-agent/capture-client.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/lead-automation.test.ts`, `tests/product-core.test.ts`, `scripts/smoke-hvac.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

Current in-site chat is not a standalone sub-40 KB widget, two-way SMS, consent ledger or human takeover.

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

# 03. AI runtime, skills, provider portability and evaluation

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `AIQ`. Proposed accountable roles: AI Lead + QA Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-AIQ-004](tickets/EVN-AIQ-004.md) | Truthful and safe AI | Partial | P1 |
| [EVN-AIQ-076](tickets/EVN-AIQ-076.md) | Safe AI change control | Partial | P1 |
| [EVN-AIQ-101](tickets/EVN-AIQ-101.md) | Make provider selection portable and measurable | Partial | P0 |
| [EVN-AIQ-102](tickets/EVN-AIQ-102.md) | Allow AI actions only through verified business contracts | Partial | P0 foundation / P1 completion |
| [EVN-AIQ-103](tickets/EVN-AIQ-103.md) | Make AI changes pass a repeatable quality and safety gate | Partial | P0 |
| [EVN-AIQ-104](tickets/EVN-AIQ-104.md) | Give each service a governed skill and approved memory policy | Partial | P1 |

## Current project capability

**EVN-AIQ-004:** Approved knowledge composition, HVAC safety rules, no-false-booking checks and output grounding guards exist.

**EVN-AIQ-076:** Versioned Markdown/digests, guarded tools and website rollback exist.

**EVN-AIQ-101:** Gemini generation and ElevenLabs sessions use scoped application services.

**EVN-AIQ-102:** Booking/capture endpoints validate explicit details and actual provider results.

**EVN-AIQ-103:** Unit tests, skill digests and EVALS Markdown exist.

**EVN-AIQ-104:** Shared/HVAC Markdown and scoped website preferences with 20 requests are implemented.

Current persistence: Skill version/digest traces, generation metadata, scoped preferences and usage records. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 47 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-FND-101](../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-KNW-102](../02-knowledge-agent-configuration/tickets/EVN-KNW-102.md).

## Existing code and verification

- `ai/SYSTEM.md` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `ai/GUARDRAILS.md` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `ai/domains/hvac/SKILL.md` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `ai/domains/hvac/GUARDRAILS.md` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `ai/capabilities/website-building/SKILL.md` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/agent-runtime/tool-registry.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/agent-runtime/safety.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/voice-agent/gemini.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `lib/provider-config.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/agent-runtime.test.ts`, `tests/website-ai.test.ts`, `tests/website-code.test.ts`, `tests/provider-config.test.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

Deterministic mocks and EVALS Markdown do not prove live-model accuracy, audio latency or the required 150/500 scenario launch datasets.

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

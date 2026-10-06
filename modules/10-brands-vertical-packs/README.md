# 10. Vertical brands, packs, readiness and capability parity

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `VRT`. Proposed accountable roles: Vertical Manager + Product Owner + Counsel; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-VRT-044](tickets/EVN-VRT-044.md) | One suite, many vertical brands | Planned | P1 |
| [EVN-VRT-045](tickets/EVN-VRT-045.md) | Brands are kept apart | Planned | P1 |
| [EVN-VRT-046](tickets/EVN-VRT-046.md) | Launch a vertical by configuration | Partial | P1 |
| [EVN-VRT-047](tickets/EVN-VRT-047.md) | Vertical readiness gate | Planned | P1 |
| [EVN-VRT-048](tickets/EVN-VRT-048.md) | Match what customers already rely on | Planned | P1 first packs; later by wave |

## Current project capability

**EVN-VRT-044:** One product brand and selected HVAC skill pack exist.

**EVN-VRT-045:** Tenant isolation exists; brand context and legal/sender separation do not.

**EVN-VRT-046:** Versioned shared/capability/HVAC Markdown uses an allowlisted registry.

**EVN-VRT-047:** Eval Markdown is not a named-approver launch gate.

**EVN-VRT-048:** Service pages exist; complete vertical parity products/connectors do not.

Current persistence: Explicit skillId/domain selection and generation skill traces; no first-class brand/pack governance tables. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 41 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-AIQ-104](../03-ai-governance-evaluation/tickets/EVN-AIQ-104.md), [EVN-ONB-102](../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md).

## Existing code and verification

- `features/agent-runtime/skill-registry.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/agent-runtime/skill-loader.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `ai/domains/hvac/SKILL.md` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `ai/domains/hvac/EVALS.md` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `ai/domains/hvac/SOURCES.md` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/agent-runtime.test.ts`, `scripts/smoke-hvac.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

One HVAC pack is not two live brands/packs, configuration-only launch, vertical parity or legal/expert/operator readiness approval.

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

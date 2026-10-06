# 02. Knowledge, agent configuration and approved business memory

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `KNW`. Proposed accountable roles: AI Lead + Backend Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-KNW-020](tickets/EVN-KNW-020.md) | Approve what the AI knows | Partial | P1 |
| [EVN-KNW-021](tickets/EVN-KNW-021.md) | Self-service configuration | Partial | P1 |
| [EVN-KNW-023](tickets/EVN-KNW-023.md) | Explain and correct | Partial | P1 |
| [EVN-KNW-101](tickets/EVN-KNW-101.md) | Make approved business documents usable by the assistant | Partial | P1 |
| [EVN-KNW-102](tickets/EVN-KNW-102.md) | Keep agent behaviour stable while owners edit business knowledge | Partial | P1 |

## Current project capability

**EVN-KNW-020:** Owners maintain facts, services and approved FAQs; unapproved knowledge is excluded from prompts.

**EVN-KNW-021:** Business settings save; website preferences/history and website release rollback exist.

**EVN-KNW-023:** Generation records skill versions and approved website change requests.

**EVN-KNW-101:** Approved structured FAQs are composed into prompts.

**EVN-KNW-102:** The existing profile saves and website snapshots preserve live website facts.

Current persistence: business_profiles, business_services, knowledge_items; scoped website aiMemory in workspace payload. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 34 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-FND-101](../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md).

## Existing code and verification

- `features/everonn/types.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/agent-runtime/prompt-composer.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/agent-runtime/memory.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/agent-runtime/skill-loader.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `app/api/agent-runtime/memory/route.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `components/dashboard/website-design-editor.tsx` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/agent-runtime.test.ts`, `tests/json-workspace.test.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

Structured FAQs and website memory are not document RAG, immutable published KB/agent versions or assistant long-term memory.

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

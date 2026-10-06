# 06. AI website generation, editing, publishing and domains

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `WEB`. Proposed accountable roles: Frontend Lead + AI Lead + Platform Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-WEB-013](tickets/EVN-WEB-013.md) | Chat, call and forms on every site | Partial | P1 |
| [EVN-WEB-014](tickets/EVN-WEB-014.md) | Private preview in minutes | Partial | P1 |
| [EVN-WEB-016](tickets/EVN-WEB-016.md) | Custom domains | Planned | P1 |
| [EVN-WEB-017](tickets/EVN-WEB-017.md) | Search and AI-search ready | Partial | P1 |
| [EVN-WEB-018](tickets/EVN-WEB-018.md) | 1,000 sites per day | Planned | P2 |
| [EVN-WEB-019](tickets/EVN-WEB-019.md) | Prevent fake or abusive sites | Partial | P1 |
| [EVN-WEB-101](tickets/EVN-WEB-101.md) | Preserve website work across timeouts and host restarts | Partial | P1 |
| [EVN-WEB-102](tickets/EVN-WEB-102.md) | Approve a premium service-specific website before replacing the saved live site | Partial | P1 |
| [EVN-WEB-103](tickets/EVN-WEB-103.md) | Serve tenant websites with isolated domains, immutable assets and fast recovery | Planned | P1 |

## Current project capability

**EVN-WEB-013:** Generated pages connect request forms, assistant controls and approved telephone links.

**EVN-WEB-014:** Gemini writes multi-page HTML/CSS with private previews, bounded repairs and streamed progress.

**EVN-WEB-016:** Sites publish on application paths; a custom-domain lifecycle is absent.

**EVN-WEB-017:** Generated pages have metadata and service-specific routes.

**EVN-WEB-018:** Generation runs in one request with up to three concurrent concept calls.

**EVN-WEB-019:** Validation rejects unsafe execution, unsupported routes/assets and invented business claims.

**EVN-WEB-101:** Small batches, fallbacks, repairs and NDJSON progress are implemented.

**EVN-WEB-102:** New generation is original HTML/CSS; saved older publications retain a compatibility renderer.

**EVN-WEB-103:** Application-path publishing is implemented.

Current persistence: website_projects and immutable draft/live release snapshots in scoped workspace records. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 50 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-AIQ-101](../03-ai-governance-evaluation/tickets/EVN-AIQ-101.md), [EVN-AIQ-104](../03-ai-governance-evaluation/tickets/EVN-AIQ-104.md), [EVN-FND-101](../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-OPS-101](../18-reliability-deployment-scale/tickets/EVN-OPS-101.md).

## Existing code and verification

- `features/website-studio/ai-generator.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/website-studio/code-generator.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/website-studio/code-validation.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/website-studio/progress.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/website-studio/releases.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/website-studio/media.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `app/api/website-studio/route.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `app/api/website-studio/status/route.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `components/preview/website-page.tsx` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `components/preview/legacy-website-preview.tsx` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/website-ai.test.ts`, `tests/website-code.test.ts`, `tests/website-media.test.ts`, `scripts/smoke-hvac.ts`, `scripts/verify-website-live.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

Synchronous generation can exceed host limits; premium visuals, ownership verification, domains/TLS and scale are not established by parser tests.

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

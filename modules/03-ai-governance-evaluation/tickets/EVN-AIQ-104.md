# EVN-AIQ-104 - Give each service a governed skill and approved memory policy

Project: EverOnnAI. Module: [AI runtime, skills, provider portability and evaluation](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | AI Lead + QA Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-KNW-102](../../02-knowledge-agent-configuration/tickets/EVN-KNW-102.md), [EVN-AIQ-103](EVN-AIQ-103.md) |

## Business deliverable

Give each service a governed skill and approved memory policy.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Shared/HVAC Markdown and scoped website preferences with 20 requests are implemented.

## Remaining delivery checklist

- [ ] Strengthen design/intake standards, document ai/MEMORY.md, define assistant memory retention/approval and implement additional packs after review.

## Technical component

- [ ] Implement the module boundary and contracts for: Allowlisted composer, memory resolver and change review.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Skill version/digest traces, generation metadata, scoped preferences and usage records.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] skill_registry, memory scopes, immutable instruction versions.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Approved preferences and skill/version visibility.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Give each service a governed skill and approved memory policy. | Allowlisted composer, memory resolver and change review | Tenant-scoped end-to-end demonstration of the outcome |
| Strengthen design/intake standards, document ai/MEMORY.md, define assistant memory retention/approval and implement additional packs after review. | skill_registry, memory scopes, immutable instruction versions; Approved preferences and skill/version visibility | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Service-specific skills; memory cannot override safety/facts or leak across tenants | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Allowlisted composer, memory resolver and change review.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Service-specific skills.
- [ ] memory cannot override safety/facts or leak across tenants.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

No dedicated source AT is assigned to this enabling/extension ticket. Define a ticket-specific acceptance report before closing it; the module and release gates still apply.

Source stories: No dedicated source story; business/enabling outcome above is the acceptance brief.

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AGT-002](../../../requirements/AGT.md#agt-002) | Source-linked | 13.3 Agent configuration |
| [BRL-001](../../../requirements/BRL.md#brl-001) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-002](../../../requirements/BRL.md#brl-002) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-003](../../../requirements/BRL.md#brl-003) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-035](../../../requirements/BRL.md#brl-035) | Plan allocation / source cross-reference | 8. Business rules |
| [KNW-002](../../../requirements/KNW.md#knw-002) | Source-linked | 13.1 Business profile (structured facts) |
| [POL-001](../../../requirements/POL.md#pol-001) | Source-linked | 13.4 Guardrails and policy engine |
| [VRT-003](../../../requirements/VRT.md#vrt-003) | Source-linked | 19.6 Brands and vertical packs (VRT) |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [AGT-002](../../../requirements/AGT.md#agt-002): AGT-002 [P1] MUST implement layered prompt assembly (highest to lowest authority; lower layers cannot override higher ones):.
- [ ] [BRL-001](../../../requirements/BRL.md#brl-001): BRL-001 | The AI answers only from the client's approved knowledge. When it does not know, it says so and captures a callback. | AI agents | KNW-005, KNW-007, POL-001.
- [ ] [BRL-002](../../../requirements/BRL.md#brl-002): BRL-002 | No price is quoted unless the client's pricing policy permits it. The default is never to quote. | AI agents, operators | POL-001, DSK-008, AGT-003.
- [ ] [BRL-003](../../../requirements/BRL.md#brl-003): BRL-003 | No arrival time or availability is promised unless dispatch or calendar data supports it. | AI agents, operators | POL-001, DSK-008.
- [ ] [BRL-035](../../../requirements/BRL.md#brl-035): BRL-035 | The AI gives no clinical, legal, tax or insurance advice. In licensed professions, binding actions and coverage or claims answers are reserved to licensed staff. | AI agents, operators | COM-016, COM-017, POL-001.
- [ ] [KNW-002](../../../requirements/KNW.md#knw-002): KNW-002 [P1] MUST support a vertical template per trade (Appendix E) that seeds the profile, intake slots, triage rules, sample FAQs and guardrails. Templates are data, editable by EverOnn staff without deploys.
- [ ] [POL-001](../../../requirements/POL.md#pol-001): POL-001 [P1] MUST enforce guardrails in two places: in the prompt (soft) and in code (hard): output filters and tool-call validators the model cannot bypass. Hard rules include: no price quote unless the pricing policy and KB explicitly allow it; no promise of arrival time unless dispatch data supports it; no medical/legal/financial advice; no collection of full card numbers or SSNs; no disclosure of other customers' information; no impersonating a human when sincerely asked whether it is an AI (COM-003).
- [ ] [VRT-003](../../../requirements/VRT.md#vrt-003): VRT-003 [P1] MUST define a Vertical pack as a versioned data bundle containing: website templates and section variants; content library (service pages, FAQs, industry explanations); vocabulary and labels; intake playbooks and slot definitions; urgency, escalation and authority defaults; starter knowledge; greeting templates; the vertical's structured request schema (VRT-006); the compliance profile it requires (COM-014); the connector set it uses (INT-002); plans, entitlements and default terms; dashboard and report definitions; the onboarding checklist; and the migration playbooks for its conquest targets (MIG-010). Pack changes are versioned, staged, evaluated (EVL-005) and reversible.

## Existing code / check evidence

- `ai/SYSTEM.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/GUARDRAILS.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/domains/hvac/SKILL.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/domains/hvac/GUARDRAILS.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/capabilities/website-building/SKILL.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/agent-runtime/tool-registry.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/agent-runtime/safety.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/voice-agent/gemini.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/provider-config.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/agent-runtime.test.ts`, `tests/website-ai.test.ts`, `tests/website-code.test.ts`, `tests/provider-config.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Deterministic mocks and EVALS Markdown do not prove live-model accuracy, audio latency or the required 150/500 scenario launch datasets.

Dependencies: [EVN-KNW-102](../../02-knowledge-agent-configuration/tickets/EVN-KNW-102.md), [EVN-AIQ-103](EVN-AIQ-103.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.

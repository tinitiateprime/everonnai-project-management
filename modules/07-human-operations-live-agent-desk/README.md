# 07. Human escalation and the multi-client Live Agent Desk

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `HIL`. Proposed accountable roles: Operations Lead + Voice/Media Lead + Backend Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-HIL-024](tickets/EVN-HIL-024.md) | Always able to reach a human | Partial | P1 |
| [EVN-HIL-025](tickets/EVN-HIL-025.md) | Configurable escalation rules | Partial | P1 |
| [EVN-HIL-026](tickets/EVN-HIL-026.md) | Shared multi-client operator desk | Planned | P1 pilot, P2 scale |
| [EVN-HIL-027](tickets/EVN-HIL-027.md) | Client screen-pop and correct greeting | Planned | P1 |
| [EVN-HIL-028](tickets/EVN-HIL-028.md) | No client mix-ups | Planned | P1 |
| [EVN-HIL-029](tickets/EVN-HIL-029.md) | Operator authority per client | Planned | P1 |
| [EVN-HIL-030](tickets/EVN-HIL-030.md) | Operator call and chat controls | Planned | P1 |
| [EVN-HIL-031](tickets/EVN-HIL-031.md) | Supervision | Planned | P2 |
| [EVN-HIL-032](tickets/EVN-HIL-032.md) | Staffing and rosters | Planned | P2 |
| [EVN-HIL-033](tickets/EVN-HIL-033.md) | Human quality and audit | Planned | P1 |
| [EVN-HIL-034](tickets/EVN-HIL-034.md) | Approvals for sensitive actions | Partial | P1 |
| [EVN-HIL-036](tickets/EVN-HIL-036.md) | Desk reliability | Planned | P1 |

## Current project capability

**EVN-HIL-024:** Safety text can recommend emergency services or a human; guaranteed takeover is absent.

**EVN-HIL-025:** The profile stores emergency rules and a transfer number.

**EVN-HIL-026:** The tenant dashboard is not a multi-client Live Agent Desk.

**EVN-HIL-027:** No carrier line resolver or operator screen-pop exists.

**EVN-HIL-028:** Tenant API guards exist; operator grants and client locks do not.

**EVN-HIL-029:** No operator authority matrix is implemented.

**EVN-HIL-030:** Browser AI voice testing is not an operator softphone.

**EVN-HIL-031:** Supervisor wallboard and monitor/whisper/barge controls are absent.

**EVN-HIL-032:** Business invitations do not implement operator staffing.

**EVN-HIL-033:** No operator intervention ledger, QA sampler or learning queue exists.

**EVN-HIL-034:** Booking confirms from server/provider success; selected website changes require owner publication.

**EVN-HIL-036:** Desk state, offer races and media reconnection are absent.

Current persistence: Basic tenant conversation handoff status and transfer-number facts only; no managed desk domain. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 106 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-AIQ-102](../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md), [EVN-ONB-101](../01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md), [EVN-ONB-102](../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-VOX-101](../04-telephone-voice-language/tickets/EVN-VOX-101.md).

## Existing code and verification

- `features/voice-agent/engine.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/auth/rbac.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `components/dashboard/everonn-dashboard.tsx` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/workspace-security.test.ts`, `tests/agent-runtime.test.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

No operator grants/queue/softphone, private briefing, authoritative offers, supervised human SLA or staffing evidence exists.

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

# 11. Public API, webhooks and vertical connectors

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `INT`. Proposed accountable roles: Integration Lead + Backend Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-INT-049](tickets/EVN-INT-049.md) | Connect the systems each vertical uses | Partial | P1 framework, P2 connectors |
| [EVN-INT-071](tickets/EVN-INT-071.md) | API and integrations | Partial | P1 |

## Current project capability

**EVN-INT-049:** Google Calendar/Gmail and customer GitHub are separate integrations.

**EVN-INT-071:** Internal scoped APIs, Google integrations and signed usage ingress exist.

Current persistence: Encrypted Google connections, GitHub repository credentials and specialised metering ingress records. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 25 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-ONB-102](../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-OPS-101](../18-reliability-deployment-scale/tickets/EVN-OPS-101.md), [EVN-SEC-101](../15-security-privacy-compliance/tickets/EVN-SEC-101.md).

## Existing code and verification

- `features/integrations/google.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/integrations/google-oauth.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `lib/provider-credentials.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `app/api/integrations/google/route.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `app/api/usage/elevenlabs/webhook/route.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/project-workspace/github.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/provider-credentials.test.ts`, `tests/usage-reliability.test.ts`, `tests/project-workspace.test.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

Internal app endpoints and provider ingress do not establish a public /v1 API, tenant API keys, partner webhooks or a connector SDK.

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

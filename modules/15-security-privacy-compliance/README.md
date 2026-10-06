# 15. Security, consent, privacy, legal terms and assurance

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `SEC`. Proposed accountable roles: Security Lead + Counsel + Product Owner; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-SEC-063](tickets/EVN-SEC-063.md) | Client data isolation | Partial | P1 |
| [EVN-SEC-064](tickets/EVN-SEC-064.md) | Consent and disclosure rules | Planned | P1 |
| [EVN-SEC-065](tickets/EVN-SEC-065.md) | Compliance profile for each vertical | Planned | P1 framework, P3 health care |
| [EVN-SEC-066](tickets/EVN-SEC-066.md) | Clear client terms | Planned | P1 |
| [EVN-SEC-067](tickets/EVN-SEC-067.md) | Export and deletion | Planned | P1 |
| [EVN-SEC-073](tickets/EVN-SEC-073.md) | Security assurance | Partial | P1 |
| [EVN-SEC-101](tickets/EVN-SEC-101.md) | Protect access, data and secrets with an approved security design | Partial | P1 |
| [EVN-SEC-102](tickets/EVN-SEC-102.md) | Prove important actions and incidents with tamper-evident evidence | Planned | P1 |

## Current project capability

**EVN-SEC-063:** Server workspace scope, RBAC, private SQL and isolation tests exist.

**EVN-SEC-064:** Prompt/session setup is not a jurisdiction consent system.

**EVN-SEC-065:** HVAC guardrails are not a compliance-profile engine.

**EVN-SEC-066:** Marketing legal pages are not recorded client/DPA acceptance.

**EVN-SEC-067:** Complete export/deletion/retention is absent.

**EVN-SEC-073:** Private tables, hashing, session/origin guards and regression tests exist.

**EVN-SEC-101:** Sessions/origin checks, private SQL, AES-GCM provider secrets and isolation tests exist.

**EVN-SEC-102:** Operational usage journals are not a full security audit chain.

Current persistence: Private entity tables, scoped auth, encrypted provider payloads and invoker write functions. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 81 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-FND-101](../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-OPS-102](../18-reliability-deployment-scale/tickets/EVN-OPS-102.md).

## Existing code and verification

- `features/auth/request-origin.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/auth/session.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/auth/rbac.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `lib/provider-credentials.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `lib/app-records.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `supabase/migrations/202610040003_everonn_relational.sql` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `supabase/migrations/202610060004_project_repositories.sql` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/workspace-security.test.ts`, `tests/request-origin.test.ts`, `tests/provider-credentials.test.ts`, `tests/everonn-relational.test.ts`, `tests/project-workspace.test.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

Private PostgreSQL and AES-GCM tokens are not a consent ledger, per-tenant KMS keys, audit/WORM chain, privacy operations, pen-test pass or SOC 2 certification.

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

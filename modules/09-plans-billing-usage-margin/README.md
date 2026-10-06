# 09. Plans, subscriptions, metering, budgets and margin

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `BIL`. Proposed accountable roles: Finance/Product Owner + Backend Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-BIL-010](tickets/EVN-BIL-010.md) | Fraud and cost protection | Partial | P1 |
| [EVN-BIL-040](tickets/EVN-BIL-040.md) | Plans and billing | Planned | P1 |
| [EVN-BIL-041](tickets/EVN-BIL-041.md) | Metering and limits | Partial | P1 |
| [EVN-BIL-042](tickets/EVN-BIL-042.md) | Cost and margin visibility | Partial | P1 |
| [EVN-BIL-043](tickets/EVN-BIL-043.md) | Published claims match the product | Partial | P1 |
| [EVN-BIL-101](tickets/EVN-BIL-101.md) | Show trustworthy observed Gemini and ElevenLabs usage | Implemented | P1 |

## Current project capability

**EVN-BIL-010:** Selected API rate limits and provider usage reporting exist.

**EVN-BIL-040:** Billing clearly reports subscriptions are not connected.

**EVN-BIL-041:** Gemini/ElevenLabs usage has durable records, dedupe and coverage status.

**EVN-BIL-042:** Reported costs and dated Gemini token estimates stay distinct.

**EVN-BIL-043:** Usage/billing UI avoids fake invoices; marketing claims/prices remain static.

**EVN-BIL-101:** Durable attempts, metadata journals, scoped summaries, duplicate/replay rejection and worker health are implemented.

Current persistence: usage_events, usage_sessions, usage_outbox, usage_claims, billing_reports, worker state/nonces/receipts. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 46 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-ONB-102](../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md).

## Existing code and verification

- `features/usage/gemini.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/usage/elevenlabs.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/usage/worker.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/usage/summary.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/usage/pricing.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/usage/billing.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/usage/job-auth.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/usage/webhook.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `components/dashboard/usage-section.tsx` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `lib/usage-postgres.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `lib/usage-scheduler.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/usage.test.ts`, `tests/usage-reliability.test.ts`, `tests/usage-scheduler.test.ts`, `tests/usage-supabase.test.ts`, `scripts/smoke-usage.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

Observed usage/estimated provider costs are not subscriptions, Stripe invoices, plan enforcement, all-channel costs or measured margins.

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

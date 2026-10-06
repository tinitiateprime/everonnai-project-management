# Delivery plan and release gates

Dates and effort require client/team agreement. The original documents estimate P0 at 3-4 weeks, P1 at 10-14 weeks and P2 at 8-12 weeks. These are source planning estimates, not new commitments, remaining-effort calculations or proof that earlier phases are complete.

## Immediate sequence

1. Review the current-state gaps and sign the architecture/scope ADRs. Resolve database/hosting/identity/voice/renderer choices without risking existing tenant records.
2. Agree one pilot service and its business acceptance scenarios. HVAC is the current implemented domain pack, so it is the practical candidate; the client still decides the launch scope.
3. Complete foundational contracts: tenant/published-version identity, provider/task boundaries, typed tools, event/job semantics, security and consent policy.
4. Prove a real telephone call on the agreed carriers and measure voice quality, latency, failure handling and cost. Prototype operator audio isolation before building the desk around assumptions.
5. Make website generation durable, then evaluate real drafts for service-specific design quality and factual grounding. Replace saved legacy publications only after owner approval.
6. Deliver the pilot's booking/inbox, plans/usage, verification/domains and human fallback workflows with staging and live-provider evidence.
7. Run the full pilot acceptance gate, rehearse rollback/recovery, and record client sign-off before broad launch.

## Phase scope

| Phase | Business result | Work and dependencies | Exit evidence |
| --- | --- | --- | --- |
| P0 - decisions and proof | Feasible, owned and approved production direction | FND-101; provider/tool foundations; real PSTN spike; evaluation harness seed; tenant schema decisions; CI/IaC; operator audio topology; ownership/access baseline | Approved ADRs, measured call/audio/cost traces, agreed pilot scope and acceptance owners, deploy/rollback proof |
| P1 - controlled pilot | Owners receive a verified site, approved assistant and measurable front-desk service | Onboarding/verification; immutable KB/config; durable website jobs; safe domains; actual voice/chat; consent; inbox/booking; owner/human fallback and required desk slice; subscriptions/entitlements; reporting; security/runbooks | Source acceptance scenarios for pilot scope, approved visual/a11y/AI review, provider receipts, staffing evidence, restore and rollout results, signed UAT |
| P2 - scale and expansion | Proven scale with reviewed new verticals and migrations | Source target of 1,000 clients and 1,000 sites/day; cell capacity; porting; additional connectors; acquisition/migration; deeper reporting; accounting as approved; three-restaurant pilot | Load/soak/chaos traces, measured unit economics, migration/parallel-run proof, pack readiness and restaurant accuracy/receipt tests |
| P3 - regulated/extended scope | Additional markets and regulated services only after readiness | Health/legal/insurance readiness, provider agreement chain, language expansion and any approved outbound campaigns | Jurisdiction/provider/legal approval, gated pack readiness, evaluated workflows and explicit new scope agreement |
| Session extension | Customer documentation workflow | Existing GitHub repository reader plus this Markdown planning pack | Repository role/isolation checks, hosted rollout/private-access verification, client navigation/review |

The source P1 pilot target is 20-50 clients with two brands/two packs. A first HVAC slice can precede that pilot; it does not silently reduce the contracted pilot. P0 schema/tool/event work is a foundation stage of tickets whose full delivery remains P1. Ownership/exit responsibilities begin at P0 and continue through later handover/drills. A later-phase drill does not delay initial ownership proof.

## Proposed pilot increments

| Increment | Reviewable deliverable | Key dependencies | Go/no-go review |
| --- | --- | --- | --- |
| 1 - foundation | Approved architecture, safe tenant identity, published configuration and reproducible staging | D-2/D-5/D-7/D-8; FND, ONB, KNW, SEC, OPS foundations | No unresolved platform exception or tenant-isolation defect |
| 2 - service experience | Premium HVAC website drafts, durable progress/resume, verified assistant capture and booking | AIQ-104; WEB-101/102/103; INB-101; provider/tool receipts | Owner approves factual/visual outcome; drafts remain private until verification |
| 3 - actual front desk | Real inbound telephone service, measured bilingual handling, owner/operator fallback and shared-desk proof | VOX spike and line setup; HIL routing/audio/grants; consent; workforce decisions | Real call/transfer/recording/STOP scenarios, authority and privacy tests pass |
| 4 - paid pilot | Plans/payment/usage enforcement, reporting, runbooks and staged pilot rollout | BIL, SEC/COM, OPS recovery, QA-101, OWN | All pilot Must criteria pass or are explicitly re-scoped in the agreement; client signs version |

The formal ticket index supplies detailed dependencies. Cross-module business workflows remain distinct tickets: for example, real calls do not close booking, operator staffing, consent or billing tickets automatically.

## Premium website acceptance

- [ ] Agree an art-direction brief from the business, audience and service; avoid unsupported trust badges, reviews and claims.
- [ ] Review independently generated concepts, typography, spacing, contrast, imagery and a coherent page system. Concept labels do not prescribe fixed layouts.
- [ ] Approve real desktop/mobile screenshots, content density, navigation, forms, booking and assistant interactions.
- [ ] Verify contact facts, locality, services and approved knowledge; uncertain facts stay omitted or clearly pending.
- [ ] Run accessibility, page-weight/Core Web Vitals and safe-code checks against the actual release.
- [ ] Make requested revisions, approve the draft, publish the reviewed snapshot and confirm rollback.

AI-generated original HTML/CSS is the current direction. A reviewable creative brief, deterministic safety rules and quality gates remain necessary. Generated code freedom does not remove business functionality, evidence, hosting or security obligations.

## Operational targets require measurement

| Source target | Proposed value | Evidence to collect |
| --- | --- | --- |
| Voice availability | 99.9% monthly | Real inbound synthetic calls, failure/incident accounting and safe capture |
| Tenant-site availability | 99.95% monthly | External checks and edge/origin failure evidence |
| Caller response gap | p50 below 1.0 s; p95 below 1.8 s | Carrier/audio/LLM stage traces across realistic noise/load |
| Summary completion | 99% within 30 s | Receipt-linked call-completion events and queue measurements |
| Operator offer / media | Offer p95 below 500 ms; media connection below 1.5 s | Timed desk offer/audio traces with multiple tenants |
| Desk recovery | Restore within 3 s; heartbeat every 5 s | Browser reconnect/loss and authoritative offer tests |
| External widget | Below 40 KB gz | Standalone packaged artifact size, not whole dashboard size |
| Mobile website quality | Lighthouse at least 90 in four source categories; LCP at most 2.5 s; CLS at most 0.1 | Actual page reports under agreed measurement conditions |
| Recovery | Source P1 RPO 15 min/RTO 4 h; other topology sections propose 5 min/60 min | Resolve phase/topology target, then run restore drills |

None of these targets is claimed as achieved by the current unit suite. Agree test environment, percentile population, excluded maintenance and measurement period before promising an SLA.

## Team and client inputs

Assign a product/acceptance owner, technical/backend/frontend leads, AI and voice/media leads, QA, SRE/security and an operations/workforce owner where human service is offered. Some roles can be combined only with demonstrated capacity. Counsel and vendor-account owners supply policy/agreement approvals where required by the source specification.

Required inputs include pilot business facts/approved knowledge, chosen domain/brand, authorised test numbers/providers/calendar, preferred workflow and operating hours, consent/recording wording, pricing/entitlements and staffing authority. Do not copy credentials or personal customer data into this planning repository.

## Release gate

- [ ] Architecture and product decisions approved; owners/estimates agreed.
- [ ] Scoped source criteria, AI/text/audio tests and premium UI review passed.
- [ ] No critical tenant leak, false business action, unsafe advice, consent violation or blocking accessibility defect.
- [ ] Provider costs, plan enforcement and actual business receipts reconciled.
- [ ] Staging/live rollout, observability, staffing, rollback and restore verified.
- [ ] Client records dated UAT acceptance for the released version.

See [ACCEPTANCE.md](ACCEPTANCE.md), [DECISIONS.md](DECISIONS.md) and [RISKS.md](RISKS.md). Deferred features must have explicit agreed scope disposition; a checkbox cannot replace contract review.

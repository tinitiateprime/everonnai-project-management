# EverOnn Delivery Kanban

[Architecture](everonn-architecture.md) · [End-to-end data flow](everonn-dataflow.md)

**Basis:** Both EverOnn requirements documents, version 1.0, dated 26 September 2026. **Revision:** 7 October 2026.

This is the delivery plan for the required EverOnn platform. Start with the client board and phase gates. Each short card links to a plain-language check and its complete source requirement. The source wording, including continuation lists and tables, is preserved in the ticket details.

**Planning baseline:** All cards start as Pending. No implementation, test result, client approval or production deployment is asserted by this revision. Owners, dates and evidence must be entered when delivery is planned and verified.

## How to read this board

1. Choose a module in the client board to see its business purpose and short cards.
2. Open a ticket link to read what will be delivered and how it will be checked.
3. Use the complete source text for engineering scope; the short label never replaces it.
4. Use the business, acceptance-test and user-story links to review why the work is needed.
5. Move a card only when its status conditions and evidence are recorded.

| Term | Meaning |
| --- | --- |
| Business / client | The subscribing business; its caller or visitor is the customer. |
| P0 / P1 / P2 / P3 | Foundations / pilot / scale / separately scoped expansion. These are delivery phases. |
| MUST | Required in the stated phase. |
| SHOULD | Expected unless an explicit reason to defer is recorded. |
| MAY | Optional under the source requirement. |
| Supporting task | Derived implementation/delivery work. PLAT, DATA and DEL IDs are planning labels, not new source requirement IDs. |
| Source severity p1–p4 | Escalation urgency, not delivery phase. The data-flow guide calls these S1–S4 for readability. |

## Status rules

**Workflow:** Pending → In Progress → Ready for Deploy → Ready for Test → Done.

| Status | Evidence needed to enter or leave it |
| --- | --- |
| Pending | Scope exists; named owner and confirmed prerequisites may still need planning. |
| In Progress | Owner and intended deliverable are recorded; work has started. Record blockers separately. |
| Ready for Deploy | Change is reviewed, relevant pre-deploy checks pass and it can be deployed to staging. This does not authorise production. |
| Ready for Test | Staging deployment/smoke checks pass and the reviewer can run the ticket and applicable official acceptance checks. |
| Done | Complete requirement and applicable checks pass; evidence, staging demonstration and product-owner acceptance are recorded under the definition of done. |

Failed review returns the card to In Progress with the reason. A blocked card retains its current status and records the blocking item, responsible person and next action. Production promotion remains a separately recorded release decision after applicable phase gates; staging deployment is not client acceptance.

For a decision, document or other non-code deliverable, Ready for Deploy means its reviewable artifact is ready to share; Ready for Test means it is ready for the required owner review. Done still requires recorded acceptance.

## Scope and counts

| Item | Count |
| --- | --- |
| Major modules | 15 |
| Workstreams | 77 |
| Original numbered engineering requirements | 325 |
| Retained platform/data supporting tasks | 35 |
| Added delivery/quality/handover supporting tasks | 9 |
| Total delivery cards | 369 |
| Business requirements mapped | 76 |
| Business rules retained | 38 |
| Official acceptance tests retained | 60 |
| User stories retained | 72 |
| Decisions linked | 34 |

The additional nine DEL tasks expose non-numbered deliverables in specification §§24 and 26. All 360 original IDs remain. Original engineering phases and priorities are unchanged. Phase/owner suggestions on supporting tasks are planning proposals, not source approvals.

## Phase gates

| Phase | Business result | Acceptance gate |
| --- | --- | --- |
| P0 — Foundations | Prove the voice, operator audio, tenancy and industry configuration; approve decisions and establish environments, threat/cost models and evaluations. | Required spikes and isolation checks pass; decisions are ratified; measured voice target or accepted gap plan is recorded. |
| P1 — Pilot | Launch the specified phone/chat/site/inbox service with a small human pool, two brands/packs, billing, acquisition and migration basics. | Applicable P1 AT tests pass; 20+ clients run real numbers for two weeks meeting SLOs; required security findings fixed; runbooks complete. |
| P2 — Scale | Prove larger capacity, operator service levels, sequences, additional industries, restaurant pickup pilot and recovery. | Applicable P2 tests, load/soak, 30-day operator pilot, restaurant accuracy and recovery evidence pass; SOC 2 readiness assessment completed as specified. |
| P3 — Expansion | Deliver separately agreed regulated industries, broader integrations/languages, reseller and enterprise scope. | Approved P3 scope and applicable acceptance/compliance/readiness gates. |

Source week ranges (P0 3–4, P1 10–14, P2 8–12) are estimates for the studio to validate, not committed dates. Source §§5.5 and 25.1 provide complementary gates; both apply.

| P1 increment | Required focus |
| --- | --- |
| 1 | Voice core, numbers/forwarding, playbook/tools, post-call package, owner summary, metering and consent. |
| 2 | Claim/knowledge approval, agent controls, test/publish/rollback, owner escalation and pilot operator desk. |
| 3 | Chat/SMS, inbox/booking, sites/custom domains, two brands/packs and migration basics. |
| 4 | Billing/entitlements, admin/API, cost/quality, acquisition/readiness consoles and hardening for pilot onboarding. |

## Planning dependencies

The table below is recommended sequencing, not an invented approval or a blanket requirement to finish a whole module before starting another. Spikes and foundations can run in parallel; actual blocking dependencies must be recorded per ticket.

| Work | Required or proposed prerequisite |
| --- | --- |
| P1 build | Source AR-001 decision records and applicable P0 gates; unresolved baseline/provider decisions need their named owner. |
| Live customer channels | Scoped access/storage, approved knowledge and policies, consent/disclosures and verified channel setup. |
| Human desk | Client grants and identity, escalation state/timers, tested audio topology and the approved authority/coverage rules. |
| Appointment promises | An authorised calendar, validated business rules and successful atomic booking. |
| Public website | Verified owner/domain, resolved claims and recorded approval of the published version. |
| Acquisition contact / cut-over | Approved sources/channels/claims; then customer authorisation, inventory, tested continuity and sign-off. |
| Restaurant pilot | Approved pack/menu, staff receipt path, payment choice and accuracy thresholds under D-30. |
| Regulated pack | Applicable compliance profile, reviewed terms/provider agreements, safety tests and VRT-005 readiness approval. |
| Production release | Applicable tests, security/evaluation evidence, accepted staging result and phase/release gate. |

Security, privacy, consent, observability and evaluation work accompany each feature; they are not postponed until the end.

## Client board

The overview cards represent modules; the delivery cards below represent individual requirements/tasks. All columns are a planning starting point. The tables and ticket delivery records must be updated alongside diagram moves.

On a phone, use the linked ticket table below each diagram. It contains the same cards, phases, priorities and statuses in a readable text layout.

```mermaid
kanban
    pending[Pending]
        module01["01 - Who can access the platform"]
        module02["02 - Platform design and key decisions"]
        module03["03 - Platform setup"]
        module04["04 - Data storage and recovery"]
        module05["05 - Business setup and account management"]
        module06["06 - Approved business knowledge and AI controls"]
        module07["07 - Phone answering"]
        module08["08 - Website chat and text messages"]
        module09["09 - Human help and the operator desk"]
        module10["10 - Inbox, booking and follow-up"]
        module11["11 - Business websites"]
        module12["12 - Billing, brands, growth and integrations"]
        module13["13 - Security and future readiness"]
        module14["14 - Performance, reliability and operating costs"]
        module15["15 - Testing, release and client acceptance"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Module | Business purpose | Cards |
| --- | --- | --- |
| [01 — Who can access the platform](#module-01) | People receive only the access their role, business and brand allow. | 6 |
| [02 — Platform design and key decisions](#module-02) | The platform stays reliable, scalable and independent of a single provider. | 10 |
| [03 — Platform setup](#module-03) | The approved production foundation can be built, secured and reproduced. | 25 |
| [04 — Data storage and recovery](#module-04) | Business records, versions, files and history remain separate, recoverable and auditable. | 10 |
| [05 — Business setup and account management](#module-05) | An owner moves from a private preview to a verified, tested and live business account. | 19 |
| [06 — Approved business knowledge and AI controls](#module-06) | The assistant uses approved facts, follows the business rules and changes safely. | 23 |
| [07 — Phone answering](#module-07) | Real callers get accurate, timely answers, confirmed details and human help when needed. | 40 |
| [08 — Website chat and text messages](#module-08) | Customers receive the same approved help through chat and consent-aware texting. | 13 |
| [09 — Human help and the operator desk](#module-09) | A suitable person receives the right client context, handles safely and records the outcome. | 43 |
| [10 — Inbox, booking and follow-up](#module-10) | The business can organise enquiries, book available times and follow up with permission. | 15 |
| [11 — Business websites](#module-11) | Owners receive truthful, fast websites they can review, approve, edit and publish safely. | 18 |
| [12 — Billing, brands, growth and integrations](#module-12) | The shared platform supports plans, brands, reporting, switching customers and later pickup ordering. | 97 |
| [13 — Security and future readiness](#module-13) | Client information and accounts stay protected, with tested recovery and incident procedures. | 18 |
| [14 — Performance, reliability and operating costs](#module-14) | Measured tests prove speed, capacity, continuity and commercially sustainable costs. | 13 |
| [15 — Testing, release and client acceptance](#module-15) | Releases have quality evidence, client acceptance and complete operational handover. | 19 |

## Decisions and clarification

All 34 decisions, their source owners, deadlines and defaults are in the [architecture decision register](everonn-architecture.md#13-decision-register). None is marked approved here. Record actual outcomes before treating a default as an approval.

| Item | Required resolution |
| --- | --- |
| Platform/provider decisions | D-2/4/5/6/7/8/15 include baseline exceptions, vectors, identity, edge, voice, hosting and operator audio. |
| Commercial/operations decisions | Pricing, authority, recording, STOP, operator coverage and legal terms follow their source decision owners. |
| Industry/acquisition decisions | D-19/26–34 cover launch order, brands, source licences, outreach, restaurant pilot, regulated readiness and switching offers. |
| P2 call-load wording | §23.1 lists 35 peak / 70 design concurrent calls, while LT-002 says 3x projected peak (about 200). Agree and record the test count; retain both source statements. |
| Review solicitation | FUP-002 explicitly requires platform-policy review before its proposed sentiment-based gating can ship. |

## Module boards

## Module 01

**Who can access the platform**

People receive only the access their role, business and brand allow.

**Suggested accountable role:** Security / identity lead. Named owner and dates are not assigned.

**Planning status:** 6 cards Pending; no acceptance evidence recorded.

### 01.01

**Access permissions**

**Suggested role(s):** Security / identity lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardACC001["ACC-001 - Check permissions on every request"]
        cardACC002["ACC-002 - Record and control support access"]
        cardACC003["ACC-003 - Protect accounts with a second login check"]
        cardACC004["ACC-004 - Use one trusted staff login"]
        cardACC005["ACC-005 - Control integration access keys"]
        cardACC006["ACC-006 - Separate brand and growth-team permissions"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [ACC-001 — Check permissions on every request](#acc-001) | P1 · Required | Pending |
| [ACC-002 — Record and control support access](#acc-002) | P1 · Required | Pending |
| [ACC-003 — Protect accounts with a second login check](#acc-003) | P1 · Required | Pending |
| [ACC-004 — Use one trusted staff login](#acc-004) | P2 · Expected | Pending |
| [ACC-005 — Control integration access keys](#acc-005) | P1 · Required | Pending |
| [ACC-006 — Separate brand and growth-team permissions](#acc-006) | P1 · Required | Pending |

[Back to the client board](#client-board)

## Module 02

**Platform design and key decisions**

The platform stays reliable, scalable and independent of a single provider.

**Suggested accountable role:** Architecture lead. Named owner and dates are not assigned.

**Planning status:** 10 cards Pending; no acceptance evidence recorded.

### 02.01

**Design, provider choice and continuity**

**Suggested role(s):** Architecture lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardAR001["AR-001 - Record and approve the platform design decisions"]
        cardAR002["AR-002 - Keep service providers replaceable"]
        cardAR003["AR-003 - Deliver system events reliably"]
        cardAR004["AR-004 - Keep answering during an outage"]
        cardAR005["AR-005 - Add capacity without redesigning"]
        cardAR006["AR-006 - Keep servers easy to replace"]
        cardAR007["AR-007 - Version APIs, events and AI settings"]
        cardAR008["AR-008 - Maintain understandable design diagrams"]
        cardAR009["AR-009 - Deploy updates without dropping calls"]
        cardAR010["AR-010 - Prepare for larger deployment platforms"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [AR-001 — Record and approve the platform design decisions](#ar-001) | P0 · Required | Pending |
| [AR-002 — Keep service providers replaceable](#ar-002) | P0 · Required | Pending |
| [AR-003 — Deliver system events reliably](#ar-003) | P0 · Required | Pending |
| [AR-004 — Keep answering during an outage](#ar-004) | P1 · Required | Pending |
| [AR-005 — Add capacity without redesigning](#ar-005) | P1 · Required | Pending |
| [AR-006 — Keep servers easy to replace](#ar-006) | P1 · Required | Pending |
| [AR-007 — Version APIs, events and AI settings](#ar-007) | P1 · Required | Pending |
| [AR-008 — Maintain understandable design diagrams](#ar-008) | P0 · Expected | Pending |
| [AR-009 — Deploy updates without dropping calls](#ar-009) | P1 · Required | Pending |
| [AR-010 — Prepare for larger deployment platforms](#ar-010) | P2 · Expected | Pending |

[Back to the client board](#client-board)

## Module 03

**Platform setup**

The approved production foundation can be built, secured and reproduced.

**Suggested accountable role:** Platform / infrastructure lead. Named owner and dates are not assigned.

**Planning status:** 25 cards Pending; no acceptance evidence recorded.

### 03.01

**Background work and deadlines**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT013["PLAT-013 - Prepare reliable background work and timers"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-013 — Prepare reliable background work and timers](#plat-013) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.02

**Caching and queues**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT007["PLAT-007 - Separate caching and background workloads"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-007 — Separate caching and background workloads](#plat-007) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.03

**Chat widget foundation**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT012["PLAT-012 - Create the website chat foundation"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-012 — Create the website chat foundation](#plat-012) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.04

**Production containers**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT002["PLAT-002 - Run reproducible production containers"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-002 — Run reproducible production containers](#plat-002) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.05

**Business API foundation**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT004["PLAT-004 - Create the shared business API foundation"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-004 — Create the shared business API foundation](#plat-004) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.06

**Database foundation**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT006["PLAT-006 - Prepare the database and replica"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-006 — Prepare the database and replica](#plat-006) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.07

**Deployment tiers**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT025["PLAT-025 - Separate deployment tiers"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-025 — Separate deployment tiers](#plat-025) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.08

**Secure edge and website delivery**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT016["PLAT-016 - Prepare secure website and application delivery"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-016 — Prepare secure website and application delivery](#plat-016) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.09

**Email service**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT015["PLAT-015 - Connect an approved email service"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-015 — Connect an approved email service](#plat-015) | P1 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.10

**Knowledge-search benchmark**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT020["PLAT-020 - Measure knowledge-search quality and speed"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-020 — Measure knowledge-search quality and speed](#plat-020) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.11

**Separate environments**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT023["PLAT-023 - Separate development, test and production"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-023 — Separate development, test and production](#plat-023) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.12

**Login foundation**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT009["PLAT-009 - Set up the approved identity service"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-009 — Set up the approved identity service](#plat-009) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.13

**Safe image processing**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT022["PLAT-022 - Process website images safely"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-022 — Process website images safely](#plat-022) | P1 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.14

**Automated infrastructure**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT024["PLAT-024 - Automate environment and capacity setup"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-024 — Automate environment and capacity setup](#plat-024) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.15

**Phone and audio foundation**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT017["PLAT-017 - Prove real phone and operator audio connections"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-017 — Prove real phone and operator audio connections](#plat-017) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.16

**Shared AI model service**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT019["PLAT-019 - Create the shared AI model service"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-019 — Create the shared AI model service](#plat-019) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.17

**Private file storage**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT008["PLAT-008 - Store recordings, sites and backups safely"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-008 — Store recordings, sites and backups safely](#plat-008) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.18

**Service monitoring**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT014["PLAT-014 - Prepare service monitoring"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-014 — Prepare service monitoring](#plat-014) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.19

**Production operating system**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT001["PLAT-001 - Prepare the required production operating system"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-001 — Prepare the required production operating system](#plat-001) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.20

**Voice/evaluation service foundation**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT005["PLAT-005 - Create the voice and evaluation service foundation"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-005 — Create the voice and evaluation service foundation](#plat-005) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.21

**Engineering repository**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT003["PLAT-003 - Create the shared engineering repository"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-003 — Create the shared engineering repository](#plat-003) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.22

**Secrets and keys**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT010["PLAT-010 - Set up secrets and encryption-key management"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-010 — Set up secrets and encryption-key management](#plat-010) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.23

**Both telephone carriers**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT018["PLAT-018 - Connect both P1 telephone carriers"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-018 — Connect both P1 telephone carriers](#plat-018) | P1 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.24

**Client and staff application shells**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT011["PLAT-011 - Create client and staff application foundations"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-011 — Create client and staff application foundations](#plat-011) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 03.25

**Website renderer foundation**

**Suggested role(s):** Platform / infrastructure lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPLAT021["PLAT-021 - Create the versioned website renderer"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [PLAT-021 — Create the versioned website renderer](#plat-021) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

## Module 04

**Data storage and recovery**

Business records, versions, files and history remain separate, recoverable and auditable.

**Suggested accountable role:** Data / backend lead. Named owner and dates are not assigned.

**Planning status:** 10 cards Pending; no acceptance evidence recorded.

### 04.01

**Backup and recovery**

**Suggested role(s):** Data / backend lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDATA004["DATA-004 - Back up and restore the platform"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DATA-004 — Back up and restore the platform](#data-004) | P1 · Supporting | Pending |

[Back to the client board](#client-board)

### 04.02

**Controlled database connections**

**Suggested role(s):** Data / backend lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDATA005["DATA-005 - Use controlled database connections"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DATA-005 — Use controlled database connections](#data-005) | P1 · Supporting | Pending |

[Back to the client board](#client-board)

### 04.03

**Events usage and audit records**

**Suggested role(s):** Data / backend lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDATA007["DATA-007 - Store usage, events and audits reliably"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DATA-007 — Store usage, events and audits reliably](#data-007) | P1 · Supporting | Pending |

[Back to the client board](#client-board)

### 04.04

**Large volumes of history**

**Suggested role(s):** Data / backend lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDATA003["DATA-003 - Manage high-volume history efficiently"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DATA-003 — Manage high-volume history efficiently](#data-003) | P1 · Supporting | Pending |

[Back to the client board](#client-board)

### 04.05

**Private files and metadata**

**Suggested role(s):** Data / backend lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDATA008["DATA-008 - Protect file references and metadata"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DATA-008 — Protect file references and metadata](#data-008) | P1 · Supporting | Pending |

[Back to the client board](#client-board)

### 04.06

**Retention and archive**

**Suggested role(s):** Data / backend lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDATA010["DATA-010 - Archive and expire records correctly"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DATA-010 — Archive and expire records correctly](#data-010) | P1 · Supporting | Pending |

[Back to the client board](#client-board)

### 04.07

**Safe schema changes**

**Suggested role(s):** Data / backend lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDATA002["DATA-002 - Change database schemas safely"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DATA-002 — Change database schemas safely](#data-002) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 04.08

**Search indexes**

**Suggested role(s):** Data / backend lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDATA009["DATA-009 - Index approved knowledge and inbox search"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DATA-009 — Index approved knowledge and inbox search](#data-009) | P1 · Supporting | Pending |

[Back to the client board](#client-board)

### 04.09

**Business isolation conventions**

**Suggested role(s):** Data / backend lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDATA001["DATA-001 - Apply business-scoped storage conventions"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DATA-001 — Apply business-scoped storage conventions](#data-001) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

### 04.10

**Immutable published versions**

**Suggested role(s):** Data / backend lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDATA006["DATA-006 - Preserve published knowledge and AI versions"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DATA-006 — Preserve published knowledge and AI versions](#data-006) | P1 · Supporting | Pending |

[Back to the client board](#client-board)

## Module 05

**Business setup and account management**

An owner moves from a private preview to a verified, tested and live business account.

**Suggested accountable role:** Product / onboarding lead. Named owner and dates are not assigned.

**Planning status:** 19 cards Pending; no acceptance evidence recorded.

### 05.01

**Owner setup and activation**

**Suggested role(s):** Product / onboarding lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardONB001["ONB-001 - Create a private preview in minutes"]
        cardONB002["ONB-002 - Verify the business before going public"]
        cardONB003["ONB-003 - Guide the owner through setup"]
        cardONB004["ONB-004 - Try the AI before launch"]
        cardONB005["ONB-005 - Record the owner's approval"]
        cardONB006["ONB-006 - Capture hours, coverage and contact preferences"]
        cardONB007["ONB-007 - Import existing business information"]
        cardONB008["ONB-008 - Support businesses with several locations"]
        cardONB009["ONB-009 - Invite staff with suitable access"]
        cardONB010["ONB-010 - Avoid duplicate business accounts"]
        cardONB011["ONB-011 - Use the correct brand during setup"]
        cardONB012["ONB-012 - Start setup for a switching customer"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [ONB-001 — Create a private preview in minutes](#onb-001) | P1 · Required | Pending |
| [ONB-002 — Verify the business before going public](#onb-002) | P1 · Required | Pending |
| [ONB-003 — Guide the owner through setup](#onb-003) | P1 · Required | Pending |
| [ONB-004 — Try the AI before launch](#onb-004) | P1 · Required | Pending |
| [ONB-005 — Record the owner's approval](#onb-005) | P1 · Required | Pending |
| [ONB-006 — Capture hours, coverage and contact preferences](#onb-006) | P1 · Required | Pending |
| [ONB-007 — Import existing business information](#onb-007) | P1 · Expected | Pending |
| [ONB-008 — Support businesses with several locations](#onb-008) | P2 · Expected | Pending |
| [ONB-009 — Invite staff with suitable access](#onb-009) | P1 · Required | Pending |
| [ONB-010 — Avoid duplicate business accounts](#onb-010) | P1 · Required | Pending |
| [ONB-011 — Use the correct brand during setup](#onb-011) | P1 · Required | Pending |
| [ONB-012 — Start setup for a switching customer](#onb-012) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 05.02

**Business and brand isolation**

**Suggested role(s):** Product / onboarding lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardTEN001["TEN-001 - Keep every business's data separate"]
        cardTEN002["TEN-002 - Record where each business is hosted"]
        cardTEN003["TEN-003 - Offer dedicated data placement later"]
        cardTEN004["TEN-004 - Separate files, queues and caches by business"]
        cardTEN005["TEN-005 - Prevent one business from slowing others"]
        cardTEN006["TEN-006 - Export or delete business data"]
        cardTEN007["TEN-007 - Keep brands and industry packs separate"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [TEN-001 — Keep every business's data separate](#ten-001) | P0 · Required | Pending |
| [TEN-002 — Record where each business is hosted](#ten-002) | P1 · Required | Pending |
| [TEN-003 — Offer dedicated data placement later](#ten-003) | P2 · Expected | Pending |
| [TEN-004 — Separate files, queues and caches by business](#ten-004) | P1 · Required | Pending |
| [TEN-005 — Prevent one business from slowing others](#ten-005) | P1 · Required | Pending |
| [TEN-006 — Export or delete business data](#ten-006) | P1 · Required | Pending |
| [TEN-007 — Keep brands and industry packs separate](#ten-007) | P1 · Required | Pending |

[Back to the client board](#client-board)

## Module 06

**Approved business knowledge and AI controls**

The assistant uses approved facts, follows the business rules and changes safely.

**Suggested accountable role:** AI / knowledge lead. Named owner and dates are not assigned.

**Planning status:** 23 cards Pending; no acceptance evidence recorded.

### 06.01

**Assistant settings and safe changes**

**Suggested role(s):** AI / knowledge lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardAGT001["AGT-001 - Define a versioned assistant"]
        cardAGT002["AGT-002 - Apply instructions in the correct order"]
        cardAGT003["AGT-003 - Let owners adjust the assistant easily"]
        cardAGT004["AGT-004 - Test, publish and undo AI changes"]
        cardAGT005["AGT-005 - Compare approved assistant variants"]
        cardAGT006["AGT-006 - Choose AI models by task"]
        cardAGT007["AGT-007 - Control which actions the AI can take"]
        cardAGT008["AGT-008 - Create a reliable request after each conversation"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [AGT-001 — Define a versioned assistant](#agt-001) | P1 · Required | Pending |
| [AGT-002 — Apply instructions in the correct order](#agt-002) | P1 · Required | Pending |
| [AGT-003 — Let owners adjust the assistant easily](#agt-003) | P1 · Required | Pending |
| [AGT-004 — Test, publish and undo AI changes](#agt-004) | P1 · Required | Pending |
| [AGT-005 — Compare approved assistant variants](#agt-005) | P2 · Expected | Pending |
| [AGT-006 — Choose AI models by task](#agt-006) | P1 · Required | Pending |
| [AGT-007 — Control which actions the AI can take](#agt-007) | P1 · Required | Pending |
| [AGT-008 — Create a reliable request after each conversation](#agt-008) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 06.02

**Business facts and industry playbooks**

**Suggested role(s):** AI / knowledge lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardKNW001["KNW-001 - Maintain a structured business profile"]
        cardKNW002["KNW-002 - Start with an industry-specific playbook"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [KNW-001 — Maintain a structured business profile](#knw-001) | P1 · Required | Pending |
| [KNW-002 — Start with an industry-specific playbook](#knw-002) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 06.03

**Safety rules**

**Suggested role(s):** AI / knowledge lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardPOL001["POL-001 - Enforce the business's safety rules"]
        cardPOL002["POL-002 - Recognise emergencies and seek human help"]
        cardPOL003["POL-003 - Ignore attempts to override the AI's rules"]
        cardPOL004["POL-004 - Handle abusive or unwanted interactions"]
        cardPOL005["POL-005 - Collect only necessary personal information"]
        cardPOL006["POL-006 - Record safety interventions"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [POL-001 — Enforce the business's safety rules](#pol-001) | P1 · Required | Pending |
| [POL-002 — Recognise emergencies and seek human help](#pol-002) | P1 · Required | Pending |
| [POL-003 — Ignore attempts to override the AI's rules](#pol-003) | P1 · Required | Pending |
| [POL-004 — Handle abusive or unwanted interactions](#pol-004) | P1 · Required | Pending |
| [POL-005 — Collect only necessary personal information](#pol-005) | P1 · Required | Pending |
| [POL-006 — Record safety interventions](#pol-006) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 06.04

**Imported knowledge and answer sources**

**Suggested role(s):** AI / knowledge lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardKNW003["KNW-003 - Import documents and questions"]
        cardKNW004["KNW-004 - Search only the right business's knowledge"]
        cardKNW005["KNW-005 - Approve knowledge before the AI uses it"]
        cardKNW006["KNW-006 - Find outdated or conflicting information"]
        cardKNW007["KNW-007 - Admit when an answer is unknown"]
        cardKNW008["KNW-008 - Improve the quality of knowledge search"]
        cardKNW009["KNW-009 - Explain why the AI gave an answer"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [KNW-003 — Import documents and questions](#knw-003) | P1 · Required | Pending |
| [KNW-004 — Search only the right business's knowledge](#knw-004) | P1 · Required | Pending |
| [KNW-005 — Approve knowledge before the AI uses it](#knw-005) | P1 · Required | Pending |
| [KNW-006 — Find outdated or conflicting information](#knw-006) | P1 · Expected | Pending |
| [KNW-007 — Admit when an answer is unknown](#knw-007) | P1 · Required | Pending |
| [KNW-008 — Improve the quality of knowledge search](#knw-008) | P2 · Expected | Pending |
| [KNW-009 — Explain why the AI gave an answer](#knw-009) | P1 · Required | Pending |

[Back to the client board](#client-board)

## Module 07

**Phone answering**

Real callers get accurate, timely answers, confirmed details and human help when needed.

**Suggested accountable role:** Voice engineering lead. Named owner and dates are not assigned.

**Planning status:** 40 cards Pending; no acceptance evidence recorded.

### 07.01

**What the phone assistant does**

**Suggested role(s):** Voice engineering lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardVOX016["VOX-016 - Follow the industry's intake steps"]
        cardVOX017["VOX-017 - Classify the request's urgency"]
        cardVOX018["VOX-018 - Check whether the business serves the address"]
        cardVOX019["VOX-019 - Transfer calls with useful context"]
        cardVOX020["VOX-020 - Book an appointment when appropriate"]
        cardVOX021["VOX-021 - Send the owner a prompt call summary"]
        cardVOX022["VOX-022 - Send a permitted customer confirmation"]
        cardVOX023["VOX-023 - Save the complete call outcome"]
        cardVOX024["VOX-024 - Recognise a verified returning caller"]
        cardVOX025["VOX-025 - Make approved callbacks"]
        cardVOX026["VOX-026 - Stop unexpectedly expensive calls safely"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [VOX-016 — Follow the industry's intake steps](#vox-016) | P1 · Required | Pending |
| [VOX-017 — Classify the request's urgency](#vox-017) | P1 · Required | Pending |
| [VOX-018 — Check whether the business serves the address](#vox-018) | P1 · Required | Pending |
| [VOX-019 — Transfer calls with useful context](#vox-019) | P1 · Required | Pending |
| [VOX-020 — Book an appointment when appropriate](#vox-020) | P1 · Required | Pending |
| [VOX-021 — Send the owner a prompt call summary](#vox-021) | P1 · Required | Pending |
| [VOX-022 — Send a permitted customer confirmation](#vox-022) | P1 · Required | Pending |
| [VOX-023 — Save the complete call outcome](#vox-023) | P1 · Required | Pending |
| [VOX-024 — Recognise a verified returning caller](#vox-024) | P1 · Required | Pending |
| [VOX-025 — Make approved callbacks](#vox-025) | P2 · Expected | Pending |
| [VOX-026 — Stop unexpectedly expensive calls safely](#vox-026) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 07.02

**Conversation quality and languages**

**Suggested role(s):** Voice engineering lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardVOX002["VOX-002 - Run the real-time speech conversation"]
        cardVOX003["VOX-003 - Keep phone responses fast"]
        cardVOX004["VOX-004 - Let callers interrupt the assistant"]
        cardVOX005["VOX-005 - Recognise when a caller has finished speaking"]
        cardVOX006["VOX-006 - Understand noisy calls safely"]
        cardVOX007["VOX-007 - Read back important details"]
        cardVOX008["VOX-008 - Answer in English and Spanish"]
        cardVOX009["VOX-009 - Always provide a route to a person"]
        cardVOX010["VOX-010 - Recognise voicemail on outgoing call legs"]
        cardVOX011["VOX-011 - Handle silence, holds and disconnected calls"]
        cardVOX012["VOX-012 - Offer approved voices"]
        cardVOX013["VOX-013 - Avoid interruptions caused by background noise"]
        cardVOX014["VOX-014 - Adjust speaking style"]
        cardVOX015["VOX-015 - Handle several people on speakerphone"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [VOX-002 — Run the real-time speech conversation](#vox-002) | P0 · Required | Pending |
| [VOX-003 — Keep phone responses fast](#vox-003) | P0 · Required | Pending |
| [VOX-004 — Let callers interrupt the assistant](#vox-004) | P1 · Required | Pending |
| [VOX-005 — Recognise when a caller has finished speaking](#vox-005) | P1 · Required | Pending |
| [VOX-006 — Understand noisy calls safely](#vox-006) | P1 · Required | Pending |
| [VOX-007 — Read back important details](#vox-007) | P1 · Required | Pending |
| [VOX-008 — Answer in English and Spanish](#vox-008) | P1 · Required | Pending |
| [VOX-009 — Always provide a route to a person](#vox-009) | P1 · Required | Pending |
| [VOX-010 — Recognise voicemail on outgoing call legs](#vox-010) | P1 · Required | Pending |
| [VOX-011 — Handle silence, holds and disconnected calls](#vox-011) | P1 · Required | Pending |
| [VOX-012 — Offer approved voices](#vox-012) | P1 · Required | Pending |
| [VOX-013 — Avoid interruptions caused by background noise](#vox-013) | P1 · Required | Pending |
| [VOX-014 — Adjust speaking style](#vox-014) | P2 · Expected | Pending |
| [VOX-015 — Handle several people on speakerphone](#vox-015) | P2 · Expected | Pending |

[Back to the client board](#client-board)

### 07.03

**Numbers forwarding and carrier controls**

**Suggested role(s):** Voice engineering lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardVOX001["VOX-001 - Answer real business phone calls"]
        cardVOX030["VOX-030 - Connect an existing or new business number"]
        cardVOX031["VOX-031 - Test forwarding before activation"]
        cardVOX032["VOX-032 - Let the owner answer first"]
        cardVOX033["VOX-033 - Follow up on a missed call by text"]
        cardVOX034["VOX-034 - Use the correct caller identity"]
        cardVOX035["VOX-035 - Track phone and texting registrations"]
        cardVOX036["VOX-036 - Switch carriers during a failure"]
        cardVOX037["VOX-037 - Block phone fraud and artificial traffic"]
        cardVOX038["VOX-038 - Monitor phone-number reputation"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [VOX-001 — Answer real business phone calls](#vox-001) | P1 · Required | Pending |
| [VOX-030 — Connect an existing or new business number](#vox-030) | P1 · Required | Pending |
| [VOX-031 — Test forwarding before activation](#vox-031) | P1 · Required | Pending |
| [VOX-032 — Let the owner answer first](#vox-032) | P1 · Required | Pending |
| [VOX-033 — Follow up on a missed call by text](#vox-033) | P1 · Required | Pending |
| [VOX-034 — Use the correct caller identity](#vox-034) | P1 · Required | Pending |
| [VOX-035 — Track phone and texting registrations](#vox-035) | P1 · Required | Pending |
| [VOX-036 — Switch carriers during a failure](#vox-036) | P2 · Required | Pending |
| [VOX-037 — Block phone fraud and artificial traffic](#vox-037) | P1 · Required | Pending |
| [VOX-038 — Monitor phone-number reputation](#vox-038) | P1 · Expected | Pending |

[Back to the client board](#client-board)

### 07.04

**Voice deployment and measurements**

**Suggested role(s):** Voice engineering lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardVOX040["VOX-040 - Scale voice workers safely"]
        cardVOX041["VOX-041 - Place voice services near the carrier"]
        cardVOX042["VOX-042 - Measure each stage and call's cost"]
        cardVOX043["VOX-043 - Replay calls safely for testing"]
        cardVOX044["VOX-044 - Prepare voice sessions before calls arrive"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [VOX-040 — Scale voice workers safely](#vox-040) | P1 · Required | Pending |
| [VOX-041 — Place voice services near the carrier](#vox-041) | P1 · Required | Pending |
| [VOX-042 — Measure each stage and call's cost](#vox-042) | P1 · Required | Pending |
| [VOX-043 — Replay calls safely for testing](#vox-043) | P1 · Required | Pending |
| [VOX-044 — Prepare voice sessions before calls arrive](#vox-044) | P2 · Expected | Pending |

[Back to the client board](#client-board)

## Module 08

**Website chat and text messages**

Customers receive the same approved help through chat and consent-aware texting.

**Suggested accountable role:** Messaging / frontend lead. Named owner and dates are not assigned.

**Planning status:** 13 cards Pending; no acceptance evidence recorded.

### 08.01

**Chat and text experience**

**Suggested role(s):** Messaging / frontend lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardCHT001["CHT-001 - Add a small, accessible chat widget"]
        cardCHT002["CHT-002 - Show chat answers as they arrive"]
        cardCHT003["CHT-003 - Use the same approved assistant in every channel"]
        cardCHT004["CHT-004 - Offer helpful chat actions and photo upload"]
        cardCHT005["CHT-005 - Ask permission before texting a chat visitor"]
        cardCHT006["CHT-006 - Keep the visitor's conversation together"]
        cardCHT007["CHT-007 - Protect chat against spam and cost abuse"]
        cardCHT008["CHT-008 - Let a human take over the chat"]
        cardCHT009["CHT-009 - Keep text conversations together and honour STOP"]
        cardCHT010["CHT-010 - Start chat with configured invitations"]
        cardCHT011["CHT-011 - Save chat and text outcomes in the inbox"]
        cardCHT012["CHT-012 - Chat in the visitor's language"]
        cardCHT013["CHT-013 - Tell visitors they are speaking with AI"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [CHT-001 — Add a small, accessible chat widget](#cht-001) | P1 · Required | Pending |
| [CHT-002 — Show chat answers as they arrive](#cht-002) | P1 · Required | Pending |
| [CHT-003 — Use the same approved assistant in every channel](#cht-003) | P1 · Required | Pending |
| [CHT-004 — Offer helpful chat actions and photo upload](#cht-004) | P1 · Required | Pending |
| [CHT-005 — Ask permission before texting a chat visitor](#cht-005) | P1 · Required | Pending |
| [CHT-006 — Keep the visitor's conversation together](#cht-006) | P1 · Required | Pending |
| [CHT-007 — Protect chat against spam and cost abuse](#cht-007) | P1 · Required | Pending |
| [CHT-008 — Let a human take over the chat](#cht-008) | P1 · Required | Pending |
| [CHT-009 — Keep text conversations together and honour STOP](#cht-009) | P1 · Required | Pending |
| [CHT-010 — Start chat with configured invitations](#cht-010) | P2 · Expected | Pending |
| [CHT-011 — Save chat and text outcomes in the inbox](#cht-011) | P1 · Required | Pending |
| [CHT-012 — Chat in the visitor's language](#cht-012) | P2 · Expected | Pending |
| [CHT-013 — Tell visitors they are speaking with AI](#cht-013) | P1 · Required | Pending |

[Back to the client board](#client-board)

## Module 09

**Human help and the operator desk**

A suitable person receives the right client context, handles safely and records the outcome.

**Suggested accountable role:** Operator experience / operations lead. Named owner and dates are not assigned.

**Planning status:** 43 cards Pending; no acceptance evidence recorded.

### 09.01

**Client context and operator authority**

**Suggested role(s):** Operator experience / operations lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDSK007["DSK-007 - Show the complete client context"]
        cardDSK008["DSK-008 - Enforce what the operator may promise or do"]
        cardDSK009["DSK-009 - Prevent operators from mixing up clients"]
        cardDSK010["DSK-010 - Mask information the operator does not need"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DSK-007 — Show the complete client context](#dsk-007) | P1 · Required | Pending |
| [DSK-008 — Enforce what the operator may promise or do](#dsk-008) | P1 · Required | Pending |
| [DSK-009 — Prevent operators from mixing up clients](#dsk-009) | P1 · Required | Pending |
| [DSK-010 — Mask information the operator does not need](#dsk-010) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 09.02

**Accessible desk and reconnect**

**Suggested role(s):** Operator experience / operations lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDSK025["DSK-025 - Make the desk easy to use by keyboard"]
        cardDSK026["DSK-026 - Restore the desk after a connection loss"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DSK-025 — Make the desk easy to use by keyboard](#dsk-025) | P1 · Expected | Pending |
| [DSK-026 — Restore the desk after a connection loss](#dsk-026) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 09.03

**Routing deadlines and fallback**

**Suggested role(s):** Operator experience / operations lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardHIL001["HIL-001 - Track every request for human help"]
        cardHIL002["HIL-002 - Route urgent requests within agreed service times"]
        cardHIL003["HIL-003 - Give a human-or-callback outcome"]
        cardHIL004["HIL-004 - Support live human takeover"]
        cardHIL005["HIL-005 - Handle escalations in the operator desk"]
        cardHIL006["HIL-006 - Route work to suitable, available people"]
        cardHIL007["HIL-007 - Approve sensitive actions before sending"]
        cardHIL015["HIL-015 - Notify the right people about escalations"]
        cardHIL016["HIL-016 - Provide a safe fallback when nobody answers"]
        cardHIL017["HIL-017 - Carry business identity through the handoff"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [HIL-001 — Track every request for human help](#hil-001) | P1 · Required | Pending |
| [HIL-002 — Route urgent requests within agreed service times](#hil-002) | P1 · Required | Pending |
| [HIL-003 — Give a human-or-callback outcome](#hil-003) | P1 · Required | Pending |
| [HIL-004 — Support live human takeover](#hil-004) | P1 · Required | Pending |
| [HIL-005 — Handle escalations in the operator desk](#hil-005) | P1 · Required | Pending |
| [HIL-006 — Route work to suitable, available people](#hil-006) | P1 · Required | Pending |
| [HIL-007 — Approve sensitive actions before sending](#hil-007) | P1 · Required | Pending |
| [HIL-015 — Notify the right people about escalations](#hil-015) | P1 · Required | Pending |
| [HIL-016 — Provide a safe fallback when nobody answers](#hil-016) | P1 · Expected | Pending |
| [HIL-017 — Carry business identity through the handoff](#hil-017) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 09.04

**Live call chat and callback controls**

**Suggested role(s):** Operator experience / operations lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDSK011["DSK-011 - Answer through a tested browser phone"]
        cardDSK012["DSK-012 - Provide the required call controls"]
        cardDSK013["DSK-013 - Handle chats and texts from the same desk"]
        cardDSK014["DSK-014 - Track availability and workload"]
        cardDSK015["DSK-015 - Suggest useful answers to operators"]
        cardDSK016["DSK-016 - Call back from the correct business line"]
        cardDSK017["DSK-017 - Match the caller's language"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DSK-011 — Answer through a tested browser phone](#dsk-011) | P1 · Required | Pending |
| [DSK-012 — Provide the required call controls](#dsk-012) | P1 · Required | Pending |
| [DSK-013 — Handle chats and texts from the same desk](#dsk-013) | P1 · Required | Pending |
| [DSK-014 — Track availability and workload](#dsk-014) | P1 · Required | Pending |
| [DSK-015 — Suggest useful answers to operators](#dsk-015) | P2 · Expected | Pending |
| [DSK-016 — Call back from the correct business line](#dsk-016) | P1 · Required | Pending |
| [DSK-017 — Match the caller's language](#dsk-017) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 09.05

**Instant client identification and greeting**

**Suggested role(s):** Operator experience / operations lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDSK004["DSK-004 - Show who the call is for immediately"]
        cardDSK005["DSK-005 - Brief the operator privately"]
        cardDSK006["DSK-006 - Show the right greeting script"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DSK-004 — Show who the call is for immediately](#dsk-004) | P1 · Required | Pending |
| [DSK-005 — Brief the operator privately](#dsk-005) | P1 · Required | Pending |
| [DSK-006 — Show the right greeting script](#dsk-006) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 09.06

**Client assignments and the shared queue**

**Suggested role(s):** Operator experience / operations lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDSK001["DSK-001 - Work from one operator queue"]
        cardDSK002["DSK-002 - Assign operators to permitted clients"]
        cardDSK003["DSK-003 - Identify which business was called"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DSK-001 — Work from one operator queue](#dsk-001) | P1 · Required | Pending |
| [DSK-002 — Assign operators to permitted clients](#dsk-002) | P1 · Required | Pending |
| [DSK-003 — Identify which business was called](#dsk-003) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 09.07

**Offers availability and wrap-up**

**Suggested role(s):** Operator experience / operations lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDSK018["DSK-018 - Handle offers, declines and timeouts reliably"]
        cardDSK019["DSK-019 - Record the outcome before finishing work"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DSK-018 — Handle offers, declines and timeouts reliably](#dsk-018) | P1 · Required | Pending |
| [DSK-019 — Record the outcome before finishing work](#dsk-019) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 09.08

**Human quality review and improvement**

**Suggested role(s):** Operator experience / operations lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardHIL008["HIL-008 - Let owners review and correct answers"]
        cardHIL009["HIL-009 - Review risky conversations for quality"]
        cardHIL010["HIL-010 - Turn reviewed outcomes into improvements"]
        cardHIL011["HIL-011 - Record every human intervention"]
        cardHIL012["HIL-012 - Measure human-handling usage"]
        cardHIL013["HIL-013 - Protect operator access"]
        cardHIL014["HIL-014 - Support separate partner operator teams"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [HIL-008 — Let owners review and correct answers](#hil-008) | P1 · Required | Pending |
| [HIL-009 — Review risky conversations for quality](#hil-009) | P2 · Required | Pending |
| [HIL-010 — Turn reviewed outcomes into improvements](#hil-010) | P2 · Required | Pending |
| [HIL-011 — Record every human intervention](#hil-011) | P1 · Required | Pending |
| [HIL-012 — Measure human-handling usage](#hil-012) | P2 · Required | Pending |
| [HIL-013 — Protect operator access](#hil-013) | P1 · Required | Pending |
| [HIL-014 — Support separate partner operator teams](#hil-014) | P2 · Expected | Pending |

[Back to the client board](#client-board)

### 09.09

**Supervision staffing and client visibility**

**Suggested role(s):** Operator experience / operations lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDSK020["DSK-020 - Give supervisors a live service overview"]
        cardDSK021["DSK-021 - Let supervisors assist with calls"]
        cardDSK022["DSK-022 - Plan staffing and shifts"]
        cardDSK023["DSK-023 - Show clients when a human handled a request"]
        cardDSK024["DSK-024 - Measure each handling stage"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DSK-020 — Give supervisors a live service overview](#dsk-020) | P2 · Required | Pending |
| [DSK-021 — Let supervisors assist with calls](#dsk-021) | P2 · Required | Pending |
| [DSK-022 — Plan staffing and shifts](#dsk-022) | P2 · Required | Pending |
| [DSK-023 — Show clients when a human handled a request](#dsk-023) | P1 · Required | Pending |
| [DSK-024 — Measure each handling stage](#dsk-024) | P1 · Required | Pending |

[Back to the client board](#client-board)

## Module 10

**Inbox, booking and follow-up**

The business can organise enquiries, book available times and follow up with permission.

**Suggested accountable role:** Workflow / booking lead. Named owner and dates are not assigned.

**Planning status:** 15 cards Pending; no acceptance evidence recorded.

### 10.01

**Requests appointments and follow-up**

**Suggested role(s):** Booking lead; Workflow / booking lead; Workflow lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardBKG001["BKG-001 - Connect the owner's calendar securely"]
        cardBKG002["BKG-002 - Offer appointments that fit business rules"]
        cardBKG003["BKG-003 - Prevent two people booking the same slot"]
        cardBKG004["BKG-004 - Confirm, remind and change appointments"]
        cardBKG005["BKG-005 - Connect field-service systems in the later phase"]
        cardFUP001["FUP-001 - Follow up with customers automatically"]
        cardFUP002["FUP-002 - Request reviews under an approved policy"]
        cardFUP003["FUP-003 - Show the enquiry-to-job pipeline"]
        cardINB001["INB-001 - See all customer requests in one inbox"]
        cardINB002["INB-002 - Review the complete conversation"]
        cardINB003["INB-003 - Reply to a customer from the inbox"]
        cardINB004["INB-004 - Assign work, add notes and call back"]
        cardINB005["INB-005 - Merge duplicate contacts safely"]
        cardINB006["INB-006 - Choose notification preferences"]
        cardINB007["INB-007 - Export requests or connect other tools"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [BKG-001 — Connect the owner's calendar securely](#bkg-001) | P1 · Required | Pending |
| [BKG-002 — Offer appointments that fit business rules](#bkg-002) | P1 · Required | Pending |
| [BKG-003 — Prevent two people booking the same slot](#bkg-003) | P1 · Required | Pending |
| [BKG-004 — Confirm, remind and change appointments](#bkg-004) | P1 · Required | Pending |
| [BKG-005 — Connect field-service systems in the later phase](#bkg-005) | P3 · Optional | Pending |
| [FUP-001 — Follow up with customers automatically](#fup-001) | P2 · Required | Pending |
| [FUP-002 — Request reviews under an approved policy](#fup-002) | P2 · Required | Pending |
| [FUP-003 — Show the enquiry-to-job pipeline](#fup-003) | P2 · Expected | Pending |
| [INB-001 — See all customer requests in one inbox](#inb-001) | P1 · Required | Pending |
| [INB-002 — Review the complete conversation](#inb-002) | P1 · Required | Pending |
| [INB-003 — Reply to a customer from the inbox](#inb-003) | P1 · Required | Pending |
| [INB-004 — Assign work, add notes and call back](#inb-004) | P1 · Required | Pending |
| [INB-005 — Merge duplicate contacts safely](#inb-005) | P1 · Required | Pending |
| [INB-006 — Choose notification preferences](#inb-006) | P1 · Required | Pending |
| [INB-007 — Export requests or connect other tools](#inb-007) | P1 · Expected | Pending |

[Back to the client board](#client-board)

## Module 11

**Business websites**

Owners receive truthful, fast websites they can review, approve, edit and publish safely.

**Suggested accountable role:** Website product / engineering lead. Named owner and dates are not assigned.

**Planning status:** 18 cards Pending; no acceptance evidence recorded.

### 11.01

**Website generation editing and delivery**

**Suggested role(s):** Website product / engineering lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardWEB001["WEB-001 - Generate a complete private website preview"]
        cardWEB002["WEB-002 - Use only truthful business claims"]
        cardWEB003["WEB-003 - Keep unapproved previews private"]
        cardWEB004["WEB-004 - Connect a domain with automatic security"]
        cardWEB005["WEB-005 - Isolate customer websites from platform domains"]
        cardWEB006["WEB-006 - Make sites fast and search-ready"]
        cardWEB007["WEB-007 - Include chat, calls and enquiry forms"]
        cardWEB008["WEB-008 - Let owners edit and undo site changes"]
        cardWEB009["WEB-009 - Prevent unsafe website content"]
        cardWEB010["WEB-010 - Show where website enquiries come from"]
        cardWEB011["WEB-011 - Update many sites safely"]
        cardWEB012["WEB-012 - Create useful service and area pages"]
        cardWEB013["WEB-013 - Prevent fake sites and handle abuse reports"]
        cardWEB014["WEB-014 - Serve sites quickly and refresh changes"]
        cardWEB015["WEB-015 - Support English and Spanish websites"]
        cardWEB016["WEB-016 - Use the right industry website content"]
        cardWEB017["WEB-017 - Show the correct brand and legal identity"]
        cardWEB018["WEB-018 - Add the website features each industry needs"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [WEB-001 — Generate a complete private website preview](#web-001) | P1 · Required | Pending |
| [WEB-002 — Use only truthful business claims](#web-002) | P1 · Required | Pending |
| [WEB-003 — Keep unapproved previews private](#web-003) | P1 · Required | Pending |
| [WEB-004 — Connect a domain with automatic security](#web-004) | P1 · Required | Pending |
| [WEB-005 — Isolate customer websites from platform domains](#web-005) | P1 · Required | Pending |
| [WEB-006 — Make sites fast and search-ready](#web-006) | P1 · Required | Pending |
| [WEB-007 — Include chat, calls and enquiry forms](#web-007) | P1 · Required | Pending |
| [WEB-008 — Let owners edit and undo site changes](#web-008) | P1 · Required | Pending |
| [WEB-009 — Prevent unsafe website content](#web-009) | P1 · Required | Pending |
| [WEB-010 — Show where website enquiries come from](#web-010) | P1 · Required | Pending |
| [WEB-011 — Update many sites safely](#web-011) | P2 · Required | Pending |
| [WEB-012 — Create useful service and area pages](#web-012) | P2 · Expected | Pending |
| [WEB-013 — Prevent fake sites and handle abuse reports](#web-013) | P1 · Required | Pending |
| [WEB-014 — Serve sites quickly and refresh changes](#web-014) | P1 · Required | Pending |
| [WEB-015 — Support English and Spanish websites](#web-015) | P2 · Expected | Pending |
| [WEB-016 — Use the right industry website content](#web-016) | P1 · Required | Pending |
| [WEB-017 — Show the correct brand and legal identity](#web-017) | P1 · Required | Pending |
| [WEB-018 — Add the website features each industry needs](#web-018) | P2 · Expected | Pending |

[Back to the client board](#client-board)

## Module 12

**Billing, brands, growth and integrations**

The shared platform supports plans, brands, reporting, switching customers and later pickup ordering.

**Suggested accountable role:** Product lead with workstream specialists. Named owner and dates are not assigned.

**Planning status:** 97 cards Pending; no acceptance evidence recorded.

### 12.01

**Protected administration**

**Suggested role(s):** Administration lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardADM001["ADM-001 - Provide a protected administration workspace"]
        cardADM002["ADM-002 - Control rollouts and stop faulty features"]
        cardADM003["ADM-003 - Review and release AI policy changes"]
        cardADM004["ADM-004 - Track costs and unusual spending"]
        cardADM005["ADM-005 - Manage phone numbers and registrations"]
        cardADM006["ADM-006 - Preview and audit bulk administration"]
        cardADM007["ADM-007 - Respond to a service incident"]
        cardADM008["ADM-008 - Manage brands, prospects and migration work"]
        cardADM009["ADM-009 - Show industry launch-readiness evidence"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [ADM-001 — Provide a protected administration workspace](#adm-001) | P1 · Required | Pending |
| [ADM-002 — Control rollouts and stop faulty features](#adm-002) | P1 · Required | Pending |
| [ADM-003 — Review and release AI policy changes](#adm-003) | P1 · Required | Pending |
| [ADM-004 — Track costs and unusual spending](#adm-004) | P1 · Required | Pending |
| [ADM-005 — Manage phone numbers and registrations](#adm-005) | P1 · Required | Pending |
| [ADM-006 — Preview and audit bulk administration](#adm-006) | P2 · Expected | Pending |
| [ADM-007 — Respond to a service incident](#adm-007) | P1 · Required | Pending |
| [ADM-008 — Manage brands, prospects and migration work](#adm-008) | P1 · Required | Pending |
| [ADM-009 — Show industry launch-readiness evidence](#adm-009) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 12.02

**Outcome and quality reporting**

**Suggested role(s):** Analytics lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardANL001["ANL-001 - Show owners the value they receive"]
        cardANL002["ANL-002 - Build reliable reporting from platform events"]
        cardANL003["ANL-003 - Show service quality and provider health"]
        cardANL004["ANL-004 - Understand onboarding conversion"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [ANL-001 — Show owners the value they receive](#anl-001) | P1 · Required | Pending |
| [ANL-002 — Build reliable reporting from platform events](#anl-002) | P1 · Required | Pending |
| [ANL-003 — Show service quality and provider health](#anl-003) | P1 · Required | Pending |
| [ANL-004 — Understand onboarding conversion](#anl-004) | P2 · Expected | Pending |

[Back to the client board](#client-board)

### 12.03

**Plans payments and usage**

**Suggested role(s):** Billing lead with product-owner pricing decisions. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardBIL001["BIL-001 - Define plans and allowances as data"]
        cardBIL002["BIL-002 - Let customers pay through hosted checkout"]
        cardBIL003["BIL-003 - Keep payment-provider state in sync"]
        cardBIL004["BIL-004 - Show accurate usage and allowance alerts"]
        cardBIL005["BIL-005 - Apply plan limits without blocking emergencies"]
        cardBIL006["BIL-006 - Add approved outcome-based charges"]
        cardBIL007["BIL-007 - Measure the cost of serving each business"]
        cardBIL008["BIL-008 - Support reseller billing in the later phase"]
        cardBIL009["BIL-009 - Keep brand prices and offers consistent"]
        cardBIL010["BIL-010 - Add ordering and human-handling fee components"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [BIL-001 — Define plans and allowances as data](#bil-001) | P1 · Required | Pending |
| [BIL-002 — Let customers pay through hosted checkout](#bil-002) | P1 · Required | Pending |
| [BIL-003 — Keep payment-provider state in sync](#bil-003) | P1 · Required | Pending |
| [BIL-004 — Show accurate usage and allowance alerts](#bil-004) | P1 · Required | Pending |
| [BIL-005 — Apply plan limits without blocking emergencies](#bil-005) | P1 · Required | Pending |
| [BIL-006 — Add approved outcome-based charges](#bil-006) | P2 · Expected | Pending |
| [BIL-007 — Measure the cost of serving each business](#bil-007) | P1 · Required | Pending |
| [BIL-008 — Support reseller billing in the later phase](#bil-008) | P3 · Optional | Pending |
| [BIL-009 — Keep brand prices and offers consistent](#bil-009) | P1 · Required | Pending |
| [BIL-010 — Add ordering and human-handling fee components](#bil-010) | P2 · Expected | Pending |

[Back to the client board](#client-board)

### 12.04

**Industry brands and launch readiness**

**Suggested role(s):** Vertical manager and product owner. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardVRT001["VRT-001 - Define each brand's identity"]
        cardVRT002["VRT-002 - Apply the brand throughout the experience"]
        cardVRT003["VRT-003 - Package an industry as versioned configuration"]
        cardVRT004["VRT-004 - Run two brands and two packs in the pilot"]
        cardVRT005["VRT-005 - Approve an industry before launching it"]
        cardVRT006["VRT-006 - Capture industry-specific request details"]
        cardVRT007["VRT-007 - Provide brand-specific operator defaults"]
        cardVRT008["VRT-008 - Share one engine across brands"]
        cardVRT009["VRT-009 - Name the contracting business correctly"]
        cardVRT010["VRT-010 - Maintain and review industry packs"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [VRT-001 — Define each brand's identity](#vrt-001) | P1 · Required | Pending |
| [VRT-002 — Apply the brand throughout the experience](#vrt-002) | P1 · Required | Pending |
| [VRT-003 — Package an industry as versioned configuration](#vrt-003) | P1 · Required | Pending |
| [VRT-004 — Run two brands and two packs in the pilot](#vrt-004) | P1 · Required | Pending |
| [VRT-005 — Approve an industry before launching it](#vrt-005) | P1 · Required | Pending |
| [VRT-006 — Capture industry-specific request details](#vrt-006) | P1 · Required | Pending |
| [VRT-007 — Provide brand-specific operator defaults](#vrt-007) | P2 · Expected | Pending |
| [VRT-008 — Share one engine across brands](#vrt-008) | P1 · Required | Pending |
| [VRT-009 — Name the contracting business correctly](#vrt-009) | P1 · Required | Pending |
| [VRT-010 — Maintain and review industry packs](#vrt-010) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 12.05

**Consent privacy and industry rules**

**Suggested role(s):** Privacy / compliance lead with required counsel review. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardCOM001["COM-001 - Keep proof of consent and opt-out"]
        cardCOM002["COM-002 - Enforce texting permissions and STOP"]
        cardCOM003["COM-003 - Disclose AI use as required"]
        cardCOM004["COM-004 - Record calls only under the applicable rules"]
        cardCOM005["COM-005 - Track carrier-compliance work"]
        cardCOM006["COM-006 - Publish correct client legal pages"]
        cardCOM007["COM-007 - Remove personal details from secondary records"]
        cardCOM008["COM-008 - Keep and delete data under approved policies"]
        cardCOM009["COM-009 - Handle customers' privacy-rights requests"]
        cardCOM010["COM-010 - Prepare the later HIPAA-ready mode"]
        cardCOM011["COM-011 - Track provider agreements"]
        cardCOM012["COM-012 - Require review for high-risk outbound activity"]
        cardCOM013["COM-013 - Make the platform accessible"]
        cardCOM014["COM-014 - Apply the right compliance profile"]
        cardCOM015["COM-015 - Gate health-care features on required agreements"]
        cardCOM016["COM-016 - Enforce professional-services intake limits"]
        cardCOM017["COM-017 - Use safe advice limits in every industry"]
        cardCOM018["COM-018 - Maintain reviewed state and industry rule tables"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [COM-001 — Keep proof of consent and opt-out](#com-001) | P1 · Required | Pending |
| [COM-002 — Enforce texting permissions and STOP](#com-002) | P1 · Required | Pending |
| [COM-003 — Disclose AI use as required](#com-003) | P1 · Required | Pending |
| [COM-004 — Record calls only under the applicable rules](#com-004) | P1 · Required | Pending |
| [COM-005 — Track carrier-compliance work](#com-005) | P1 · Required | Pending |
| [COM-006 — Publish correct client legal pages](#com-006) | P1 · Required | Pending |
| [COM-007 — Remove personal details from secondary records](#com-007) | P1 · Required | Pending |
| [COM-008 — Keep and delete data under approved policies](#com-008) | P1 · Required | Pending |
| [COM-009 — Handle customers' privacy-rights requests](#com-009) | P1 · Required | Pending |
| [COM-010 — Prepare the later HIPAA-ready mode](#com-010) | P2 · Expected | Pending |
| [COM-011 — Track provider agreements](#com-011) | P2 · Expected | Pending |
| [COM-012 — Require review for high-risk outbound activity](#com-012) | P3 · Required | Pending |
| [COM-013 — Make the platform accessible](#com-013) | P1 · Required | Pending |
| [COM-014 — Apply the right compliance profile](#com-014) | P1 · Required | Pending |
| [COM-015 — Gate health-care features on required agreements](#com-015) | P3 · Required | Pending |
| [COM-016 — Enforce professional-services intake limits](#com-016) | P2 · Required | Pending |
| [COM-017 — Use safe advice limits in every industry](#com-017) | P1 · Required | Pending |
| [COM-018 — Maintain reviewed state and industry rule tables](#com-018) | P2 · Required | Pending |

[Back to the client board](#client-board)

### 12.06

**Competitor prospects and permitted outreach**

**Suggested role(s):** Acquisition lead with required compliance review. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardACQ001["ACQ-001 - Record competitor targets and playbooks"]
        cardACQ002["ACQ-002 - Import prospects from permitted sources"]
        cardACQ003["ACQ-003 - Keep a complete prospect record"]
        cardACQ004["ACQ-004 - Explain how prospects are prioritised"]
        cardACQ005["ACQ-005 - Track the prospect-to-customer journey"]
        cardACQ006["ACQ-006 - Prepare a private, personalised demonstration"]
        cardACQ007["ACQ-007 - Show an honest switching-cost comparison"]
        cardACQ008["ACQ-008 - Use reviewed outreach channels"]
        cardACQ009["ACQ-009 - Record prospect contact preferences"]
        cardACQ010["ACQ-010 - Keep evidence for marketing claims"]
        cardACQ011["ACQ-011 - Protect and expire prospect information"]
        cardACQ012["ACQ-012 - Measure acquisition results"]
        cardACQ013["ACQ-013 - Review changing source information"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [ACQ-001 — Record competitor targets and playbooks](#acq-001) | P1 · Required | Pending |
| [ACQ-002 — Import prospects from permitted sources](#acq-002) | P1 · Required | Pending |
| [ACQ-003 — Keep a complete prospect record](#acq-003) | P1 · Required | Pending |
| [ACQ-004 — Explain how prospects are prioritised](#acq-004) | P1 · Expected | Pending |
| [ACQ-005 — Track the prospect-to-customer journey](#acq-005) | P1 · Required | Pending |
| [ACQ-006 — Prepare a private, personalised demonstration](#acq-006) | P1 · Required | Pending |
| [ACQ-007 — Show an honest switching-cost comparison](#acq-007) | P1 · Required | Pending |
| [ACQ-008 — Use reviewed outreach channels](#acq-008) | P1 · Required | Pending |
| [ACQ-009 — Record prospect contact preferences](#acq-009) | P1 · Required | Pending |
| [ACQ-010 — Keep evidence for marketing claims](#acq-010) | P1 · Required | Pending |
| [ACQ-011 — Protect and expire prospect information](#acq-011) | P1 · Expected | Pending |
| [ACQ-012 — Measure acquisition results](#acq-012) | P2 · Expected | Pending |
| [ACQ-013 — Review changing source information](#acq-013) | P2 · Optional | Pending |

[Back to the client board](#client-board)

### 12.07

**Approved connections and fallback**

**Suggested role(s):** Integration lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardINT001["INT-001 - Use a standard connection framework"]
        cardINT002["INT-002 - Show which connections are available"]
        cardINT003["INT-003 - Keep working when no connector is available"]
        cardINT004["INT-004 - Track provider-access approvals"]
        cardINT005["INT-005 - Apply privacy rules to connected services"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [INT-001 — Use a standard connection framework](#int-001) | P1 · Required | Pending |
| [INT-002 — Show which connections are available](#int-002) | P1 · Expected | Pending |
| [INT-003 — Keep working when no connector is available](#int-003) | P1 · Required | Pending |
| [INT-004 — Track provider-access approvals](#int-004) | P2 · Expected | Pending |
| [INT-005 — Apply privacy rules to connected services](#int-005) | P2 · Required | Pending |

[Back to the client board](#client-board)

### 12.08

**Authorised customer migration**

**Suggested role(s):** Migration lead with client authorisation. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardMIG001["MIG-001 - Plan the customer's move from an incumbent"]
        cardMIG002["MIG-002 - Import the customer's permitted website content"]
        cardMIG003["MIG-003 - Guide domain and account ownership changes"]
        cardMIG004["MIG-004 - Run in parallel and switch with rollback"]
        cardMIG005["MIG-005 - Keep the customer's phone service working"]
        cardMIG006["MIG-006 - Record contract terms and switching fees"]
        cardMIG007["MIG-007 - Move data only with customer authorisation"]
        cardMIG008["MIG-008 - Preserve useful search and listing links"]
        cardMIG009["MIG-009 - Measure migration quality"]
        cardMIG010["MIG-010 - Maintain reusable migration playbooks"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [MIG-001 — Plan the customer's move from an incumbent](#mig-001) | P1 · Required | Pending |
| [MIG-002 — Import the customer's permitted website content](#mig-002) | P1 · Required | Pending |
| [MIG-003 — Guide domain and account ownership changes](#mig-003) | P1 · Required | Pending |
| [MIG-004 — Run in parallel and switch with rollback](#mig-004) | P1 · Required | Pending |
| [MIG-005 — Keep the customer's phone service working](#mig-005) | P1 · Required | Pending |
| [MIG-006 — Record contract terms and switching fees](#mig-006) | P1 · Required | Pending |
| [MIG-007 — Move data only with customer authorisation](#mig-007) | P1 · Required | Pending |
| [MIG-008 — Preserve useful search and listing links](#mig-008) | P1 · Expected | Pending |
| [MIG-009 — Measure migration quality](#mig-009) | P2 · Expected | Pending |
| [MIG-010 — Maintain reusable migration playbooks](#mig-010) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 12.09

**Restaurant pickup ordering**

**Suggested role(s):** Restaurant product / engineering lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardORD001["ORD-001 - Manage the restaurant's real menu"]
        cardORD002["ORD-002 - Let customers order pickup online"]
        cardORD003["ORD-003 - Take phone orders with full read-back"]
        cardORD004["ORD-004 - Deliver orders and obtain kitchen acceptance"]
        cardORD005["ORD-005 - Connect approved point-of-sale systems"]
        cardORD006["ORD-006 - Keep payments on hosted pages"]
        cardORD007["ORD-007 - Review order accuracy before wider launch"]
        cardORD008["ORD-008 - Update the restaurant's public ordering links"]
        cardORD009["ORD-009 - Apply the agreed restaurant fee model"]
        cardORD010["ORD-010 - Export restaurant data with consent history"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [ORD-001 — Manage the restaurant's real menu](#ord-001) | P2 · Required | Pending |
| [ORD-002 — Let customers order pickup online](#ord-002) | P2 · Required | Pending |
| [ORD-003 — Take phone orders with full read-back](#ord-003) | P2 · Required | Pending |
| [ORD-004 — Deliver orders and obtain kitchen acceptance](#ord-004) | P2 · Required | Pending |
| [ORD-005 — Connect approved point-of-sale systems](#ord-005) | P2 · Expected | Pending |
| [ORD-006 — Keep payments on hosted pages](#ord-006) | P2 · Required | Pending |
| [ORD-007 — Review order accuracy before wider launch](#ord-007) | P2 · Required | Pending |
| [ORD-008 — Update the restaurant's public ordering links](#ord-008) | P2 · Expected | Pending |
| [ORD-009 — Apply the agreed restaurant fee model](#ord-009) | P2 · Expected | Pending |
| [ORD-010 — Export restaurant data with consent history](#ord-010) | P2 · Required | Pending |

[Back to the client board](#client-board)

### 12.10

**Public API and reliable notifications**

**Suggested role(s):** API lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardAPI001["API-001 - Publish a documented integration API"]
        cardAPI002["API-002 - Secure user, integration and widget access"]
        cardAPI003["API-003 - Notify connected systems reliably"]
        cardAPI004["API-004 - Connect workflow-automation tools"]
        cardAPI005["API-005 - Deliver integrations in their stated phases"]
        cardAPI006["API-006 - Keep dashboards updated live"]
        cardAPI007["API-007 - Give notice before breaking integrations"]
        cardAPI008["API-008 - Review partner apps before access"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [API-001 — Publish a documented integration API](#api-001) | P1 · Required | Pending |
| [API-002 — Secure user, integration and widget access](#api-002) | P1 · Required | Pending |
| [API-003 — Notify connected systems reliably](#api-003) | P1 · Required | Pending |
| [API-004 — Connect workflow-automation tools](#api-004) | P1 · Expected | Pending |
| [API-005 — Deliver integrations in their stated phases](#api-005) | P2 · Expected | Pending |
| [API-006 — Keep dashboards updated live](#api-006) | P1 · Required | Pending |
| [API-007 — Give notice before breaking integrations](#api-007) | P1 · Required | Pending |
| [API-008 — Review partner apps before access](#api-008) | P3 · Optional | Pending |

[Back to the client board](#client-board)

## Module 13

**Security and future readiness**

Client information and accounts stay protected, with tested recovery and incident procedures.

**Suggested accountable role:** Security / privacy lead. Named owner and dates are not assigned.

**Planning status:** 18 cards Pending; no acceptance evidence recorded.

### 13.01

**Security controls and incident readiness**

**Suggested role(s):** Security lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardSEC001["SEC-001 - Review threats throughout development"]
        cardSEC002["SEC-002 - Separate network tiers and service access"]
        cardSEC003["SEC-003 - Secure logins and sessions"]
        cardSEC004["SEC-004 - Encrypt data while it travels"]
        cardSEC005["SEC-005 - Encrypt stored data with business-specific keys"]
        cardSEC006["SEC-006 - Store and rotate secrets securely"]
        cardSEC007["SEC-007 - Validate all incoming information"]
        cardSEC008["SEC-008 - Limit abuse and fraudulent usage"]
        cardSEC009["SEC-009 - Keep a tamper-evident audit trail"]
        cardSEC010["SEC-010 - Check software and container provenance"]
        cardSEC011["SEC-011 - Fix vulnerabilities within agreed deadlines"]
        cardSEC012["SEC-012 - Detect suspicious activity from security logs"]
        cardSEC013["SEC-013 - Prove backup and recovery protection"]
        cardSEC014["SEC-014 - Continuously test business isolation"]
        cardSEC015["SEC-015 - Test attacks against the AI"]
        cardSEC016["SEC-016 - Prepare the staged compliance programme"]
        cardSEC017["SEC-017 - Build privacy into the data lifecycle"]
        cardSEC018["SEC-018 - Prepare and rehearse incident response"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [SEC-001 — Review threats throughout development](#sec-001) | P0 · Required | Pending |
| [SEC-002 — Separate network tiers and service access](#sec-002) | P1 · Required | Pending |
| [SEC-003 — Secure logins and sessions](#sec-003) | P1 · Required | Pending |
| [SEC-004 — Encrypt data while it travels](#sec-004) | P1 · Required | Pending |
| [SEC-005 — Encrypt stored data with business-specific keys](#sec-005) | P1 · Required | Pending |
| [SEC-006 — Store and rotate secrets securely](#sec-006) | P1 · Required | Pending |
| [SEC-007 — Validate all incoming information](#sec-007) | P1 · Required | Pending |
| [SEC-008 — Limit abuse and fraudulent usage](#sec-008) | P1 · Required | Pending |
| [SEC-009 — Keep a tamper-evident audit trail](#sec-009) | P1 · Required | Pending |
| [SEC-010 — Check software and container provenance](#sec-010) | P1 · Required | Pending |
| [SEC-011 — Fix vulnerabilities within agreed deadlines](#sec-011) | P1 · Required | Pending |
| [SEC-012 — Detect suspicious activity from security logs](#sec-012) | P1 · Required | Pending |
| [SEC-013 — Prove backup and recovery protection](#sec-013) | P1 · Required | Pending |
| [SEC-014 — Continuously test business isolation](#sec-014) | P1 · Required | Pending |
| [SEC-015 — Test attacks against the AI](#sec-015) | P1 · Required | Pending |
| [SEC-016 — Prepare the staged compliance programme](#sec-016) | P2 · Required | Pending |
| [SEC-017 — Build privacy into the data lifecycle](#sec-017) | P1 · Required | Pending |
| [SEC-018 — Prepare and rehearse incident response](#sec-018) | P1 · Required | Pending |

[Back to the client board](#client-board)

## Module 14

**Performance, reliability and operating costs**

Measured tests prove speed, capacity, continuity and commercially sustainable costs.

**Suggested accountable role:** Reliability / performance lead. Named owner and dates are not assigned.

**Planning status:** 13 cards Pending; no acceptance evidence recorded.

### 14.01

**Load failure and endurance tests**

**Suggested role(s):** Reliability / performance lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardLT001["LT-001 - Prove the P1 call-load target"]
        cardLT002["LT-002 - Prove P2 scale and sustained operation"]
        cardLT003["LT-003 - Prove large-scale website generation"]
        cardLT004["LT-004 - Prove inbox and API performance at scale"]
        cardLT005["LT-005 - Test service failures under load"]
        cardLT006["LT-006 - Prove the operator desk under heavy load"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [LT-001 — Prove the P1 call-load target](#lt-001) | P1 · Required | Pending |
| [LT-002 — Prove P2 scale and sustained operation](#lt-002) | P2 · Required | Pending |
| [LT-003 — Prove large-scale website generation](#lt-003) | P2 · Required | Pending |
| [LT-004 — Prove inbox and API performance at scale](#lt-004) | P2 · Required | Pending |
| [LT-005 — Test service failures under load](#lt-005) | P1 · Required | Pending |
| [LT-006 — Prove the operator desk under heavy load](#lt-006) | P2 · Required | Pending |

[Back to the client board](#client-board)

### 14.02

**Provider costs limits and margins**

**Suggested role(s):** Product / cost lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardCST001["CST-001 - Measure voice cost before choosing vendors"]
        cardCST002["CST-002 - Control budgets and show margins"]
        cardCST003["CST-003 - Reduce AI costs without losing quality"]
        cardCST004["CST-004 - Avoid charging for abandoned calls"]
        cardCST005["CST-005 - Evaluate later self-hosted AI options"]
        cardCST006["CST-006 - Define included minutes and fair use"]
        cardCST007["CST-007 - Measure the cost of human handling"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [CST-001 — Measure voice cost before choosing vendors](#cst-001) | P0 · Required | Pending |
| [CST-002 — Control budgets and show margins](#cst-002) | P1 · Required | Pending |
| [CST-003 — Reduce AI costs without losing quality](#cst-003) | P1 · Required | Pending |
| [CST-004 — Avoid charging for abandoned calls](#cst-004) | P1 · Required | Pending |
| [CST-005 — Evaluate later self-hosted AI options](#cst-005) | P2 · Expected | Pending |
| [CST-006 — Define included minutes and fair use](#cst-006) | P1 · Required | Pending |
| [CST-007 — Measure the cost of human handling](#cst-007) | P2 · Required | Pending |

[Back to the client board](#client-board)

## Module 15

**Testing, release and client acceptance**

Releases have quality evidence, client acceptance and complete operational handover.

**Suggested accountable role:** Quality / delivery lead. Named owner and dates are not assigned.

**Planning status:** 19 cards Pending; no acceptance evidence recorded.

### 15.01

**AI accuracy safety and release gates**

**Suggested role(s):** AI quality lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardEVL001["EVL-001 - Build text and phone evaluation tools"]
        cardEVL002["EVL-002 - Create realistic industry test conversations"]
        cardEVL003["EVL-003 - Measure AI accuracy, safety, speed and cost"]
        cardEVL004["EVL-004 - Check automated judges against people"]
        cardEVL005["EVL-005 - Block AI releases that fail quality gates"]
        cardEVL006["EVL-006 - Try AI changes safely before wide release"]
        cardEVL007["EVL-007 - Monitor AI quality after launch"]
        cardEVL008["EVL-008 - Add approved corrections to test data"]
        cardEVL009["EVL-009 - Review adversarial-test results before release"]
        cardEVL010["EVL-010 - Verify every new industry's AI readiness"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [EVL-001 — Build text and phone evaluation tools](#evl-001) | P0 · Required | Pending |
| [EVL-002 — Create realistic industry test conversations](#evl-002) | P1 · Required | Pending |
| [EVL-003 — Measure AI accuracy, safety, speed and cost](#evl-003) | P1 · Required | Pending |
| [EVL-004 — Check automated judges against people](#evl-004) | P1 · Required | Pending |
| [EVL-005 — Block AI releases that fail quality gates](#evl-005) | P1 · Required | Pending |
| [EVL-006 — Try AI changes safely before wide release](#evl-006) | P1 · Required | Pending |
| [EVL-007 — Monitor AI quality after launch](#evl-007) | P2 · Required | Pending |
| [EVL-008 — Add approved corrections to test data](#evl-008) | P2 · Required | Pending |
| [EVL-009 — Review adversarial-test results before release](#evl-009) | P1 · Required | Pending |
| [EVL-010 — Verify every new industry's AI readiness](#evl-010) | P1 · Required | Pending |

[Back to the client board](#client-board)

### 15.02

**Build and release pipeline**

**Suggested role(s):** Quality / delivery lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDEL001["DEL-001 - Automate the required build checks"]
        cardDEL002["DEL-002 - Promote releases with tests and rollback"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DEL-001 — Automate the required build checks](#del-001) | P0 · Supporting | Pending |
| [DEL-002 — Promote releases with tests and rollback](#del-002) | P0 / P1 / P2 · Supporting | Pending |

[Back to the client board](#client-board)

### 15.03

**Verification and observability**

**Suggested role(s):** Quality / delivery lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDEL003["DEL-003 - Complete the full verification programme"]
        cardDEL004["DEL-004 - Provide actionable dashboards and alerts"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DEL-003 — Complete the full verification programme](#del-003) | P0 / P1 / P2 / P3 · Supporting | Pending |
| [DEL-004 — Provide actionable dashboards and alerts](#del-004) | P0 / P1 / P2 · Supporting | Pending |

[Back to the client board](#client-board)

### 15.04

**Documentation standards and handover**

**Suggested role(s):** Quality / delivery lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDEL005["DEL-005 - Deliver documentation and operational runbooks"]
        cardDEL006["DEL-006 - Apply coding and module-boundary standards"]
        cardDEL008["DEL-008 - Arrange ownership access and handover"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DEL-005 — Deliver documentation and operational runbooks](#del-005) | P0 / P1 / P2 · Supporting | Pending |
| [DEL-006 — Apply coding and module-boundary standards](#del-006) | P0 · Supporting | Pending |
| [DEL-008 — Arrange ownership access and handover](#del-008) | P0 / P1 / P2 · Supporting | Pending |

[Back to the client board](#client-board)

### 15.05

**Acceptance and delivery planning**

**Suggested role(s):** Quality / delivery lead. Named owners: to assign.

```mermaid
kanban
    pending[Pending]
        cardDEL007["DEL-007 - Record feature completion and client acceptance"]
        cardDEL009["DEL-009 - Agree delivery estimates responsibilities and risks"]
    working[In Progress]
    deploy[Ready for Deploy]
    test[Ready for Test]
    done[Done]
```

| Ticket — short deliverable | Phase · priority | Status |
| --- | --- | --- |
| [DEL-007 — Record feature completion and client acceptance](#del-007) | P0 / P1 / P2 / P3 · Supporting | Pending |
| [DEL-009 — Agree delivery estimates responsibilities and risks](#del-009) | P0 · Supporting | Pending |

[Back to the client board](#client-board)

## Ticket details

The short check makes client review easier. It is additional guidance and never narrows the full source requirement. Official AT links are inherited through the specification's business traceability; a linked scenario may cover several tickets. Every ticket still needs its own applicable verification evidence.

Delivery records are deliberately unfilled planning fields. A suggested role is not a named assignment, and a source default is not a recorded approval.

### ACC-001

**Deliverable:** Check permissions on every request

**P1 · MUST · Pending**

**Check:** A user or operator cannot view or change a business unless their role and client assignment permit it.

**Owner:** To assign.

**Source:** Technical specification §10.3 Access requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [DSK-002](#dsk-002).

**Full source text:**

> ACC-001 [P1] MUST enforce authorization in a single policy layer (not scattered in handlers). Every request carries a resolved tenant_id and actor; operator requests additionally carry the operator's client grant (DSK-002).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACC-002

**Deliverable:** Record and control support access

**P1 · MUST · Pending**

**Check:** Support access records who accessed which business and why; impersonation is visible and can be stopped.

**Owner:** To assign.

**Source:** Technical specification §10.3 Access requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ACC-002 [P1] MUST log every cross-client access by internal staff and operators to an append-only audit log with reason code. Support impersonation MUST show a banner to the client user and be revocable.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACC-003

**Deliverable:** Protect accounts with a second login check

**P1 · MUST · Pending**

**Check:** Internal staff and operators use multi-factor authentication; client requirements follow the stated phase.

**Owner:** To assign.

**Source:** Technical specification §10.3 Access requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ACC-003 [P1] MUST support multi-factor authentication for all internal roles and operators and offer it to clients (mandatory for tenant_owner on paid plans at P2).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACC-004

**Deliverable:** Use one trusted staff login

**P2 · SHOULD · Pending**

**Check:** Internal single sign-on works; the later client single sign-on option has a documented integration point.

**Owner:** To assign.

**Source:** Technical specification §10.3 Access requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ACC-004 [P2] SHOULD support single sign-on (OIDC or SAML) for internal roles; scaffold client single sign-on for P3.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACC-005

**Deliverable:** Control integration access keys

**P1 · MUST · Pending**

**Check:** A business can revoke or replace an integration key and see when it was last used.

**Owner:** To assign.

**Source:** Technical specification §10.3 Access requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ACC-005 [P1] MUST issue scoped, revocable API keys per client with rotation and last-used tracking.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACC-006

**Deliverable:** Separate brand and growth-team permissions

**P1 · MUST · Pending**

**Check:** Brand access stays separate; acquisition and migration staff cannot read client conversations, recordings or transcripts.

**Owner:** To assign.

**Source:** Technical specification §10.3 Access requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ACC-006 [P1] MUST support brand-scoped and vertical-scoped roles (brand_admin, vertical_manager, acquisition_manager, migration_specialist) with least privilege; acquisition and migration roles MUST NOT be able to read clients' conversations, recordings or transcripts.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AR-001

**Deliverable:** Record and approve the platform design decisions

**P0 · MUST · Pending**

**Check:** Written records cover every source decision before the P1 build; approvals follow each decision's owner and deadline.

**Owner:** To assign.

**Source:** Technical specification §11.7 Architecture requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> AR-001 [P0] MUST deliver a written architecture decision record (ADR) set covering every "Decision" in this document, before P1 build starts.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AR-002

**Deliverable:** Keep service providers replaceable

**P0 · MUST · Pending**

**Check:** Provider contracts and alternative implementations meet the P1 telephony/LLM and P2 remaining-provider deadlines.

**Owner:** To assign.

**Source:** Technical specification §11.7 Architecture requirements.

**Business links:** [BR-075](#br-075).

**Official acceptance links:** [AT-60](#at-60).

**Full source text:**

> AR-002 [P0] MUST expose every external vendor behind an internal interface: TelephonyProvider, SttProvider, TtsProvider, LlmProvider, SmsProvider, EmailProvider, PaymentProvider, CalendarProvider, GeocodingProvider. Each MUST have at least one alternative implementation stubbed or contract-tested by end of P1 for telephony and LLM, by P2 for the rest.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AR-003

**Deliverable:** Deliver system events reliably

**P0 · MUST · Pending**

**Check:** A saved business change and its event are committed together; replay does not duplicate the resulting action.

**Owner:** To assign.

**Source:** Technical specification §11.7 Architecture requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> AR-003 [P0] MUST use an event-driven backbone: state changes emit versioned domain events (Appendix C) via an outbox table, so that workers, analytics, webhooks and future services consume them without coupling. The outbox pattern MUST be used so events are never lost on commit.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AR-004

**Deliverable:** Keep answering during an outage

**P1 · MUST · Pending**

**Check:** Calls use approved cached settings and a working alternative or safe message-capture flow when a dependency fails.

**Owner:** To assign.

**Source:** Technical specification §11.7 Architecture requirements.

**Business links:** [BR-068](#br-068).

**Official acceptance links:** [AT-49](#at-49).

**Full source text:**

> AR-004 [P1] MUST ensure the voice path degrades gracefully: if the control plane, database or a primary vendor is down, calls still get answered with cached configuration and a fallback provider or a safe fallback flow (take a message, text the owner). Test with chaos drills in P2.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AR-005

**Deliverable:** Add capacity without redesigning

**P1 · MUST · Pending**

**Check:** Business placement and routing are recorded from P1; another complete capacity group can be provisioned automatically.

**Owner:** To assign.

**Source:** Technical specification §11.7 Architecture requirements.

**Business links:** [BR-072](#br-072).

**Official acceptance links:** [AT-51](#at-51).

**Full source text:**

> AR-005 [P1] MUST be cell-ready: a "cell" is a complete stack (API, workers, DB schema set, Redis, media/voice workers) serving a subset of tenants. tenants.cell_id and a routing map MUST exist from P1 even if only one cell runs. Adding a cell MUST be scriptable (infra as code).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AR-006

**Deliverable:** Keep servers easy to replace

**P1 · MUST · Pending**

**Check:** Replacing an application server does not lose authoritative business data or require hidden local configuration.

**Owner:** To assign.

**Source:** Technical specification §11.7 Architecture requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> AR-006 [P1] MUST make every service stateless where possible, with 12-factor configuration; state lives in MariaDB, Redis or object storage.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AR-007

**Deliverable:** Version APIs, events and AI settings

**P1 · MUST · Pending**

**Check:** The versions of public interfaces, events, settings and prompts can be identified and changed compatibly.

**Owner:** To assign.

**Source:** Technical specification §11.7 Architecture requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> AR-007 [P1] MUST version all external APIs (/v1), all events, all agent configuration schemas, and all prompt templates.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AR-008

**Deliverable:** Maintain understandable design diagrams

**P0 · SHOULD · Pending**

**Check:** Context, service and component diagrams plus channel data flows are present and updated with releases.

**Owner:** To assign.

**Source:** Technical specification §11.7 Architecture requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> AR-008 [P0] SHOULD produce a C4 model (context, container, component) and a data-flow diagram per channel, kept in the repo and updated per release.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AR-009

**Deliverable:** Deploy updates without dropping calls

**P1 · MUST · Pending**

**Check:** Active calls finish on draining workers while new calls reach the new release.

**Owner:** To assign.

**Source:** Technical specification §11.7 Architecture requirements.

**Business links:** [BR-069](#br-069).

**Official acceptance links:** [AT-50](#at-50).

**Full source text:**

> AR-009 [P1] MUST support blue/green or rolling deploys with zero dropped calls: voice workers drain (finish active calls, accept none) before termination.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AR-010

**Deliverable:** Prepare for larger deployment platforms

**P2 · SHOULD · Pending**

**Check:** The documented Kubernetes/OpenShift path includes the required manifests or charts and migration steps.

**Owner:** To assign.

**Source:** Technical specification §11.7 Architecture requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> AR-010 [P2] SHOULD provide a path to Kubernetes/OpenShift (manifests or Helm charts and a documented migration plan) while running on Podman/Quadlet at P1.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-013

**Deliverable:** Prepare reliable background work and timers

**P0 · Supporting task · Pending**

**Check:** Queued work and deadlines survive a worker restart without losing or duplicating accepted work.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.2 Application stack.

**Full supporting-task description:** Set up job queues and durable timers for generation, follow-up, summaries, metering and SLA workflows.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-007

**Deliverable:** Separate caching and background workloads

**P0 · Supporting task · Pending**

**Check:** Cache, queue, stream and rate-limit workloads have the required separation and recovery behaviour.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.1 Platform baseline (EverOnn production standard).

**Full supporting-task description:** Set up cache, queue, stream, rate-limit and ephemeral-state instances with workload separation.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-012

**Deliverable:** Create the website chat foundation

**P0 · Supporting task · Pending**

**Check:** The widget shell is isolated from host-site styles and can load within the required size budget.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.2 Application stack.

**Full supporting-task description:** Build the lightweight isolated website widget shell for chat and forms.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-002

**Deliverable:** Run reproducible production containers

**P0 · Supporting task · Pending**

**Check:** Podman/Quadlet units restart correctly and use the required ownership and security settings.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.1 Platform baseline (EverOnn production standard).

**Full supporting-task description:** Configure rootless Podman where feasible and systemd-managed Quadlet units for production workloads.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-004

**Deliverable:** Create the shared business API foundation

**P0 · Supporting task · Pending**

**Check:** Module boundaries, input validation and generated interface documentation are demonstrated.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.2 Application stack.

**Full supporting-task description:** Create the NestJS/Fastify modular monolith with Zod-first validation and generated OpenAPI contracts.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-006

**Deliverable:** Prepare the database and replica

**P0 · Supporting task · Pending**

**Check:** Primary/replica placement, replication and recovery checks match the approved baseline.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.5 Data tier design (MariaDB).

**Full supporting-task description:** Create the system-of-record database topology with primary, replica and recovery configuration.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-025

**Deliverable:** Separate deployment tiers

**P0 · Supporting task · Pending**

**Check:** Edge, app, jobs, voice/media, data and monitoring tiers have only their approved network paths.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.6 Deployment topology on RHEL (P1).

**Full supporting-task description:** Separate edge, app, worker, media/voice, data and observability tiers with controlled network flows.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-016

**Deliverable:** Prepare secure website and application delivery

**P0 · Supporting task · Pending**

**Check:** Edge routing, certificates, caching, abuse protection and limits route each host correctly.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.6 Deployment topology on RHEL (P1).

**Full supporting-task description:** Configure TLS termination, WAF, caching, site routing and rate limiting.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-015

**Deliverable:** Connect an approved email service

**P1 · Supporting task · Pending**

**Check:** The common email interface and authenticated sending domains send a test message with the right identity.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.2 Application stack.

**Full supporting-task description:** Create provider abstraction and first email integration with authenticated sending domains.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-020

**Deliverable:** Measure knowledge-search quality and speed

**P0 · Supporting task · Pending**

**Check:** The P0 benchmark records target-scale recall/latency and the decision on the baseline vector store.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.5 Data tier design (MariaDB).

**Full supporting-task description:** Validate embedding provider and MariaDB VECTOR retrieval performance, with Qdrant as fallback if targets are missed.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-023

**Deliverable:** Separate development, test and production

**P0 · Supporting task · Pending**

**Check:** Environment access and data controls prevent production personal data entering lower environments.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.6 Deployment topology on RHEL (P1).

**Full supporting-task description:** Stand up isolated environments and ensure production data is never copied into lower environments.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-009

**Deliverable:** Set up the approved identity service

**P0 · Supporting task · Pending**

**Check:** The approved identity choice demonstrates login, multi-factor authentication and scoped roles.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.2 Application stack.

**Full supporting-task description:** Configure OIDC identity, MFA, passkeys and role support on the platform baseline.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-022

**Deliverable:** Process website images safely

**P1 · Supporting task · Pending**

**Check:** Rights, malware checks, metadata removal, resizing and required delivery variants are verified.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.4 Website engine stack.

**Full supporting-task description:** Add resize, format conversion, EXIF removal, malware scanning and CDN variants.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-024

**Deliverable:** Automate environment and capacity setup

**P0 · Supporting task · Pending**

**Check:** Versioned infrastructure creates a repeatable environment/capacity group without undocumented manual changes.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §24.1 Delivery pipeline.

**Full supporting-task description:** Make each environment and cell reproducible through versioned infrastructure automation.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-017

**Deliverable:** Prove real phone and operator audio connections

**P0 · Supporting task · Pending**

**Check:** Staging calls traverse carrier, media and worker paths and prove the selected operator audio design.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.3 Voice and AI stack.

**Full supporting-task description:** Create the real-time media tier for SIP ingress, WebRTC rooms and operator audio.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-019

**Deliverable:** Create the shared AI model service

**P0 · Supporting task · Pending**

**Check:** Task routing, alternatives, budgets, redaction, traces and cost records work through the internal interface.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.3 Voice and AI stack.

**Full supporting-task description:** Create the internal model gateway for routing, fallback, budgets, prompt caching, redaction, tracing and cost capture.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-008

**Deliverable:** Store recordings, sites and backups safely

**P0 · Supporting task · Pending**

**Check:** Private storage access, lifecycle rules and archive protections match the data classification.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.1 Platform baseline (EverOnn production standard).

**Full supporting-task description:** Create secure storage for recordings, generated site bundles, exports and backups.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-014

**Deliverable:** Prepare service monitoring

**P0 · Supporting task · Pending**

**Check:** Required logs, traces and metrics can be viewed and used for alerts before the pilot.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §24.3 Observability.

**Full supporting-task description:** Set up platform-wide tracing, metrics, logs and dashboards before pilot development.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-001

**Deliverable:** Prepare the required production operating system

**P0 · Supporting task · Pending**

**Check:** RHEL hosts enforce the specified security and patching baseline.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.1 Platform baseline (EverOnn production standard).

**Full supporting-task description:** Prepare RHEL hosts with SELinux enforcing, firewalld and automated patching baseline.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-005

**Deliverable:** Create the voice and evaluation service foundation

**P0 · Supporting task · Pending**

**Check:** A locked Python build runs the service skeleton and evaluation entry points reproducibly.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.2 Application stack.

**Full supporting-task description:** Create the Python service foundation for voice agents, evaluation and ML tooling with reproducible dependency locking.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-003

**Deliverable:** Create the shared engineering repository

**P0 · Supporting task · Pending**

**Check:** The specified folders and locked language dependencies support reproducible builds.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.2 Application stack.

**Full supporting-task description:** Create apps/, services/, packages/, infra/, evals/ and docs/ with locked TypeScript and Python dependencies.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-010

**Deliverable:** Set up secrets and encryption-key management

**P0 · Supporting task · Pending**

**Check:** The approved Vault/OpenBao setup demonstrates scoped access, rotation and wrapped data keys.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.2 Application stack.

**Full supporting-task description:** Configure Vault/OpenBao for dynamic credentials, Transit envelope encryption and rotation.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-018

**Deliverable:** Connect both P1 telephone carriers

**P1 · Supporting task · Pending**

**Check:** Both adapters handle their required call/number/text functions; P2 automatic failover remains a separate ticket.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.3 Voice and AI stack.

**Full supporting-task description:** Implement Twilio and Telnyx carrier adapters to support failover, numbers and SMS.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-011

**Deliverable:** Create client and staff application foundations

**P0 · Supporting task · Pending**

**Check:** The required dashboard, inbox, desk and protected administration shells use shared design foundations.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.2 Application stack.

**Full supporting-task description:** Set up shared Next.js/React frontend foundation for dashboard, inbox, admin and internal consoles.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### PLAT-021

**Deliverable:** Create the versioned website renderer

**P0 · Supporting task · Pending**

**Check:** A validated Site Spec produces a static site from the approved component library.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.4 Website engine stack.

**Full supporting-task description:** Create schema-driven static site rendering with a versioned component library.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DATA-004

**Deliverable:** Back up and restore the platform

**P1 · Supporting task · Pending**

**Check:** Backup, point-in-time recovery and isolated restore evidence meet the phase-specific recovery targets.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §23.5 Resilience and disaster recovery.

**Full supporting-task description:** Configure nightly full backups, continuous binlog shipping, immutable copies and restore testing.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DATA-005

**Deliverable:** Use controlled database connections

**P1 · Supporting task · Pending**

**Check:** Scoped credentials, encryption, pooling and replica-aware access follow the approved design.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.5 Data tier design (MariaDB).

**Full supporting-task description:** Use pooled TLS database connections, per-service credentials and replica-aware access patterns.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DATA-007

**Deliverable:** Store usage, events and audits reliably

**P1 · Supporting task · Pending**

**Check:** Durable structures retain trace information and support duplicate-safe delivery, accounting and audit.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §11.7 Architecture requirements.

**Full supporting-task description:** Create durable event, metering and audit data structures with idempotency and trace metadata.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DATA-003

**Deliverable:** Manage high-volume history efficiently

**P1 · Supporting task · Pending**

**Check:** The selected time partitions preserve required queries and retention without losing live records.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.5 Data tier design (MariaDB).

**Full supporting-task description:** Partition calls, messages, usage and audit/event data by time for scale and retention.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DATA-008

**Deliverable:** Protect file references and metadata

**P1 · Supporting task · Pending**

**Check:** File classification, retention and key versions are recorded; public bucket exposure is prevented.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §21. Data model.

**Full supporting-task description:** Store object references, classifications, retention and encryption-key versions without public bucket exposure.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DATA-010

**Deliverable:** Archive and expire records correctly

**P1 · Supporting task · Pending**

**Check:** Archive verification precedes partition removal and the applicable retention/hold policy controls deletion.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §23.5 Resilience and disaster recovery.

**Full supporting-task description:** Archive required cold data to object storage before partition drop and apply tenant/compliance retention policies.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DATA-002

**Deliverable:** Change database schemas safely

**P0 · Supporting task · Pending**

**Check:** Reviewed migrations pass dry-run and compatibility checks for current and previous application versions.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §21.2 Schema conventions (MUST).

**Full supporting-task description:** Use reviewed, backward-compatible expand/contract migrations with dry-runs and rollback plans.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DATA-009

**Deliverable:** Index approved knowledge and inbox search

**P1 · Supporting task · Pending**

**Check:** Text and vector indexes support the required searches while enforcing business isolation.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §20.5 Data tier design (MariaDB).

**Full supporting-task description:** Add MariaDB FULLTEXT and tenant-filtered VECTOR indexes needed by inbox and knowledge retrieval.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DATA-001

**Deliverable:** Apply business-scoped storage conventions

**P0 · Supporting task · Pending**

**Check:** The required tenant-first keys and controlled repository access are enforced across business-owned tables.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §21.2 Schema conventions (MUST).

**Full supporting-task description:** Apply tenant_id-first keys and tenant-scoped repository access across tenant-owned data.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DATA-006

**Deliverable:** Preserve published knowledge and AI versions

**P1 · Supporting task · Pending**

**Check:** Published profiles, knowledge, agents and policies remain immutable and can be traced or rolled back.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §13.3 Agent configuration.

**Full supporting-task description:** Store agent, profile, knowledge, policy, prompt and vertical-pack published versions immutably.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ONB-001

**Deliverable:** Create a private preview in minutes

**P1 · MUST · Pending**

**Check:** Valid intake produces a draft profile and private preview within the stated target, with at most three first-screen fields.

**Owner:** To assign.

**Source:** Technical specification §12.2 Requirements.

**Business links:** [BR-014](#br-014).

**Official acceptance links:** [AT-01](#at-01).

**Related source references:** [WEB-001](#web-001).

**Full source text:**

> ONB-001 [P1] MUST implement the claim flow: input business name plus phone or website or Google listing link; system resolves the business, generates a private preview site (WEB-001) and a draft business profile within 2 minutes (target), then captures email or SMS to claim. Mobile thumb-friendly; at most 3 fields on the first screen.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ONB-002

**Deliverable:** Verify the business before going public

**P1 · MUST · Pending**

**Check:** An unverified person cannot publish a business site, attach real calls or expose the real business phone number.

**Owner:** To assign.

**Source:** Technical specification §12.2 Requirements.

**Business links:** [BR-015](#br-015), [BR-019](#br-019).

**Official acceptance links:** [AT-01](#at-01), [AT-05](#at-05).

**Full source text:**

> ONB-002 [P1] MUST prevent impersonation: a preview MUST NOT go public, receive real calls, or display the business's real phone number until ownership is verified (phone OTP to the number on the listing, or Google Business Profile ownership, or a document/manual review path handled by support). Verification method and result are stored.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ONB-003

**Deliverable:** Guide the owner through setup

**P1 · MUST · Pending**

**Check:** The owner completes the five setup steps, resumes saved progress and tests call/chat before going live.

**Owner:** To assign.

**Source:** Technical specification §12.2 Requirements.

**Business links:** [BR-001](#br-001), [BR-009](#br-009).

**Official acceptance links:** [AT-02](#at-02), [AT-12](#at-12).

**Related source references:** [VOX-030](#vox-030), [VOX-031](#vox-031), [VOX-032](#vox-032), [VOX-033](#vox-033), [VOX-034](#vox-034).

**Full source text:**

> ONB-003 [P1] MUST guide a 5-step setup wizard: (1) confirm business facts, (2) approve or edit services and hours, (3) set escalation and handoff rules, (4) choose how calls reach EverOnn (forward, port, or new number, VOX-030 to VOX-034), (5) test call and test chat, then go live. Progress is saved; the owner can resume from any device.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ONB-004

**Deliverable:** Try the AI before launch

**P1 · MUST · Pending**

**Check:** A sandbox call and chat use draft settings without customer notifications or billing, with a reviewable transcript.

**Owner:** To assign.

**Source:** Technical specification §12.2 Requirements.

**Business links:** [BR-022](#br-022).

**Official acceptance links:** [AT-02](#at-02).

**Related source references:** [KNW-009](#knw-009).

**Full source text:**

> ONB-004 [P1] MUST provide a test mode: a sandbox number and chat widget that run the real agent against the draft configuration without billing or notifying customers, with full transcript and "why did it say that" explanations (KNW-009).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ONB-005

**Deliverable:** Record the owner's approval

**P1 · MUST · Pending**

**Check:** Go-live requires an explicit approval linked to the exact knowledge and greeting version.

**Owner:** To assign.

**Source:** Technical specification §12.2 Requirements.

**Business links:** [BR-020](#br-020).

**Official acceptance links:** [AT-01](#at-01), [AT-02](#at-02).

**Full source text:**

> ONB-005 [P1] MUST require the owner to explicitly approve the AI's knowledge and greeting before go-live (a recorded approval event with the approved version id).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ONB-006

**Deliverable:** Capture hours, coverage and contact preferences

**P1 · MUST · Pending**

**Check:** The saved setup includes time zone, service area, languages, emergency rules and notification channels.

**Owner:** To assign.

**Source:** Technical specification §12.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ONB-006 [P1] MUST capture business-hours, time zone, service area, languages, emergency policy, and preferred notification channels at onboarding.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ONB-007

**Deliverable:** Import existing business information

**P1 · SHOULD · Pending**

**Check:** Allowed imports populate draft information; a failed import still allows manual setup.

**Owner:** To assign.

**Source:** Technical specification §12.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ONB-007 [P1] SHOULD auto-import from Google Business Profile (name, hours, categories, reviews summary, photos) and from the existing website (services, FAQs) via the public web with respect for robots.txt and terms; failures MUST degrade to manual entry.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ONB-008

**Deliverable:** Support businesses with several locations

**P2 · SHOULD · Pending**

**Check:** Locations retain their own numbers, hours and agent settings under the same business account.

**Owner:** To assign.

**Source:** Technical specification §12.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ONB-008 [P2] SHOULD support multi-location tenants (one tenant, many locations, each with its own number, hours and agent variant).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ONB-009

**Deliverable:** Invite staff with suitable access

**P1 · MUST · Pending**

**Check:** Invited staff receive the correct roles and can choose their notification preferences.

**Owner:** To assign.

**Source:** Technical specification §12.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ONB-009 [P1] MUST support team invitations with roles from §10.2 and per-user notification preferences.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ONB-010

**Deliverable:** Avoid duplicate business accounts

**P1 · MUST · Pending**

**Check:** Repeating the same claim resumes or matches the existing business rather than creating duplicates.

**Owner:** To assign.

**Source:** Technical specification §12.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ONB-010 [P1] MUST be resumable and idempotent: repeated claim submissions for the same business MUST NOT create duplicate tenants (dedupe on normalized phone, domain and Place ID).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ONB-011

**Deliverable:** Use the correct brand during setup

**P1 · MUST · Pending**

**Check:** The claim page, emails, consent wording and resulting account all use the selected brand and industry pack.

**Owner:** To assign.

**Source:** Technical specification §12.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ONB-011 [P1] MUST make the claim flow brand-aware: each brand has its own landing and claim pages, forms, emails and consent texts, and creates the tenant under that brand and its vertical pack.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ONB-012

**Deliverable:** Start setup for a switching customer

**P1 · MUST · Pending**

**Check:** A verified prospect links to its new business account and opens a migration project with recorded sources.

**Owner:** To assign.

**Source:** Technical specification §12.2 Requirements.

**Business links:** [BR-054](#br-054).

**Official acceptance links:** [AT-24](#at-24).

**Related source references:** [MIG-001](#mig-001).

**Full source text:**

> ONB-012 [P1] MUST support a switching claim: when a preview originates from an acquisition prospect, it is pre-populated from the prospect's public data with the source recorded, the prospect and tenant are linked, and a migration project (MIG-001) is opened as soon as the incumbent is known.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### TEN-001

**Deliverable:** Keep every business's data separate

**P0 · MUST · Pending**

**Check:** All four source guarantees are verified, including tenant-first keys, controlled queries, isolation tests and the database trade-off record.

**Owner:** To assign.

**Source:** Technical specification §12.3 Tenancy model requirements.

**Business links:** [BR-028](#br-028), [BR-063](#br-063).

**Official acceptance links:** [AT-30](#at-30), [AT-32](#at-32), [AT-47](#at-47).

**Full source text:**

> TEN-001 [P0] MUST use a shared-schema, tenant_id-keyed model in MariaDB for P1 and P2, with these guarantees:

> every tenant-owned table has tenant_id as the leading column of its primary key or of a unique key, and as the leading column of every tenant-scoped index;

> all data access goes through a tenant-scoped repository layer that injects tenant_id from the request context; raw queries outside this layer are forbidden by lint rules and code review;

> automated cross-tenant isolation tests run in CI and nightly (attempt to read/write tenant B's rows as tenant A through every API route and worker job);

> MariaDB has no native row-level security, so the above compensates; the studio MUST document this trade-off in an ADR.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### TEN-002

**Deliverable:** Record where each business is hosted

**P1 · MUST · Pending**

**Check:** The business record contains its capacity group, region, residency and service tier, with routing from day one.

**Owner:** To assign.

**Source:** Technical specification §12.3 Tenancy model requirements.

**Business links:** [BR-072](#br-072).

**Official acceptance links:** [AT-51](#at-51).

**Full source text:**

> TEN-002 [P1] MUST include tenants.cell_id, tenants.region, tenants.data_residency and tenants.tier columns and a routing map from day one (scaffolding for cells, regional residency and dedicated-schema enterprise tenants).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### TEN-003

**Deliverable:** Offer dedicated data placement later

**P2 · SHOULD · Pending**

**Check:** A large or regulated business can use a separate schema/database without changing feature code.

**Owner:** To assign.

**Source:** Technical specification §12.3 Tenancy model requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> TEN-003 [P2] SHOULD support schema-per-tenant or database-per-tenant placement for large or regulated tenants without code changes (the repository layer resolves the connection from the routing map).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### TEN-004

**Deliverable:** Separate files, queues and caches by business

**P1 · MUST · Pending**

**Check:** Business-specific files, cache entries, queues and indexes cannot collide; sensitive stored files use business-specific encryption.

**Owner:** To assign.

**Source:** Technical specification §12.3 Tenancy model requirements.

**Business links:** [BR-063](#br-063).

**Official acceptance links:** [AT-32](#at-32), [AT-47](#at-47).

**Related source references:** [SEC-005](#sec-005).

**Full source text:**

> TEN-004 [P1] MUST namespace all cache keys, queue names, object-storage paths and search indexes by tenant (t/{tenant_id}/...). Recordings and exports MUST be encrypted with keys derived per tenant (envelope encryption, SEC-005).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### TEN-005

**Deliverable:** Prevent one business from slowing others

**P1 · MUST · Pending**

**Check:** Limits and fair processing protect other clients when one business creates unusually heavy traffic.

**Owner:** To assign.

**Source:** Technical specification §12.3 Tenancy model requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> TEN-005 [P1] MUST enforce per-tenant quotas and rate limits (API, calls per minute, concurrent calls, SMS per hour, generation jobs) with a noisy-neighbor policy: one tenant MUST NOT be able to starve others (fair queuing in workers).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### TEN-006

**Deliverable:** Export or delete business data

**P1 · MUST · Pending**

**Check:** A complete machine-readable export or verified deletion, including the required key erasure, is delivered within the required time.

**Owner:** To assign.

**Source:** Technical specification §12.3 Tenancy model requirements.

**Business links:** [BR-067](#br-067).

**Official acceptance links:** [AT-46](#at-46).

**Full source text:**

> TEN-006 [P1] MUST support tenant data export (full, machine-readable) and deletion (hard delete plus cryptographic erasure of keys) on request within statutory timelines.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### TEN-007

**Deliverable:** Keep brands and industry packs separate

**P1 · MUST · Pending**

**Check:** Brand and industry assignment are stored and automated tests prove that one brand cannot expose another's data.

**Owner:** To assign.

**Source:** Technical specification §12.3 Tenancy model requirements.

**Business links:** [BR-045](#br-045).

**Official acceptance links:** [AT-06](#at-06).

**Related source references:** [TEN-001](#ten-001).

**Full source text:**

> TEN-007 [P1] MUST record brand_id and vertical_pack_id on every tenant, and run brand isolation tests alongside the tenant isolation tests (TEN-001): users, APIs, emails and pages of one brand MUST NOT expose another brand's data.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AGT-001

**Deliverable:** Define a versioned assistant

**P1 · MUST · Pending**

**Check:** Every assistant records its business, channels, languages, knowledge versions, policies and enabled tools.

**Owner:** To assign.

**Source:** Technical specification §13.3 Agent configuration.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> AGT-001 [P1] MUST model an agent as: {id, tenant_id, channel_set, persona, language_set, profile_version, kb_version, policy_set_version, tool_set, escalation_rules, business_hours_mode, voice_config, model_routing, created/updated, status}. A tenant has at least one agent; multi-location or multi-line tenants MAY have several.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AGT-002

**Deliverable:** Apply instructions in the correct order

**P1 · MUST · Pending**

**Check:** All six source instruction layers are represented, and lower-trust content cannot override higher-authority rules.

**Owner:** To assign.

**Source:** Technical specification §13.3 Agent configuration.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [COM-007](#com-007).

**Full source text:**

> AGT-002 [P1] MUST implement layered prompt assembly (highest to lowest authority; lower layers cannot override higher ones):

> 1.  Platform policy (EverOnn-owned; safety, legal, disclosure, prompt-injection defense, tool-use rules)

> 2.  Vertical playbook (trade-specific intake and triage logic)

> 3.  Tenant configuration (profile, tone, rules, escalation preferences)

> 4.  Retrieved knowledge (RAG chunks, clearly delimited as untrusted reference data)

> 5.  Conversation and caller context (caller ID, prior history, time, open jobs)

> All layers are versioned templates; the final assembled prompt for every turn is stored (redacted per COM-007) for debugging and eval replay.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AGT-003

**Deliverable:** Let owners adjust the assistant easily

**P1 · MUST · Pending**

**Check:** Owners can change approved greetings, tone, unknown-answer behaviour and escalation settings without coding.

**Owner:** To assign.

**Source:** Technical specification §13.3 Agent configuration.

**Business links:** [BR-021](#br-021), [BR-025](#br-025).

**Official acceptance links:** [AT-02](#at-02), [AT-16](#at-16), [AT-34](#at-34), [AT-54](#at-54).

**Full source text:**

> AGT-003 [P1] MUST give owners no-code controls: greeting text, tone slider, "what to say when you can't answer", escalation preferences (who to call, when, in what order), hours-based behavior (business hours vs after hours), pricing policy, "never say" list, transfer numbers, spam-call handling.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AGT-004

**Deliverable:** Test, publish and undo AI changes

**P1 · MUST · Pending**

**Check:** Draft settings can be tested, published and rolled back to a named previous version.

**Owner:** To assign.

**Source:** Technical specification §13.3 Agent configuration.

**Business links:** [BR-021](#br-021), [BR-076](#br-076).

**Official acceptance links:** [AT-02](#at-02), [AT-15](#at-15), [AT-54](#at-54).

**Full source text:**

> AGT-004 [P1] MUST support draft → test → publish → rollback for every agent configuration change with a version history and one-click rollback.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AGT-005

**Deliverable:** Compare approved assistant variants

**P2 · SHOULD · Pending**

**Check:** Owner-approved variants report outcomes without mixing results across businesses.

**Owner:** To assign.

**Source:** Technical specification §13.3 Agent configuration.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> AGT-005 [P2] SHOULD support A/B variants (greeting, script) with outcome metrics, run per tenant with the owner's consent.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AGT-006

**Deliverable:** Choose AI models by task

**P1 · MUST · Pending**

**Check:** Voice, chat, extraction and evaluation use the configured task routes through the shared model service.

**Owner:** To assign.

**Source:** Technical specification §13.3 Agent configuration.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> AGT-006 [P1] MUST include model routing configuration per agent and per task (voice turn, chat turn, summarization, extraction, QA judge) resolved through the model gateway (§20.3); tenants never choose raw model names, only quality tiers.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AGT-007

**Deliverable:** Control which actions the AI can take

**P1 · MUST · Pending**

**Check:** Tool inputs and outputs are validated; business permissions, plan access and approvals are enforced by the server.

**Owner:** To assign.

**Source:** Technical specification §13.3 Agent configuration.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> AGT-007 [P1] MUST define a tool registry (Appendix B). Tools have JSON-Schema-typed inputs and outputs, per-tenant enablement, per-plan entitlement, timeouts, retries and idempotency keys. Tool results are treated as untrusted data by the model.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### AGT-008

**Deliverable:** Create a reliable request after each conversation

**P1 · MUST · Pending**

**Check:** The extracted request passes the published schema and preserves uncertainty instead of inventing missing fields.

**Owner:** To assign.

**Source:** Technical specification §13.3 Agent configuration.

**Business links:** [BR-002](#br-002).

**Official acceptance links:** [AT-12](#at-12).

**Full source text:**

> AGT-008 [P1] MUST implement structured extraction: at the end of every conversation, produce a schema-validated Request object (Appendix D) from the transcript and tool results, with per-field confidence and evidence spans. Downstream systems consume the structured object, never free text.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### KNW-001

**Deliverable:** Maintain a structured business profile

**P1 · MUST · Pending**

**Check:** The profile is validated, versioned and linked to the required searchable business records.

**Owner:** To assign.

**Source:** Technical specification §13.1 Business profile (structured facts).

**Business links:** [BR-020](#br-020).

**Official acceptance links:** [AT-01](#at-01), [AT-02](#at-02).

**Full source text:**

> KNW-001 [P1] MUST store the profile as a versioned, schema-validated JSON document (JSON Schema published in the repo) plus normalized tables for query. Each save creates an immutable version; agents run against a published version, never a draft.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### KNW-002

**Deliverable:** Start with an industry-specific playbook

**P1 · MUST · Pending**

**Check:** The chosen industry supplies suitable questions, safety rules, intake fields and sample knowledge.

**Owner:** To assign.

**Source:** Technical specification §13.1 Business profile (structured facts).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> KNW-002 [P1] MUST support a vertical template per trade (Appendix E) that seeds the profile, intake slots, triage rules, sample FAQs and guardrails. Templates are data, editable by EverOnn staff without deploys.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### POL-001

**Deliverable:** Enforce the business's safety rules

**P1 · MUST · Pending**

**Check:** Forbidden quotes, commitments, advice and sensitive-data collection are blocked in code as well as instructions.

**Owner:** To assign.

**Source:** Technical specification §13.4 Guardrails and policy engine.

**Business links:** [BR-004](#br-004).

**Official acceptance links:** [AT-14](#at-14), [AT-15](#at-15).

**Related source references:** [COM-003](#com-003).

**Full source text:**

> POL-001 [P1] MUST enforce guardrails in two places: in the prompt (soft) and in code (hard): output filters and tool-call validators the model cannot bypass. Hard rules include: no price quote unless the pricing policy and KB explicitly allow it; no promise of arrival time unless dispatch data supports it; no medical/legal/financial advice; no collection of full card numbers or SSNs; no disclosure of other customers' information; no impersonating a human when sincerely asked whether it is an AI (COM-003).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### POL-002

**Deliverable:** Recognise emergencies and seek human help

**P1 · MUST · Pending**

**Check:** Industry-specific emergency cases produce the required guidance and highest-priority escalation.

**Owner:** To assign.

**Source:** Technical specification §13.4 Guardrails and policy engine.

**Business links:** [BR-005](#br-005).

**Official acceptance links:** [AT-16](#at-16).

**Related source references:** [HIL-002](#hil-002).

**Full source text:**

> POL-002 [P1] MUST implement emergency and safety triage per vertical: gas smell, fire, carbon monoxide, medical emergency, child locked in car, and threats. The agent MUST advise contacting emergency services where appropriate, and immediately escalate (HIL-002) to the owner or operator with highest priority. The trigger phrases and actions are configured in vertical templates and covered by the eval set.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### POL-003

**Deliverable:** Ignore attempts to override the AI's rules

**P1 · MUST · Pending**

**Check:** Hostile messages, imported pages and tool results cannot change permissions or execute arbitrary actions.

**Owner:** To assign.

**Source:** Technical specification §13.4 Guardrails and policy engine.

**Business links:** [BR-004](#br-004).

**Official acceptance links:** [AT-14](#at-14), [AT-15](#at-15).

**Full source text:**

> POL-003 [P1] MUST defend against prompt injection and jailbreaks from callers, website visitors, ingested web content and tool results: separate system and untrusted content channels, strip or neutralize instructions in retrieved/ingested text, restrict tools by allow-list, validate tool arguments server-side, and never let model output execute arbitrary code or URLs. Include an adversarial test suite in CI (§24.5).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### POL-004

**Deliverable:** Handle abusive or unwanted interactions

**P1 · MUST · Pending**

**Check:** Configured responses and business/platform block lists deal with repeated abuse and spam.

**Owner:** To assign.

**Source:** Technical specification §13.4 Guardrails and policy engine.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> POL-004 [P1] MUST detect and handle abuse, harassment, threats, and spam or robocalls (configurable: hang up politely, take message, block number). Repeated abusive numbers go to a tenant-scoped, then platform-scoped, block list.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### POL-005

**Deliverable:** Collect only necessary personal information

**P1 · MUST · Pending**

**Check:** Sensitive details are minimised and masked; full card information is refused and routed to hosted payment.

**Owner:** To assign.

**Source:** Technical specification §13.4 Guardrails and policy engine.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> POL-005 [P1] MUST apply PII minimization: collect only what the playbook requires; mask sensitive tokens (card, SSN, DOB) in transcripts and logs; refuse to store payment card data (route to a payment link instead).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### POL-006

**Deliverable:** Record safety interventions

**P1 · MUST · Pending**

**Check:** Every enforced guardrail creates a coded event that reviewers can find in quality reports.

**Owner:** To assign.

**Source:** Technical specification §13.4 Guardrails and policy engine.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> POL-006 [P1] MUST log every guardrail intervention with a code, so quality dashboards and QA sampling can target them.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### KNW-003

**Deliverable:** Import documents and questions

**P1 · MUST · Pending**

**Check:** Supported documents, website content and custom questions retain their source, processing state and version.

**Owner:** To assign.

**Source:** Technical specification §13.2 Unstructured knowledge (RAG).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> KNW-003 [P1] MUST ingest: pasted FAQs, uploaded PDFs/DOCX/TXT, the tenant's website pages, and structured "custom Q&amp;A" pairs. Each source has status, last-ingested time, and owner approval state.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### KNW-004

**Deliverable:** Search only the right business's knowledge

**P1 · MUST · Pending**

**Check:** Answers retrieve relevant information only from the current business and the approved knowledge version.

**Owner:** To assign.

**Source:** Technical specification §13.2 Unstructured knowledge (RAG).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [KNW-007](#knw-007).

**Full source text:**

> KNW-004 [P1] MUST chunk, embed and index knowledge per tenant with metadata (source, version, section, language). Retrieval MUST be tenant-filtered at the query layer, top-k limited, with a relevance threshold: below threshold the agent MUST treat the answer as unknown (KNW-007).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### KNW-005

**Deliverable:** Approve knowledge before the AI uses it

**P1 · MUST · Pending**

**Check:** Imported or edited knowledge remains draft until the owner approves it and can review the change.

**Owner:** To assign.

**Source:** Technical specification §13.2 Unstructured knowledge (RAG).

**Business links:** [BR-020](#br-020).

**Official acceptance links:** [AT-01](#at-01), [AT-02](#at-02).

**Full source text:**

> KNW-005 [P1] MUST support owner approval of every KB item before it becomes agent-visible, with diff view on edits. Auto-imported content enters as pending.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### KNW-006

**Deliverable:** Find outdated or conflicting information

**P1 · SHOULD · Pending**

**Check:** Conflicting hours or stale facts are flagged for the owner to resolve.

**Owner:** To assign.

**Source:** Technical specification §13.2 Unstructured knowledge (RAG).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> KNW-006 [P1] SHOULD detect stale or conflicting content (for example two different hours) and prompt the owner to resolve.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### KNW-007

**Deliverable:** Admit when an answer is unknown

**P1 · MUST · Pending**

**Check:** Missing knowledge produces an honest explanation and a structured follow-up request rather than an invented answer.

**Owner:** To assign.

**Source:** Technical specification §13.2 Unstructured knowledge (RAG).

**Business links:** [BR-004](#br-004), [BR-023](#br-023).

**Official acceptance links:** [AT-14](#at-14), [AT-15](#at-15), [AT-39](#at-39).

**Full source text:**

> KNW-007 [P1] MUST implement the "I don't know" contract: when retrieval fails or confidence is low, the agent states it will have someone follow up, captures the question and contact details, and creates a knowledge_gap item shown to the owner ("Your AI was asked this and didn't know. Add an answer?"). Answering it updates the KB after approval.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### KNW-008

**Deliverable:** Improve the quality of knowledge search

**P2 · SHOULD · Pending**

**Check:** The required combined search strategy is evaluated separately for each business.

**Owner:** To assign.

**Source:** Technical specification §13.2 Unstructured knowledge (RAG).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> KNW-008 [P2] SHOULD support a hybrid retrieval strategy (vector plus keyword/BM25) with reranking, and per-tenant retrieval evaluation.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### KNW-009

**Deliverable:** Explain why the AI gave an answer

**P1 · MUST · Pending**

**Check:** A reviewer can inspect the supporting facts, knowledge, tools and rules behind an AI response.

**Owner:** To assign.

**Source:** Technical specification §13.2 Unstructured knowledge (RAG).

**Business links:** [BR-023](#br-023).

**Official acceptance links:** [AT-39](#at-39).

**Full source text:**

> KNW-009 [P1] MUST provide explainability: for any AI message, the dashboard shows which profile fields and KB chunks were used, which tools were called, and which policy rules fired.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-016

**Deliverable:** Follow the industry's intake steps

**P1 · MUST · Pending**

**Check:** The conversation captures the required industry details and applies its safety and business rules.

**Owner:** To assign.

**Source:** Technical specification §14.5 Requirements: business behavior.

**Business links:** [BR-001](#br-001), [BR-002](#br-002).

**Official acceptance links:** [AT-12](#at-12).

**Full source text:**

> VOX-016 [P1] MUST execute the vertical playbook: required slots (for example locksmith: lockout type, vehicle or property, address, safety status, ID-at-arrival note; HVAC: system type, symptom, urgency, occupants at risk). The agent asks one question at a time, adapts to volunteered information, and never re-asks for known data.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-017

**Deliverable:** Classify the request's urgency

**P1 · MUST · Pending**

**Check:** Emergency, urgent, standard and information-only cases receive the correct reason and routing.

**Owner:** To assign.

**Source:** Technical specification §14.5 Requirements: business behavior.

**Business links:** [BR-002](#br-002).

**Official acceptance links:** [AT-12](#at-12).

**Full source text:**

> VOX-017 [P1] MUST support urgency triage producing urgency ∈ {emergency, urgent, standard, info} with reason, and route accordingly (immediate owner transfer or text with priority flag).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-018

**Deliverable:** Check whether the business serves the address

**P1 · MUST · Pending**

**Check:** In-area and out-of-area requests follow the business's configured coverage policy.

**Owner:** To assign.

**Source:** Technical specification §14.5 Requirements: business behavior.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-018 [P1] MUST check service area using geocoding of the captured address and politely decline or route out-of-area requests per tenant policy.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-019

**Deliverable:** Transfer calls with useful context

**P1 · MUST · Pending**

**Check:** Warm and cold transfer cases preserve the correct identity and context, with a safe result if the recipient does not answer.

**Owner:** To assign.

**Source:** Technical specification §14.5 Requirements: business behavior.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-019 [P1] MUST support live transfer: warm transfer with a whispered context summary to the receiving party ("Caller Maria, lockout at 12 Oak St, urgent"), cold transfer, and transfer failure fallback (no answer → return to AI → capture message and schedule callback). Transfer targets and priority order are configured per hours mode. Targets are the client's own contacts and, in operator mode, EverOnn operators on the Live Agent Desk (§16.4).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-020

**Deliverable:** Book an appointment when appropriate

**P1 · MUST · Pending**

**Check:** Allowed bookings check real availability, avoid conflicts and confirm the result before promising a slot.

**Owner:** To assign.

**Source:** Technical specification §14.5 Requirements: business behavior.

**Business links:** [BR-008](#br-008).

**Official acceptance links:** [AT-18](#at-18).

**Full source text:**

> VOX-020 [P1] MUST allow the AI to book appointments through the CalendarProvider (Google, Microsoft, Cal.com at P1; scheduling software integrations at P3) respecting buffers, service durations and territory, with confirmation SMS.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-021

**Deliverable:** Send the owner a prompt call summary

**P1 · MUST · Pending**

**Check:** The required summary is delivered through the selected channels within the stated 30-second target.

**Owner:** To assign.

**Source:** Technical specification §14.5 Requirements: business behavior.

**Business links:** [BR-007](#br-007).

**Official acceptance links:** [AT-12](#at-12).

**Full source text:**

> VOX-021 [P1] MUST send the owner summary within 30 seconds of call end via the tenant's preferred channels (SMS, push, email): who, what, where, urgency, next action, link to transcript and audio.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-022

**Deliverable:** Send a permitted customer confirmation

**P1 · MUST · Pending**

**Check:** The optional confirmation uses recorded consent and the correct business identity.

**Owner:** To assign.

**Source:** Technical specification §14.5 Requirements: business behavior.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [COM-002](#com-002).

**Full source text:**

> VOX-022 [P1] MUST send an optional customer confirmation SMS (subject to consent, COM-002).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-023

**Deliverable:** Save the complete call outcome

**P1 · MUST · Pending**

**Check:** The post-call package contains the required transcript, summary and request; audio is included only when permitted.

**Owner:** To assign.

**Source:** Technical specification §14.5 Requirements: business behavior.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-023 [P1] MUST produce the post-call package: transcript with timestamps and speaker labels, audio recording (if permitted), summary, structured Request, sentiment, outcome code, tool-call log, cost breakdown, guardrail events, latency per turn.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-024

**Deliverable:** Recognise a verified returning caller

**P1 · MUST · Pending**

**Check:** Contact matches are business-specific and use the verified identity required by the specification.

**Owner:** To assign.

**Source:** Technical specification §14.5 Requirements: business behavior.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-024 [P1] MUST support returning-caller recognition (matched by verified phone number and tenant contacts) to personalize ("Welcome back, Maria") without exposing history to unverified callers beyond what policy allows.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-025

**Deliverable:** Make approved callbacks

**P2 · SHOULD · Pending**

**Check:** Callbacks are limited to the business's own initiated interactions and applicable consent/calling rules.

**Owner:** To assign.

**Source:** Technical specification §14.5 Requirements: business behavior.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [COM-012](#com-012).

**Full source text:**

> VOX-025 [P2] SHOULD support outbound callbacks initiated by operators or by rules for a tenant's own inbound leads, within TCPA and consent limits (COM-012).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-026

**Deliverable:** Stop unexpectedly expensive calls safely

**P1 · MUST · Pending**

**Check:** Cost limits produce a graceful wrap-up or human handoff without abandoning emergencies.

**Owner:** To assign.

**Source:** Technical specification §14.5 Requirements: business behavior.

**Business links:** [BR-010](#br-010).

**Official acceptance links:** [AT-48](#at-48).

**Full source text:**

> VOX-026 [P1] MUST support per-call and per-day cost circuit breakers (for example a call exceeding 15 minutes triggers a graceful wrap-up or human transfer).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-002

**Deliverable:** Run the real-time speech conversation

**P0 · MUST · Pending**

**Check:** Speech recognition, AI reasoning and spoken answers work through replaceable provider integrations and the required audio evaluations.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Business links:** [BR-003](#br-003).

**Official acceptance links:** [AT-13](#at-13).

**Full source text:**

> VOX-002 [P0] MUST implement a cascaded real-time pipeline (streaming STT → LLM → streaming TTS) behind provider interfaces, with the ability to swap in a speech-to-speech model as an alternative implementation later. P0 spike compares at least: two STT vendors, two TTS vendors, two LLM tiers, on real PSTN audio (8 kHz, noisy, accents) and reports latency, accuracy and cost.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-003

**Deliverable:** Keep phone responses fast

**P0 · MUST · Pending**

**Check:** Measured caller-perceived response gaps meet the source percentiles and stage budgets on real phone audio.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Business links:** [BR-003](#br-003).

**Official acceptance links:** [AT-13](#at-13).

**Full source text:**

> VOX-003 [P0] MUST meet the latency budget (planning targets, measured end-to-end as caller-perceived silence between end of caller speech and first agent audio):

> Tool-calling turns MAY exceed this but MUST use fillers ("One moment while I check that") when a tool is expected to take more than 1.2 s.

**Table belonging to this requirement:**

| Stage | p50 target | p95 target |
| --- | --- | --- |
| Telephony and media transport (one way) | 60 ms | 120 ms |
| Endpointing / end-of-turn detection | 250 ms | 450 ms |
| STT final transcript (streaming, after endpoint) | 80 ms | 200 ms |
| LLM time-to-first-token (voice tier, with tool-free turn) | 300 ms | 700 ms |
| TTS time-to-first-audio | 150 ms | 300 ms |
| Total perceived gap | under 1.0 s | under 1.8 s |

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-004

**Deliverable:** Let callers interrupt the assistant

**P1 · MUST · Pending**

**Check:** Speech stops within the specified interruption budget and the assistant handles the interruption correctly.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Business links:** [BR-003](#br-003).

**Official acceptance links:** [AT-13](#at-13).

**Full source text:**

> VOX-004 [P1] MUST support barge-in: the caller can interrupt; TTS stops within 200 ms; the agent resumes from the interrupted context and does not repeat itself.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-005

**Deliverable:** Recognise when a caller has finished speaking

**P1 · MUST · Pending**

**Check:** Pauses, hesitations and callers trailing off are handled without cutting off meaningful speech.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Business links:** [BR-003](#br-003).

**Official acceptance links:** [AT-13](#at-13).

**Full source text:**

> VOX-005 [P1] MUST implement robust turn-taking: semantic end-of-turn detection (not silence alone), tolerance for "um/uh", handling of caller thinking pauses, and detection of the caller reading back numbers or addresses (longer pauses).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-006

**Deliverable:** Understand noisy calls safely

**P1 · MUST · Pending**

**Check:** Noise tests show polite requests for repetition and confirmation of important details.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Business links:** [BR-002](#br-002).

**Official acceptance links:** [AT-12](#at-12).

**Full source text:**

> VOX-006 [P1] MUST handle noisy and degraded audio (car, wind, speakerphone): request repetition politely, confirm critical slots by read-back (phone number, address, name spelling), and fall back to SMS link capture ("I'll text you a link to share your location") when audio fails repeatedly.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-007

**Deliverable:** Read back important details

**P1 · MUST · Pending**

**Check:** Phone numbers, addresses, names and appointment times are confirmed with the caller.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Business links:** [BR-002](#br-002).

**Official acceptance links:** [AT-12](#at-12).

**Full source text:**

> VOX-007 [P1] MUST implement read-back confirmation for high-value slots: callback number, service address, name, appointment time.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-008

**Deliverable:** Answer in English and Spanish

**P1 · MUST · Pending**

**Check:** P1 tests cover language detection, mid-call switching and the required English/Spanish behaviour.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Business links:** [BR-006](#br-006).

**Official acceptance links:** [AT-17](#at-17).

**Full source text:**

> VOX-008 [P1] MUST support English and Spanish at P1 (auto-detect and switch mid-call; caller-preferred language stored), with an extensible language framework (P3: more languages).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-009

**Deliverable:** Always provide a route to a person

**P1 · MUST · Pending**

**Check:** Keypad input and a request for a human trigger the defined handoff or callback outcome.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Business links:** [BR-024](#br-024).

**Official acceptance links:** [AT-28](#at-28), [AT-34](#at-34).

**Related source references:** [HIL-003](#hil-003).

**Full source text:**

> VOX-009 [P1] MUST support DTMF input and output (for example "press 1 to speak to a person") and a universal "I want a person" intent that triggers HIL-003 within one turn.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-010

**Deliverable:** Recognise voicemail on outgoing call legs

**P1 · MUST · Pending**

**Check:** Transfers and approved callbacks handle voicemail and automated menus as configured.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-010 [P1] MUST detect voicemail/answering-machine and IVR situations on any outbound leg (transfers, callbacks) and behave appropriately (leave message or abort).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-011

**Deliverable:** Handle silence, holds and disconnected calls

**P1 · MUST · Pending**

**Check:** The assistant follows the configured silence limits and preserves the appropriate outcome after disconnection.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-011 [P1] MUST manage silence, hold and dropped calls: prompts after configurable silence, hang-up after N prompts, graceful handling of caller hang-up mid-turn, and full post-call processing even on abrupt termination.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-012

**Deliverable:** Offer approved voices

**P1 · MUST · Pending**

**Check:** Owners select from the approved language voices; P1 does not enable owner voice cloning.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-012 [P1] MUST provide voice selection: a curated set of natural voices per language (with cloning of the owner's voice explicitly out of scope for P1, and only with documented consent in P3). Pronunciation dictionaries per tenant (business names, streets, terms).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-013

**Deliverable:** Avoid interruptions caused by background noise

**P1 · MUST · Pending**

**Check:** Television, wind and echo do not repeatedly interrupt spoken replies in the required audio tests.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-013 [P1] MUST support background-noise-safe barge-in (do not let TV/wind trigger interruption): use VAD tuned per carrier codec and echo cancellation.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-014

**Deliverable:** Adjust speaking style

**P2 · SHOULD · Pending**

**Check:** Configured pace, warmth and brief acknowledgements apply only where enabled for that business.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-014 [P2] SHOULD provide prosody controls (pace, warmth) and backchanneling ("mm-hm") with per-tenant toggles.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-015

**Deliverable:** Handle several people on speakerphone

**P2 · SHOULD · Pending**

**Check:** The assistant confirms who is speaking where needed and avoids unsafe assumptions about identity.

**Owner:** To assign.

**Source:** Technical specification §14.4 Requirements: real-time conversation quality.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-015 [P2] SHOULD support multi-party awareness (speakerphone with two speakers) heuristics and safe behavior (confirm who the account holder is before sharing anything).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-001

**Deliverable:** Answer real business phone calls

**P1 · MUST · Pending**

**Check:** Real inbound calls work through both required P1 carrier integrations behind the common provider interface.

**Owner:** To assign.

**Source:** Technical specification §14.3 Requirements: telephony and numbers.

**Business links:** [BR-001](#br-001).

**Official acceptance links:** [AT-12](#at-12).

**Related source references:** [VOX-036](#vox-036).

**Full source text:**

> VOX-001 [P1] MUST answer inbound PSTN calls via a SIP/PSTN carrier through the TelephonyProvider interface. P1 MUST support two carriers (Twilio and Telnyx) with automatic failover routing at the number or trunk level (VOX-036).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-030

**Deliverable:** Connect an existing or new business number

**P1 · MUST · Pending**

**Check:** Forwarding, new numbers and later porting follow all three source paths and their phase restrictions.

**Owner:** To assign.

**Source:** Technical specification §14.3 Requirements: telephony and numbers.

**Business links:** [BR-001](#br-001), [BR-009](#br-009).

**Official acceptance links:** [AT-02](#at-02), [AT-12](#at-12).

**Full source text:**

> VOX-030 [P1] MUST support three ways to put EverOnn in front of a business's calls:

> 1.  Provisioned local/toll-free number (new number shown on the site);

> 2.  Forwarding from the business's existing number (all calls, no-answer, busy, or after-hours; generate carrier-specific setup instructions and verify with a test call);

> 3.  Number porting into EverOnn (P2, with a guided LOA workflow and status tracking).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-031

**Deliverable:** Test forwarding before activation

**P1 · MUST · Pending**

**Check:** An automated call proves forwarding reaches the right business before the phone channel becomes live.

**Owner:** To assign.

**Source:** Technical specification §14.3 Requirements: telephony and numbers.

**Business links:** [BR-009](#br-009).

**Official acceptance links:** [AT-02](#at-02).

**Full source text:**

> VOX-031 [P1] MUST verify that forwarding is actually working (automated test call and confirmation) before marking the channel live.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-032

**Deliverable:** Let the owner answer first

**P1 · MUST · Pending**

**Check:** The owner's configured ring period expires into the approved AI or backup path.

**Owner:** To assign.

**Source:** Technical specification §14.3 Requirements: telephony and numbers.

**Business links:** [BR-001](#br-001), [BR-009](#br-009).

**Official acceptance links:** [AT-02](#at-02), [AT-12](#at-12).

**Full source text:**

> VOX-032 [P1] MUST provide a ring-owner-first option: ring the owner's phone (and staff numbers) for N seconds (default 15, configurable), then AI answers. Whisper: when the owner answers a forwarded call, no AI disclosure is played.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-033

**Deliverable:** Follow up on a missed call by text

**P1 · MUST · Pending**

**Check:** Eligible missed/disconnected calls create the permitted text-back; consent and opt-out rules are enforced.

**Owner:** To assign.

**Source:** Technical specification §14.3 Requirements: telephony and numbers.

**Business links:** [BR-012](#br-012).

**Official acceptance links:** [AT-20](#at-20).

**Full source text:**

> VOX-033 [P1] MUST support missed-call text-back as a fallback and supplement: if a call ends unanswered (or was answered by AI but the caller dropped), send an SMS (subject to consent rules) inviting them to continue by text (handled by the chat agent).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-034

**Deliverable:** Use the correct caller identity

**P1 · MUST · Pending**

**Check:** Caller details reach the right context, and outbound caller ID is verified against spoofing and privacy rules.

**Owner:** To assign.

**Source:** Technical specification §14.3 Requirements: telephony and numbers.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-034 [P1] MUST support caller ID handling: pass caller ID into context; treat as untrusted; never assume identity from caller ID.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-035

**Deliverable:** Track phone and texting registrations

**P1 · MUST · Pending**

**Check:** Registration status, evidence, failures and required actions are visible to staff and the business.

**Owner:** To assign.

**Source:** Technical specification §14.3 Requirements: telephony and numbers.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [COM-005](#com-005).

**Full source text:**

> VOX-035 [P1] MUST handle A2P 10DLC registration (brand and campaign) and toll-free verification for SMS as a managed background workflow with status visible to support (COM-005).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-036

**Deliverable:** Switch carriers during a failure

**P2 · MUST · Pending**

**Check:** P2 degradation tests prove automatic rerouting within 60 seconds.

**Owner:** To assign.

**Source:** Technical specification §14.3 Requirements: telephony and numbers.

**Business links:** [BR-068](#br-068).

**Official acceptance links:** [AT-49](#at-49).

**Full source text:**

> VOX-036 [P2] MUST support multi-carrier failover with health checks and automatic reroute within 60 seconds of detected carrier degradation.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-037

**Deliverable:** Block phone fraud and artificial traffic

**P1 · MUST · Pending**

**Check:** Caps, allowed destinations and traffic controls stop abuse and alert the responsible team.

**Owner:** To assign.

**Source:** Technical specification §14.3 Requirements: telephony and numbers.

**Business links:** [BR-010](#br-010).

**Official acceptance links:** [AT-48](#at-48).

**Full source text:**

> VOX-037 [P1] MUST implement toll-fraud and traffic-pumping defenses: per-tenant concurrent-call and daily-minute caps, geographic permission lists (default US/Canada), premium-rate and high-cost destination blocks for transfers, alerts on anomalies, and an emergency "kill switch" per tenant and per number.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-038

**Deliverable:** Monitor phone-number reputation

**P1 · SHOULD · Pending**

**Check:** Carrier identity signals and spam-label monitoring produce the required follow-up actions.

**Owner:** To assign.

**Source:** Technical specification §14.3 Requirements: telephony and numbers.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-038 [P1] SHOULD support STIR/SHAKEN attestation awareness and reputation monitoring of provisioned numbers (spam-label detection; P2 for automated remediation).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-040

**Deliverable:** Scale voice workers safely

**P1 · MUST · Pending**

**Check:** Workers load versioned cached business settings and scale without sharing hidden authoritative state.

**Owner:** To assign.

**Source:** Technical specification §14.6 Voice runtime deployment requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [AR-009](#ar-009).

**Full source text:**

> VOX-040 [P1] MUST run voice workers as horizontally scalable, stateless containers that pull tenant configuration from a cache keyed by version, with graceful draining (AR-009).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-041

**Deliverable:** Place voice services near the carrier

**P1 · MUST · Pending**

**Check:** Measured network and media placement meet the specified latency constraints.

**Owner:** To assign.

**Source:** Technical specification §14.6 Voice runtime deployment requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-041 [P1] MUST be latency-aware in placement: media and voice workers deployed in the same region as the carrier edge; multi-region capable by config (P2).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-042

**Deliverable:** Measure each stage and call's cost

**P1 · MUST · Pending**

**Check:** A call's trace identifies speech, retrieval, AI, tools and speech-output stages and attributed cost.

**Owner:** To assign.

**Source:** Technical specification §14.6 Voice runtime deployment requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-042 [P1] MUST emit per-turn traces (OpenTelemetry) covering endpointing, STT, retrieval, LLM, tool, TTS spans, plus per-call cost attribution.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-043

**Deliverable:** Replay calls safely for testing

**P1 · MUST · Pending**

**Check:** Redacted recordings and transcripts can reproduce a staging regression without exposing production personal data.

**Owner:** To assign.

**Source:** Technical specification §14.6 Voice runtime deployment requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [COM-007](#com-007).

**Full source text:**

> VOX-043 [P1] MUST support call replay in staging from recorded audio and transcripts for debugging and regression (with redaction, COM-007).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VOX-044

**Deliverable:** Prepare voice sessions before calls arrive

**P2 · SHOULD · Pending**

**Check:** Pre-initialised sessions reduce first-turn delay within the measured capacity and cost limits.

**Owner:** To assign.

**Source:** Technical specification §14.6 Voice runtime deployment requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VOX-044 [P2] SHOULD support warm pools of pre-initialized agent sessions for common tenants to cut first-turn latency.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-001

**Deliverable:** Add a small, accessible chat widget

**P1 · MUST · Pending**

**Check:** The embeddable widget meets the stated size, privacy, keyboard and screen-reader requirements.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Business links:** [BR-011](#br-011).

**Official acceptance links:** [AT-19](#at-19).

**Full source text:**

> CHT-001 [P1] MUST ship an embeddable widget (single script, under 40 KB gzipped, no third-party cookies, accessible WCAG 2.1 AA, keyboard and screen-reader friendly) with theming from the tenant's brand, mobile-first layout, and lazy loading so it never harms Core Web Vitals.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-002

**Deliverable:** Show chat answers as they arrive

**P1 · MUST · Pending**

**Check:** Streaming chat meets the specified first-token target.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> CHT-002 [P1] MUST stream responses over SSE or WebSocket; first token within 1.5 s p50.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-003

**Deliverable:** Use the same approved assistant in every channel

**P1 · MUST · Pending**

**Check:** Chat and voice share approved knowledge, policies and tools, with the appropriate channel-specific presentation.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Business links:** [BR-011](#br-011).

**Official acceptance links:** [AT-19](#at-19).

**Related source references:** [AGT-001](#agt-001).

**Full source text:**

> CHT-003 [P1] MUST use the same agent brain, KB, playbook, tools and guardrails as voice (AGT-001), with channel-specific style (shorter, links, buttons).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-004

**Deliverable:** Offer helpful chat actions and photo upload

**P1 · MUST · Pending**

**Check:** Required buttons, permitted location capture and safe photo upload work and preserve the request context.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Business links:** [BR-011](#br-011).

**Official acceptance links:** [AT-19](#at-19).

**Full source text:**

> CHT-004 [P1] MUST support rich responses: quick-reply buttons, "Call us", "Text me", location capture (with permission), photo upload (for example a photo of a lock or a leak; virus-scanned, size-limited, stored per tenant), and a contact card.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-005

**Deliverable:** Ask permission before texting a chat visitor

**P1 · MUST · Pending**

**Check:** The displayed consent wording and required evidence are recorded before SMS follow-up.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [COM-002](#com-002).

**Full source text:**

> CHT-005 [P1] MUST capture consent for SMS follow-up in-widget with logged consent text, timestamp, IP and page (COM-002).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-006

**Deliverable:** Keep the visitor's conversation together

**P1 · MUST · Pending**

**Check:** An anonymous chat can link to a captured contact without mixing visitors or businesses.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> CHT-006 [P1] MUST support visitor identity continuity: anonymous session ID, upgraded to a contact on lead capture; the same person across voice, chat and SMS resolves to one Contact via verified identifiers (phone, email) with merge rules and merge audit.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-007

**Deliverable:** Protect chat against spam and cost abuse

**P1 · MUST · Pending**

**Check:** Bot checks and per-session/IP limits prevent abusive traffic from exhausting a business's budget.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> CHT-007 [P1] MUST provide bot protection on the widget (Turnstile/hCaptcha or equivalent risk scoring), rate limits per IP and per session, and origin allow-listing per tenant (widget keys are public and MUST be scoped to allowed origins).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-008

**Deliverable:** Let a human take over the chat

**P1 · MUST · Pending**

**Check:** The human continues the same thread and the AI cannot simultaneously send conflicting replies.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [HIL-004](#hil-004).

**Full source text:**

> CHT-008 [P1] MUST support human takeover in chat (HIL-004): the operator or owner joins the same thread; the widget shows a subtle "a team member has joined" state.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-009

**Deliverable:** Keep text conversations together and honour STOP

**P1 · MUST · Pending**

**Check:** Messages stay in the correct business/contact thread; opt-out commands are handled at the required boundary.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Business links:** [BR-012](#br-012).

**Official acceptance links:** [AT-20](#at-20).

**Full source text:**

> CHT-009 [P1] MUST support SMS threading (one thread per contact per business number), opt-out keywords (STOP/UNSUBSCRIBE/HELP) handling at the platform level, quiet hours (default 9 pm to 8 am recipient local time unless the message is a direct reply), and delivery-status tracking.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-010

**Deliverable:** Start chat with configured invitations

**P2 · SHOULD · Pending**

**Check:** Proactive prompts appear only under the owner's configured page and timing rules.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> CHT-010 [P2] SHOULD support proactive chat triggers (for example, after 20 seconds on the emergency service page) configured per tenant.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-011

**Deliverable:** Save chat and text outcomes in the inbox

**P1 · MUST · Pending**

**Check:** The transcript, summary and structured request follow the same output contract as voice.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Business links:** [BR-011](#br-011).

**Official acceptance links:** [AT-19](#at-19).

**Related source references:** [AGT-008](#agt-008).

**Full source text:**

> CHT-011 [P1] MUST provide transcript and summary delivery with the same structured Request output as voice (AGT-008).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-012

**Deliverable:** Chat in the visitor's language

**P2 · SHOULD · Pending**

**Check:** Language detection and translated responses retain the approved knowledge and safety rules.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> CHT-012 [P2] SHOULD support multilingual chat with automatic language detection.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CHT-013

**Deliverable:** Tell visitors they are speaking with AI

**P1 · MUST · Pending**

**Check:** The required AI notice is visible when the chat begins.

**Owner:** To assign.

**Source:** Technical specification §15.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> CHT-013 [P1] MUST implement an AI disclosure in chat ("You're chatting with the business's AI assistant") that is visible at the start of the conversation.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-007

**Deliverable:** Show the complete client context

**P1 · MUST · Pending**

**Check:** All seven required source context sections belong to the one active business and respect visibility permissions.

**Owner:** To assign.

**Source:** Technical specification §16.4.3 Client context and authority.

**Business links:** [BR-027](#br-027).

**Official acceptance links:** [AT-29](#at-29), [AT-30](#at-30).

**Full source text:**

> DSK-007 [P1] MUST provide a client context panel for the active interaction, with collapsible sections that all belong to that one client:

> Business: name, hours and current status, services, service area, pricing policy, payment methods;

> Instructions: owner notes, special handling, VIP list, blocked or disputed addresses;

> Contacts: who to notify or transfer to, on-call schedule, numbers masked with click-to-bridge;

> Caller history: earlier conversations, open requests and appointments;

> Availability: calendar slots for booking;

> Knowledge search: scoped to this client only;

> Playbook checklist: the slots to complete, prefilled from the AI's capture, editable and validated.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-008

**Deliverable:** Enforce what the operator may promise or do

**P1 · MUST · Pending**

**Check:** Allowed, approval-required and forbidden actions follow the client's authority matrix.

**Owner:** To assign.

**Source:** Technical specification §16.4.3 Client context and authority.

**Business links:** [BR-029](#br-029).

**Official acceptance links:** [AT-31](#at-31).

**Related source references:** [HIL-007](#hil-007).

**Full source text:**

> DSK-008 [P1] MUST enforce the client's authority matrix: for each capability the client sets one of allowed, requires owner approval or not allowed (quote a price, commit an arrival time, book an appointment, dispatch a technician, take payment by link, cancel or reschedule, share technician details, grant an exception). The desk disables or annotates controls accordingly, routes approvals through HIL-007, and the server enforces the same rules. Changes are versioned and audited. Defaults are conservative.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-009

**Deliverable:** Prevent operators from mixing up clients

**P1 · MUST · Pending**

**Check:** A persistent client lock prevents another business's context or credentials entering the active interaction.

**Owner:** To assign.

**Source:** Technical specification §16.4.3 Client context and authority.

**Business links:** [BR-028](#br-028).

**Official acceptance links:** [AT-30](#at-30), [AT-32](#at-32).

**Full source text:**

> DSK-009 [P1] MUST prevent client mix-ups through a client lock: each active interaction has exactly one client context, shown persistently in the header, in every panel, in the browser tab title and, for voice, in the operator-only announcement. When an operator has several interactions open, each is color- and name-coded, and switching shows a visible client-change confirmation. The desk never displays data of two clients in one panel, and the server rejects any action that would attach data from one client to another client's interaction. A one-tap "wrong client" control logs the event and re-routes. Wrong-client incidents (from the operator control, quality findings, or a caller correcting the greeting) are counted and alerted; the target is under 0.1% of interactions.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-010

**Deliverable:** Mask information the operator does not need

**P1 · MUST · Pending**

**Check:** Only client-authorised fields are visible and the specified sensitive values remain masked.

**Owner:** To assign.

**Source:** Technical specification §16.4.3 Client context and authority.

**Business links:** [BR-028](#br-028).

**Official acceptance links:** [AT-30](#at-30), [AT-32](#at-32).

**Full source text:**

> DSK-010 [P1] MUST apply data minimization and masking: the operator sees only fields the client has made visible to operators; sensitive tokens (card numbers, government identifiers) are masked; revealing a masked value requires a reason and is logged; bulk export or listing of contacts is not possible from the desk. A session watermark showing the operator id is a P2 option.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-025

**Deliverable:** Make the desk easy to use by keyboard

**P1 · SHOULD · Pending**

**Check:** Required shortcuts and accessibility checks work without depending on a mouse or colour alone.

**Owner:** To assign.

**Source:** Technical specification §16.4.7 Ergonomics and resilience.

**Business links:** [BR-074](#br-074).

**Official acceptance links:** [AT-52](#at-52).

**Full source text:**

> DSK-025 [P1] SHOULD be keyboard-first and accessible: shortcuts for accept, hold, transfer and wrap-up; a large client banner; light and dark themes; pop-out panels for multiple monitors; screen-reader support; WCAG 2.1 AA; distinct audio cues by severity.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-026

**Deliverable:** Restore the desk after a connection loss

**P1 · MUST · Pending**

**Check:** The server restores authoritative interaction state within the specified target without duplicate handling.

**Owner:** To assign.

**Source:** Technical specification §16.4.7 Ergonomics and resilience.

**Business links:** [BR-036](#br-036).

**Official acceptance links:** [AT-34](#at-34), [AT-37](#at-37).

**Full source text:**

> DSK-026 [P1] MUST be resilient: the server is authoritative for interaction state. A desk reload or reconnect restores the exact state within three seconds and never drops a live call. Heartbeats detect operator disconnection within five seconds (the call returns to the queue or the AI resumes, per policy). A single active desk session per operator is enforced.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-001

**Deliverable:** Track every request for human help

**P1 · MUST · Pending**

**Check:** Escalations retain their reason, urgency, due time, assigned recipient and authoritative state.

**Owner:** To assign.

**Source:** Technical specification §16.3 Escalation, routing and service levels (HIL).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> HIL-001 [P1] MUST model Escalation with: id, tenant_id, conversation_id, trigger_code, severity (p1..p4), state, created_at, sla_due_at, assigned_to, mode (A/B/C), context_snapshot, resolution_code, resolution_notes, audit.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-002

**Deliverable:** Route urgent requests within agreed service times

**P1 · MUST · Pending**

**Check:** Each severity follows its configured deadlines and fallback cascade, including emergency overrides.

**Owner:** To assign.

**Source:** Technical specification §16.3 Escalation, routing and service levels (HIL).

**Business links:** [BR-005](#br-005), [BR-025](#br-025).

**Official acceptance links:** [AT-16](#at-16), [AT-34](#at-34).

**Full source text:**

> HIL-002 [P1] MUST implement severity-based SLAs and cascades (values configurable, defaults below):

**Table belonging to this requirement:**

| Severity | Meaning | First-response SLA | Cascade |
| --- | --- | --- | --- |
| P1 | Safety/emergency, VIP, live caller waiting | Immediate (live transfer) | AI stays on line → warm transfer to owner → next contact → EverOnn operator (if Mode B) → capture callback with P1 alert every 2 min until acknowledged |
| P2 | Live caller wants a human; high-value job | Under 60 s | Owner → operator (B) → callback task |
| P3 | Unresolved question, knowledge gap, messaging needs review | Under 15 min business hours | Owner queue → operator (B) |
| P4 | QA sampling, improvement suggestions | Under 24 h | Operator lead queue |

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-003

**Deliverable:** Give a human-or-callback outcome

**P1 · MUST · Pending**

**Check:** A request for a person leads to a live transfer or a promised scheduled callback within the required turn.

**Owner:** To assign.

**Source:** Technical specification §16.3 Escalation, routing and service levels (HIL).

**Business links:** [BR-024](#br-024).

**Official acceptance links:** [AT-28](#at-28), [AT-34](#at-34).

**Full source text:**

> HIL-003 [P1] MUST guarantee that "I want a person" always produces an outcome: a live transfer if a human is reachable, otherwise a promise-and-capture with a scheduled callback task and SLA. The caller MUST never be trapped in an AI loop.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-004

**Deliverable:** Support live human takeover

**P1 · MUST · Pending**

**Check:** Chat and phone takeover preserve the interaction and support the specified transfer/hand-back controls.

**Owner:** To assign.

**Source:** Technical specification §16.3 Escalation, routing and service levels (HIL).

**Business links:** [BR-024](#br-024).

**Official acceptance links:** [AT-28](#at-28), [AT-34](#at-34).

**Full source text:**

> HIL-004 [P1] MUST support live takeover: a human can join or take over an active chat immediately; for voice, via warm transfer or conference join (listen, whisper to AI, or take over). The AI receives the human's instruction as a privileged context message ("operator whisper") and can continue under supervision.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-005

**Deliverable:** Handle escalations in the operator desk

**P1 · MUST · Pending**

**Check:** Voice, chat and text handling consistently retain business identity, context, authority and audit history.

**Owner:** To assign.

**Source:** Technical specification §16.3 Escalation, routing and service levels (HIL).

**Business links:** [BR-026](#br-026).

**Official acceptance links:** [AT-29](#at-29), [AT-34](#at-34).

**Related source references:** [DSK-011](#dsk-011).

**Full source text:**

> HIL-005 [P1] MUST perform all human handling of voice, chat and SMS escalations through the Live Agent Desk (§16.4), so that client identification, data masking, authority checks, audit, metering and quality review always apply. Operators MUST NOT handle client interactions through personal phones, email or shared inboxes, except the documented telephone fallback in DSK-011.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-006

**Deliverable:** Route work to suitable, available people

**P1 · MUST · Pending**

**Check:** Assignments honour client grants, language, skills, capacity and the stated workforce-management phases.

**Owner:** To assign.

**Source:** Technical specification §16.3 Escalation, routing and service levels (HIL).

**Business links:** [BR-032](#br-032).

**Official acceptance links:** [AT-38](#at-38).

**Full source text:**

> HIL-006 [P1] MUST implement routing and workforce management (simple skills-based routing at P1, full workforce management at P2): skills (language, vertical), shifts and availability, load balancing, priority pre-emption for P1, overflow to secondary pools, fair distribution, and "follow-the-sun" pools. Interfaces are scaffolded in P1: EscalationRouter, OperatorDirectory, ShiftCalendar.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-007

**Deliverable:** Approve sensitive actions before sending

**P1 · MUST · Pending**

**Check:** Actions requiring approval remain drafts until an authorised person approves them.

**Owner:** To assign.

**Source:** Technical specification §16.3 Escalation, routing and service levels (HIL).

**Business links:** [BR-029](#br-029), [BR-034](#br-034).

**Official acceptance links:** [AT-31](#at-31).

**Full source text:**

> HIL-007 [P1] MUST implement approval workflows for sensitive actions that the AI drafts but must not execute alone (per tenant policy): sending a price, confirming a dispatch ETA, issuing a refund credit, sending a bulk message, modifying an existing appointment. Approvers can be owner, staff or operator; approvals are logged.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-015

**Deliverable:** Notify the right people about escalations

**P1 · MUST · Pending**

**Check:** Configured channels and acknowledgement tracking work; emergency rules override quiet hours as specified.

**Owner:** To assign.

**Source:** Technical specification §16.3 Escalation, routing and service levels (HIL).

**Business links:** [BR-025](#br-025).

**Official acceptance links:** [AT-16](#at-16), [AT-34](#at-34).

**Full source text:**

> HIL-015 [P1] MUST provide owner notification preferences for escalations (push, SMS, call, email), quiet hours override for P1 severity, and acknowledgement tracking.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-016

**Deliverable:** Provide a safe fallback when nobody answers

**P1 · SHOULD · Pending**

**Check:** The system captures a detailed request, records the missed service target and creates the correct callback outcome.

**Owner:** To assign.

**Source:** Technical specification §16.3 Escalation, routing and service levels (HIL).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> HIL-016 [P1] SHOULD provide degraded-operator mode: if no human is available within SLA, the system falls back to the safest path (take detailed message, callback task, and clear promise to the caller), and alerts the on-call lead.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-017

**Deliverable:** Carry business identity through the handoff

**P1 · MUST · Pending**

**Check:** Every escalation, offer, interaction, note and audit record retains the same business and line identity.

**Owner:** To assign.

**Source:** Technical specification §16.3 Escalation, routing and service levels (HIL).

**Business links:** [BR-027](#br-027).

**Official acceptance links:** [AT-29](#at-29), [AT-30](#at-30).

**Full source text:**

> HIL-017 [P1] MUST carry client identity through every step: every escalation, offer, interaction, note and audit record holds tenant_id and line_id (or channel endpoint id), and no desk screen or API response may present interaction data without them.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-011

**Deliverable:** Answer through a tested browser phone

**P1 · MUST · Pending**

**Check:** Device selection, audio tests, echo/noise handling and the specified telephone fallback work.

**Owner:** To assign.

**Source:** Technical specification §16.4.4 Handling the interaction.

**Business links:** [BR-030](#br-030), [BR-036](#br-036).

**Official acceptance links:** [AT-33](#at-33), [AT-34](#at-34), [AT-35](#at-35), [AT-37](#at-37).

**Full source text:**

> DSK-011 [P1] MUST provide a browser softphone: WebRTC audio through the media layer, device selection and test, echo cancellation and noise suppression, a network quality indicator, pre-shift diagnostics, automatic reconnection, and a telephone fallback (the platform calls the operator's registered number) if browser audio fails. USB headset call-control buttons via WebHID are P2.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-012

**Deliverable:** Provide the required call controls

**P1 · MUST · Pending**

**Check:** Accept, hold, transfer, join and hand-back actions follow the full source list and remain auditable.

**Owner:** To assign.

**Source:** Technical specification §16.4.4 Handling the interaction.

**Business links:** [BR-030](#br-030).

**Official acceptance links:** [AT-33](#at-33), [AT-35](#at-35).

**Full source text:**

> DSK-012 [P1] MUST provide voice call controls: accept; decline with a reason (returns to the queue); hold and resume with the client's hold audio; mute; warm transfer to the client's contacts with a whispered briefing; cold transfer; add a third party (the owner or a technician); hand back to the AI with an instruction; end; keypad; schedule a callback; send an SMS from client-approved templates; recording and consent indicator. Keyboard shortcuts for the common actions.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-013

**Deliverable:** Handle chats and texts from the same desk

**P1 · MUST · Pending**

**Check:** Operators take over/release threads, review AI drafts and retain the correct business sender identity.

**Owner:** To assign.

**Source:** Technical specification §16.4.4 Handling the interaction.

**Business links:** [BR-030](#br-030).

**Official acceptance links:** [AT-33](#at-33), [AT-35](#at-35).

**Full source text:**

> DSK-013 [P1] MUST handle chat and SMS threads in the same queue and workspace: takeover and release, typing indicators, AI-drafted replies to approve, edit or send, client-specific canned replies, an attachment viewer for photos, and per-operator concurrency (default one voice interaction and up to three chat or SMS threads, configurable; chats are parked automatically when a voice interaction is accepted).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-014

**Deliverable:** Track availability and workload

**P1 · MUST · Pending**

**Check:** Presence, heartbeat expiry, channel capacity and wrap-up prevent unsuitable new assignments.

**Owner:** To assign.

**Source:** Technical specification §16.4.4 Handling the interaction.

**Business links:** [BR-026](#br-026).

**Official acceptance links:** [AT-29](#at-29), [AT-34](#at-34).

**Full source text:**

> DSK-014 [P1] MUST manage presence and capacity: statuses (available, on a call, wrap-up, away, break, offline); capacity-based routing; automatic away after a configurable number of missed offers; shift start checks (microphone and network test, review of client notices); break approval by a lead at P2.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-015

**Deliverable:** Suggest useful answers to operators

**P2 · SHOULD · Pending**

**Check:** P2 suggestions follow approved client knowledge and remain subject to operator control.

**Owner:** To assign.

**Source:** Technical specification §16.4.4 Handling the interaction.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> DSK-015 [P2] SHOULD offer an operator copilot: live suggested questions, knowledge answers, summaries and draft messages under the same guardrails, clearly marked, never executed automatically, with operator feedback and measured effect on handling time and quality scores.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-016

**Deliverable:** Call back from the correct business line

**P1 · MUST · Pending**

**Check:** Only permitted initiated interactions can be called back; identity and compliance checks are visible.

**Owner:** To assign.

**Source:** Technical specification §16.4.4 Handling the interaction.

**Business links:** [BR-030](#br-030).

**Official acceptance links:** [AT-33](#at-33), [AT-35](#at-35).

**Related source references:** [COM-012](#com-012).

**Full source text:**

> DSK-016 [P1] MUST support callbacks and outbound calls from the desk only for interactions the caller or the client initiated: click-to-call showing the client's business number as caller ID, an outbound greeting script ("calling on behalf of {client_name}"), calling-hour and consent checks, and full logging. No cold outbound calling (COM-012).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-017

**Deliverable:** Match the caller's language

**P1 · MUST · Pending**

**Check:** Offers display language and route to qualified people or the specified safe fallback.

**Owner:** To assign.

**Source:** Technical specification §16.4.4 Handling the interaction.

**Business links:** [BR-006](#br-006).

**Official acceptance links:** [AT-17](#at-17).

**Full source text:**

> DSK-017 [P1] MUST handle language: the offer shows the caller's language; routing prefers operators skilled in it (English and Spanish at P1); the operator can switch language mid-conversation; an interpreter path is P3.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-004

**Deliverable:** Show who the call is for immediately

**P1 · MUST · Pending**

**Check:** The offer displays every one of the seven required source information groups without extra clicks.

**Owner:** To assign.

**Source:** Technical specification §16.4.2 Incoming interaction, screen-pop and greeting.

**Business links:** [BR-027](#br-027).

**Official acceptance links:** [AT-29](#at-29), [AT-30](#at-30).

**Related source references:** [DSK-006](#dsk-006), [VRT-008](#vrt-008).

**Full source text:**

> DSK-004 [P1] MUST present a screen-pop offer card at the moment an interaction is offered, with no clicks needed to see who it is for:

> client name in large type on the client's brand color, line label and number, client status (open, closed, after hours), and the client's spoken-name pronunciation hint;

> the greeting to say, ready to read (DSK-006);

> caller number and name if known, returning-caller indicator, language;

> severity and why this interaction is with a human (the trigger);

> the AI summary so far, the details already captured (each with confidence and an "unconfirmed" marker) and a live transcript;

> waiting time and the accept and decline controls.

> The full context payload MUST be pushed to the desk before the offer rings, and the card MUST render within 500 ms of the offer at p95. The EverOnn brand under which the client is served appears as a small secondary tag (VRT-008).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-005

**Deliverable:** Brief the operator privately

**P1 · MUST · Pending**

**Check:** The operator hears the correct briefing before the bridge; the caller never hears that private announcement.

**Owner:** To assign.

**Source:** Technical specification §16.4.2 Incoming interaction, screen-pop and greeting.

**Business links:** [BR-027](#br-027).

**Official acceptance links:** [AT-29](#at-29), [AT-30](#at-30).

**Full source text:**

> DSK-005 [P1] MUST support an operator-only announcement for voice: on acceptance, and before the caller is bridged, the operator hears a brief synthesized announcement naming the client and the situation ("Acme Locksmith. Car lockout. Caller Maria. Urgent."), inaudible to the caller. The caller meanwhile hears a short branded hold message ("One moment, I'm connecting you to a team member at Acme Locksmith"). The announcement is on by default for voice and configurable per operator and per client. The audio topology that keeps the announcement private is decided in the Phase 0 spike (§16.7.2).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-006

**Deliverable:** Show the right greeting script

**P1 · MUST · Pending**

**Check:** The greeting matches the business, language and hours/callback context.

**Owner:** To assign.

**Source:** Technical specification §16.4.2 Incoming interaction, screen-pop and greeting.

**Business links:** [BR-027](#br-027).

**Official acceptance links:** [AT-29](#at-29), [AT-30](#at-30).

**Full source text:**

> DSK-006 [P1] MUST manage greeting scripts per client: per language and per hours mode (business hours, after hours, callback), with variables {client_name}, {operator_first_name}, {line_label}, the spoken name and a phonetic hint, time-of-day variants, an outbound variant ("calling on behalf of {client_name}"), and a "do not say" list. Scripts are versioned and approved by the client (or by EverOnn operations on the client's behalf, recorded). The desk shows the script as copy-ready text with a one-key "greeting delivered" marker that is logged so greeting compliance can be measured. If no script exists, the default is a neutral greeting that includes the client name.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-001

**Deliverable:** Work from one operator queue

**P1 · MUST · Pending**

**Check:** Permitted calls, chats, texts, callbacks and approval work appear in one queue with the required filters.

**Owner:** To assign.

**Source:** Technical specification §16.4.1 Multi-client operations.

**Business links:** [BR-026](#br-026).

**Official acceptance links:** [AT-29](#at-29), [AT-34](#at-34).

**Full source text:**

> DSK-001 [P1] MUST provide one unified queue across clients: pending and active voice offers, chats, SMS threads, callbacks, approvals and knowledge gaps for every client the operator is granted, each item showing the client name (with a brand color chip), line label, channel, severity, waiting time and service-level countdown, and language. Sort by severity then deadline; filter by client, channel, severity and language. An operator never sees items for clients they are not granted.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-002

**Deliverable:** Assign operators to permitted clients

**P1 · MUST · Pending**

**Check:** Grants specify client scope and authority; revocation takes effect on subsequent access and commands.

**Owner:** To assign.

**Source:** Technical specification §16.4.1 Multi-client operations.

**Business links:** [BR-026](#br-026), [BR-032](#br-032).

**Official acceptance links:** [AT-29](#at-29), [AT-34](#at-34), [AT-38](#at-38).

**Full source text:**

> DSK-002 [P1] MUST implement the client roster and grants: an operator is granted access per client (or per client group, vertical or brand) with skills, certification date and optional expiry. A grant is required both for routing to the operator and for seeing any client data. Granting requires the client-specific training checklist to be recorded as complete (BRL-019). Revocation takes effect within five seconds, including for interactions already open (the operator is moved out and the interaction re-routed). Every grant, change and revocation is audited.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-003

**Deliverable:** Identify which business was called

**P1 · MUST · Pending**

**Check:** The number and carrier leg resolve to the correct business and line before an offer is shown.

**Owner:** To assign.

**Source:** Technical specification §16.4.1 Multi-client operations.

**Business links:** [BR-027](#br-027), [BR-028](#br-028).

**Official acceptance links:** [AT-29](#at-29), [AT-30](#at-30), [AT-32](#at-32).

**Full source text:**

> DSK-003 [P1] MUST perform line identification: each inbound leg is resolved to tenant_id and line_id from the dialed number and the carrier's signaling (the To, Diversion and History-Info headers and provider metadata), cross-checked against the number registry. The resolved line label (for example "Acme Locksmith, after-hours emergency line") travels with the escalation. If the line cannot be resolved with confidence (unknown number, ambiguous forwarding chain, inconsistent headers), the desk MUST show a prominent UNKNOWN LINE state, hide all client data, offer only a neutral greeting ("Thank you for calling, how can I help?"), and open a support incident. The system MUST NOT guess the client.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-018

**Deliverable:** Handle offers, declines and timeouts reliably

**P1 · MUST · Pending**

**Check:** Only one valid acceptance wins; other offers cancel and declined/expired offers continue the configured cascade.

**Owner:** To assign.

**Source:** Technical specification §16.4.5 Offers, routing behavior and wrap-up.

**Business links:** [BR-026](#br-026), [BR-036](#br-036).

**Official acceptance links:** [AT-29](#at-29), [AT-34](#at-34), [AT-37](#at-37).

**Full source text:**

> DSK-018 [P1] MUST implement offer, ring and cascade behavior: offers expire after a configurable time (default 15 seconds); strategies include longest-idle and skills-first (ring-all-eligible at P2); the first acceptance wins through an atomic assignment; a decline or timeout moves to the next operator per the cascade; when no operator accepts within the service level the cascade continues (overflow pool, then the client's owner, then message capture with a promised callback and repeated alerts for emergencies). While the caller waits they hear branded hold messages, an offer to leave a message, and periodic updates. Every step is logged with timestamps.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-019

**Deliverable:** Record the outcome before finishing work

**P1 · MUST · Pending**

**Check:** Wrap-up captures the required disposition and next action before the operator becomes available as configured.

**Owner:** To assign.

**Source:** Technical specification §16.4.5 Offers, routing behavior and wrap-up.

**Business links:** [BR-030](#br-030).

**Official acceptance links:** [AT-33](#at-33), [AT-35](#at-35).

**Full source text:**

> DSK-019 [P1] MUST require wrap-up: after the interaction the operator selects a disposition (resolved, message taken, transferred to owner, callback scheduled, spam, wrong number, other), corrects the structured request, adds notes visible to the client, sets a follow-up task and sends the client summary. Wrap-up has a timer (default 60 seconds, configurable) with automatic release; fields required per client are enforced; the operator cannot accept another voice offer until wrap-up is complete or the timer expires.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-008

**Deliverable:** Let owners review and correct answers

**P1 · MUST · Pending**

**Check:** Owner feedback produces reviewable knowledge suggestions rather than immediately changing approved AI behaviour.

**Owner:** To assign.

**Source:** Technical specification §16.5 Quality, learning and control of the human layer.

**Business links:** [BR-023](#br-023).

**Official acceptance links:** [AT-39](#at-39).

**Related source references:** [KNW-005](#knw-005).

**Full source text:**

> HIL-008 [P1] MUST support post-conversation review by the owner: thumbs up/down, "correct this answer", "add to knowledge", "never say this". Owner corrections create KB proposals (KNW-005) and eval cases (§24.5).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-009

**Deliverable:** Review risky conversations for quality

**P2 · MUST · Pending**

**Check:** Risk-weighted samples can be scored, followed up and reported against the stated quality measures.

**Owner:** To assign.

**Source:** Technical specification §16.5 Quality, learning and control of the human layer.

**Business links:** [BR-033](#br-033).

**Official acceptance links:** [AT-35](#at-35).

**Full source text:**

> HIL-009 [P2] MUST implement QA sampling and scoring: automatic risk-weighted sampling (guardrail hits, low confidence, escalations, new tenants first, random baseline 2%), reviewer UI with rubric (accuracy, safety, tone, outcome), reviewer agreement tracking, and score trends per tenant, per agent version and per vertical.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-010

**Deliverable:** Turn reviewed outcomes into improvements

**P2 · MUST · Pending**

**Check:** Human resolutions produce approved, tested and versioned knowledge/playbook changes.

**Owner:** To assign.

**Source:** Technical specification §16.5 Quality, learning and control of the human layer.

**Business links:** [BR-033](#br-033).

**Official acceptance links:** [AT-35](#at-35).

**Full source text:**

> HIL-010 [P2] MUST close the learning loop: operator resolutions and QA findings produce (a) KB/profile suggestions, (b) playbook or prompt change candidates, (c) new regression cases added to the eval set with reviewer approval. Nothing changes production behavior without passing the eval gate (§24.5).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-011

**Deliverable:** Record every human intervention

**P1 · MUST · Pending**

**Check:** The audit trail identifies who acted, when and what changed.

**Owner:** To assign.

**Source:** Technical specification §16.5 Quality, learning and control of the human layer.

**Business links:** [BR-033](#br-033).

**Official acceptance links:** [AT-35](#at-35).

**Related source references:** [SEC-009](#sec-009).

**Full source text:**

> HIL-011 [P1] MUST record every human intervention with actor, time, action, and before/after state in the immutable audit log (SEC-009).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-012

**Deliverable:** Measure human-handling usage

**P2 · MUST · Pending**

**Check:** Takeover time, completed callbacks and reviews are counted according to the plan without duplicate charging.

**Owner:** To assign.

**Source:** Technical specification §16.5 Quality, learning and control of the human layer.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [BIL-004](#bil-004).

**Full source text:**

> HIL-012 [P2] MUST support billing and metering of HITL: minutes of live takeover, callbacks completed, reviews performed, per plan allowances and overage (BIL-004).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-013

**Deliverable:** Protect operator access

**P1 · MUST · Pending**

**Check:** The phase-appropriate login, device, access and personal-data restrictions are enforced.

**Owner:** To assign.

**Source:** Technical specification §16.5 Quality, learning and control of the human layer.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> HIL-013 [P1] MUST apply operator security controls (minimum set at P1, full set at P2): least-privilege access (only assigned tenants and only the fields needed), MFA, device posture checks, session recording of console actions (not customer audio beyond policy), NDA/training attestation tracking, IP allow-listing for pooled operators, and automatic access expiry at shift end. Operators MUST NOT be able to export bulk data.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### HIL-014

**Deliverable:** Support separate partner operator teams

**P2 · SHOULD · Pending**

**Check:** Partner teams see only their permitted client work and retain separate service and performance reporting.

**Owner:** To assign.

**Source:** Technical specification §16.5 Quality, learning and control of the human layer.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> HIL-014 [P2] SHOULD support partner/BPO operator pools as external tenants of the console with strict data segmentation, SLAs and per-partner reporting (scaffold identity model for external operator orgs in P1).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-020

**Deliverable:** Give supervisors a live service overview

**P2 · MUST · Pending**

**Check:** P2 dashboards show queues, wait times, service targets and operator state by permitted scope.

**Owner:** To assign.

**Source:** Technical specification §16.4.6 Supervision, staffing and visibility.

**Business links:** [BR-031](#br-031).

**Official acceptance links:** [AT-38](#at-38).

**Full source text:**

> DSK-020 [P2] MUST provide a supervisor wall board in real time by client, pool and operator: queue depth, longest wait, service-level status, abandon rate, operators by status, active interactions with client names, and alerts when a service level is at risk.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-021

**Deliverable:** Let supervisors assist with calls

**P2 · MUST · Pending**

**Check:** Monitor, whisper, join, takeover and reassignment use proper permissions and recording/audit rules.

**Owner:** To assign.

**Source:** Technical specification §16.4.6 Supervision, staffing and visibility.

**Business links:** [BR-031](#br-031).

**Official acceptance links:** [AT-38](#at-38).

**Full source text:**

> DSK-021 [P2] MUST provide supervision tools: silent monitor, whisper to the operator, barge-in, take over, and reassign. All are logged, follow the applicable monitoring notice rules, and are restricted to operator_lead.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-022

**Deliverable:** Plan staffing and shifts

**P2 · MUST · Pending**

**Check:** P2 staffing tools use skills, shifts and measured demand without presenting planning assumptions as actual results.

**Owner:** To assign.

**Source:** Technical specification §16.4.6 Supervision, staffing and visibility.

**Business links:** [BR-032](#br-032).

**Official acceptance links:** [AT-38](#at-38).

**Full source text:**

> DSK-022 [P2] MUST provide workforce and staffing tools: skills, shifts, forecast-based staffing suggestions (§16.7.5), adherence and break scheduling. Simple per-client coverage windows (the hours during which operators may take a client's calls) are P1.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-023

**Deliverable:** Show clients when a human handled a request

**P1 · MUST · Pending**

**Check:** The inbox identifies human handling and the required details without exposing inappropriate operator information.

**Owner:** To assign.

**Source:** Technical specification §16.4.6 Supervision, staffing and visibility.

**Business links:** [BR-035](#br-035).

**Official acceptance links:** [AT-36](#at-36).

**Full source text:**

> DSK-023 [P1] MUST give clients visibility of human handling: interactions handled by an operator are flagged in the client's inbox ("Handled by the EverOnn team: Sam"), with duration, disposition, notes and recording per policy. The client can rate an interaction or report a problem, which feeds quality review.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DSK-024

**Deliverable:** Measure each handling stage

**P1 · MUST · Pending**

**Check:** Offer, ring, acceptance, talk, hold, transfer and wrap-up times are recorded for service and cost reporting.

**Owner:** To assign.

**Source:** Technical specification §16.4.6 Supervision, staffing and visibility.

**Business links:** [BR-033](#br-033).

**Official acceptance links:** [AT-35](#at-35).

**Full source text:**

> DSK-024 [P1] MUST record handling data: every offer, ring, acceptance, talk, hold, transfer, wrap-up and disposition is stored with timestamps. This feeds metering of operator minutes, quality sampling, service-level reporting and operator scorecards.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BKG-001

**Deliverable:** Connect the owner's calendar securely

**P1 · MUST · Pending**

**Check:** Required calendar providers work with minimal data access, encrypted tokens and safe handling of revoked access.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Business links:** [BR-008](#br-008).

**Official acceptance links:** [AT-18](#at-18).

**Related source references:** [SEC-005](#sec-005).

**Full source text:**

> BKG-001 [P1] MUST integrate calendars via OAuth (Google Calendar, Microsoft 365) and Cal.com; store only the minimum (free/busy plus created events), refresh tokens encrypted (SEC-005), and handle token revocation gracefully.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BKG-002

**Deliverable:** Offer appointments that fit business rules

**P1 · MUST · Pending**

**Check:** Hours, durations, buffers, lead time and closures affect availability; later-phase rules remain phase-labelled.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Business links:** [BR-008](#br-008).

**Official acceptance links:** [AT-18](#at-18).

**Full source text:**

> BKG-002 [P1] MUST implement availability rules: business hours, service durations, buffers, travel-time estimates (P2), lead time, max per day, staff/technician assignment (P2), and holiday closures.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BKG-003

**Deliverable:** Prevent two people booking the same slot

**P1 · MUST · Pending**

**Check:** Simultaneous bookings cannot claim the same slot; the unsuccessful caller receives alternatives.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Business links:** [BR-008](#br-008).

**Official acceptance links:** [AT-18](#at-18).

**Full source text:**

> BKG-003 [P1] MUST implement atomic booking with conflict detection (optimistic locking) so two simultaneous callers cannot book the same slot; the agent offers alternatives when a slot is taken.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BKG-004

**Deliverable:** Confirm, remind and change appointments

**P1 · MUST · Pending**

**Check:** Permitted confirmations/reminders include working cancel/reschedule links that update the connected calendar.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> BKG-004 [P1] MUST send confirmations and reminders (SMS/email) with reschedule and cancel links; customer-initiated changes flow back to the calendar.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BKG-005

**Deliverable:** Connect field-service systems in the later phase

**P3 · MAY · Pending**

**Check:** The P2 provider interface is prepared and P3 connections follow approved provider access.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> BKG-005 [P3] MAY integrate field-service systems (Jobber, Housecall Pro, ServiceTitan, Workiz) via an FsmProvider interface scaffolded at P2.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### FUP-001

**Deliverable:** Follow up with customers automatically

**P2 · MUST · Pending**

**Check:** P2 sequences use recorded consent, quiet hours, delays, exit rules and suppression.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Business links:** [BR-038](#br-038).

**Official acceptance links:** [AT-57](#at-57).

**Related source references:** [COM-002](#com-002).

**Full source text:**

> FUP-001 [P2] MUST provide automated follow-up sequences (SMS/email): missed-call text-back, quote reminders, appointment reminders, post-job review requests, reactivation of stale leads. Sequences are templates with steps, delays, exit conditions, and per-contact suppression; all sends honor consent and quiet hours (COM-002).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### FUP-002

**Deliverable:** Request reviews under an approved policy

**P2 · MUST · Pending**

**Check:** The proposed review workflow passes the required platform-policy review before any sentiment-based gating is enabled.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Business links:** [BR-038](#br-038).

**Official acceptance links:** [AT-57](#at-57).

**Full source text:**

> FUP-002 [P2] MUST support review generation: post-job SMS with a Google review link, with negative-sentiment gating that routes unhappy customers to the owner privately (subject to platform policy compliance; the studio MUST review Google's review-solicitation policies before shipping any gating).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### FUP-003

**Deliverable:** Show the enquiry-to-job pipeline

**P2 · SHOULD · Pending**

**Check:** Pipeline counts and estimated recovered revenue use visible, owner-editable assumptions.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> FUP-003 [P2] SHOULD provide simple pipeline metrics (calls to requests to booked to done) and estimated recovered revenue with owner-editable average job values.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### INB-001

**Deliverable:** See all customer requests in one inbox

**P1 · MUST · Pending**

**Check:** Calls, chats, texts and forms can be searched, filtered and triaged on a phone.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Business links:** [BR-037](#br-037).

**Official acceptance links:** [AT-57](#at-57).

**Full source text:**

> INB-001 [P1] MUST provide a unified inbox (responsive web, PWA-installable) listing conversations and requests with filters (status, urgency, channel, assignee, date), search (name, phone, text), and a mobile-first triage view built for one-thumb use.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### INB-002

**Deliverable:** Review the complete conversation

**P1 · MUST · Pending**

**Check:** Transcript, permitted audio, summary, extracted details, confidence and AI reasoning sources can be inspected together.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Business links:** [BR-035](#br-035), [BR-037](#br-037).

**Official acceptance links:** [AT-36](#at-36), [AT-57](#at-57).

**Related source references:** [KNW-009](#knw-009).

**Full source text:**

> INB-002 [P1] MUST show each conversation with transcript, audio player with waveform and transcript sync, AI summary, extracted fields with confidence indicators, tool log, and "why the AI said this" (KNW-009).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### INB-003

**Deliverable:** Reply to a customer from the inbox

**P1 · MUST · Pending**

**Check:** SMS/email replies use the correct business and require approval unless an authorised policy enables auto-send.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Business links:** [BR-037](#br-037).

**Official acceptance links:** [AT-57](#at-57).

**Full source text:**

> INB-003 [P1] MUST allow staff to reply by SMS or email from the inbox (AI-drafted replies are suggestions requiring one tap to send unless auto-send is enabled by policy).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### INB-004

**Deliverable:** Assign work, add notes and call back

**P1 · MUST · Pending**

**Check:** Staff can assign, tag and update requests and call back using the business's caller identity.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Business links:** [BR-037](#br-037).

**Official acceptance links:** [AT-57](#at-57).

**Full source text:**

> INB-004 [P1] MUST support assignment, notes, status changes, tags, and one-tap "call back" (click-to-call bridging via provider so the business's caller ID is shown to the customer).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### INB-005

**Deliverable:** Merge duplicate contacts safely

**P1 · MUST · Pending**

**Check:** A merge preview uses verified identity keys and records an auditable merge.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> INB-005 [P1] MUST de-duplicate and merge contacts (verified phone/email keys), with merge preview and audit.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### INB-006

**Deliverable:** Choose notification preferences

**P1 · MUST · Pending**

**Check:** Channel/severity settings and quiet hours are respected, with the required emergency override.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Business links:** [BR-007](#br-007).

**Official acceptance links:** [AT-12](#at-12).

**Full source text:**

> INB-006 [P1] MUST give owners notifications with per-channel, per-severity preferences and quiet hours; P1 severity bypasses quiet hours.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### INB-007

**Deliverable:** Export requests or connect other tools

**P1 · SHOULD · Pending**

**Check:** CSV export and permitted new-request automation work without exposing another business's data.

**Owner:** To assign.

**Source:** Technical specification §17.2 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [API-004](#api-004).

**Full source text:**

> INB-007 [P1] SHOULD provide export (CSV) and Zapier/webhook triggers for new requests (API-004).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-001

**Deliverable:** Generate a complete private website preview

**P1 · MUST · Pending**

**Check:** All six generation stages, the two-minute preview target, P2 throughput and site-cost controls are verified.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Business links:** [BR-014](#br-014), [BR-018](#br-018).

**Official acceptance links:** [AT-01](#at-01), [AT-05](#at-05).

**Full source text:**

> WEB-001 [P1] MUST implement the generation pipeline as durable jobs: (1) data collection (profile, imported content), (2) content generation with schema-constrained LLM output and brand/tone controls, (3) image selection or generation from licensed sources and the owner's photos (P1: owner photos, licensed stock; generated imagery only where licensing and disclosure rules are met), (4) Site Spec validation and safety checks (no invented licenses, awards, or claims), (5) render, (6) preview deployment. Target: under 2 minutes p50 to preview; throughput target 1,000 sites/day sustained with burst to 300 per hour (P2), with per-site LLM cost tracked and capped.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-002

**Deliverable:** Use only truthful business claims

**P1 · MUST · Pending**

**Check:** Unsupported reviews, credentials, guarantees and prices are rejected or flagged for owner confirmation.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Business links:** [BR-014](#br-014), [BR-019](#br-019).

**Official acceptance links:** [AT-01](#at-01), [AT-05](#at-05).

**Full source text:**

> WEB-002 [P1] MUST ensure content claim safety: the generator MUST NOT fabricate reviews, certifications, years in business, service guarantees, or prices. Any claim must trace to a source field or be flagged for owner confirmation. Preview shows "unverified claims" highlights the owner must resolve.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-003

**Deliverable:** Keep unapproved previews private

**P1 · MUST · Pending**

**Check:** Previews are non-indexable and unguessable, conceal real contact details and expire when unclaimed.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Business links:** [BR-014](#br-014), [BR-015](#br-015), [BR-054](#br-054).

**Official acceptance links:** [AT-01](#at-01), [AT-24](#at-24).

**Related source references:** [ONB-002](#onb-002).

**Full source text:**

> WEB-003 [P1] MUST keep previews private and non-indexable (noindex, unguessable URLs, no real phone or address exposure per ONB-002) until verification and owner approval; preview TTL and cleanup jobs apply to unclaimed prospects.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-004

**Deliverable:** Connect a domain with automatic security

**P1 · MUST · Pending**

**Check:** Verified custom domains, certificates, renewals, redirects and health alerts work; later domain purchase stays P2.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Business links:** [BR-016](#br-016).

**Official acceptance links:** [AT-03](#at-03).

**Full source text:**

> WEB-004 [P1] MUST support custom domains: guided DNS setup (CNAME/ALIAS or nameservers), automatic TLS certificate issuance and renewal per hostname (ACME; on-demand TLS at the edge), domain verification, apex and www handling, redirects, and health monitoring with alerts. At P2, EverOnn can register domains on the owner's behalf through a registrar API.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-005

**Deliverable:** Isolate customer websites from platform domains

**P1 · MUST · Pending**

**Check:** Customer sites use a separate registrable domain and cannot inherit application cookies or privileges.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Business links:** [BR-019](#br-019).

**Official acceptance links:** [AT-01](#at-01), [AT-05](#at-05).

**Full source text:**

> WEB-005 [P1] MUST serve tenant sites on a separate registrable domain from EverOnn's own application and marketing domains (for example everonn.site), so cookies, XSS blast radius, email reputation and SEO reputation are isolated.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-006

**Deliverable:** Make sites fast and search-ready

**P1 · MUST · Pending**

**Check:** Required metadata and sourced structured data are present; sampled sites meet every stated mobile performance threshold.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Business links:** [BR-017](#br-017).

**Official acceptance links:** [AT-04](#at-04).

**Full source text:**

> WEB-006 [P1] MUST generate SEO and AEO/GEO-ready markup: semantic HTML, LocalBusiness (and subtype) JSON-LD, FAQPage, Service, OpeningHoursSpecification, AggregateRating only when real and sourced, sitemap.xml, robots.txt, canonical tags, Open Graph, llms.txt and clean Q&amp;A content blocks. Lighthouse mobile scores of 90 or more on all four categories, LCP under 2.5 s, CLS under 0.1 (measured in CI on a sample of generated sites).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-007

**Deliverable:** Include chat, calls and enquiry forms

**P1 · MUST · Pending**

**Check:** Default contact actions deliver the right request to the inbox with spam and consent controls.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Business links:** [BR-013](#br-013).

**Official acceptance links:** [AT-04](#at-04), [AT-19](#at-19).

**Full source text:**

> WEB-007 [P1] MUST embed the AI chat widget, click-to-call (tel: with tracking number), and lead forms by default, with spam protection (Turnstile/hCaptcha), rate limits, consent capture and delivery into the inbox.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-008

**Deliverable:** Let owners edit and undo site changes

**P1 · MUST · Pending**

**Check:** Owners edit the permitted fields, publish a new version and roll back; raw tenant HTML editing is unavailable in P1.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> WEB-008 [P1] MUST provide a simple owner editor: edit text, hours, services, photos, colors, and reorder sections in the dashboard; changes create a new version; publish and rollback. No raw HTML editing by tenants at P1 (security).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-009

**Deliverable:** Prevent unsafe website content

**P1 · MUST · Pending**

**Check:** Untrusted content is sanitised; scripts and embeds follow the P1 allow-list and content-security policy.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> WEB-009 [P1] MUST sanitize all tenant-supplied content and enforce a strict Content Security Policy on tenant sites; tenant scripts and arbitrary embeds are prohibited at P1 (allow-listed embeds such as Google Maps only).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-010

**Deliverable:** Show where website enquiries come from

**P1 · MUST · Pending**

**Check:** Privacy-conscious page/action counts and source attribution match the required phase scope.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> WEB-010 [P1] MUST support analytics for tenants: privacy-friendly first-party page views, click-to-call taps, form submissions, chat starts, source attribution (call tracking numbers per source at P2).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-011

**Deliverable:** Update many sites safely

**P2 · MUST · Pending**

**Check:** P2 queued updates show progress and use canary/rollback controls without replacing unrelated content.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Business links:** [BR-018](#br-018).

**Official acceptance links:** [AT-05](#at-05).

**Full source text:**

> WEB-011 [P2] MUST support bulk operations: template updates rolled out across all sites (with canary and rollback), bulk regeneration, and bulk domain checks; all through queued jobs with progress reporting.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-012

**Deliverable:** Create useful service and area pages

**P2 · SHOULD · Pending**

**Check:** P2 pages meet the documented quality policy and avoid thin or duplicate search content.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> WEB-012 [P2] SHOULD provide multi-page vertical templates (service pages, city/area pages generated from service-area data with quality thresholds to avoid thin or duplicate content; the studio MUST document a policy to avoid search-spam patterns).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-013

**Deliverable:** Prevent fake sites and handle abuse reports

**P1 · MUST · Pending**

**Check:** Prohibited or impersonating sites are blocked; reporting and rapid authorised takedown work.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Business links:** [BR-019](#br-019).

**Official acceptance links:** [AT-01](#at-01), [AT-05](#at-05).

**Full source text:**

> WEB-013 [P1] MUST implement abuse controls: block generation for prohibited business categories, prevent phishing/impersonation sites (brand and domain similarity checks), takedown workflow (admin action within minutes), and a report-abuse link on every site.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-014

**Deliverable:** Serve sites quickly and refresh changes

**P1 · MUST · Pending**

**Check:** Static assets, caching and publish-time invalidation meet the required independent site-serving design.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> WEB-014 [P1] MUST implement CDN and cache strategy: immutable hashed assets, short HTML TTL with instant purge on publish, stale-while-revalidate, and origin shielding; the origin holds no per-request state.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-015

**Deliverable:** Support English and Spanish websites

**P2 · SHOULD · Pending**

**Check:** P2 language versions are represented correctly in the Site Spec and generated site.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> WEB-015 [P2] SHOULD support i18n (English and Spanish first) at the Site Spec level.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-016

**Deliverable:** Use the right industry website content

**P1 · MUST · Pending**

**Check:** Each pack supplies appropriate sections and vocabulary while every claim remains source-checked.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Business links:** [BR-046](#br-046).

**Official acceptance links:** [AT-07](#at-07).

**Related source references:** [WEB-002](#web-002).

**Full source text:**

> WEB-016 [P1] MUST provide vertical site templates and content libraries per pack (section variants, vocabulary, trust elements, service pages); the generation pipeline uses the pack's knowledge, and every generated claim remains subject to WEB-002.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-017

**Deliverable:** Show the correct brand and legal identity

**P1 · MUST · Pending**

**Check:** Domains, previews, legal pages and optional provider credits accurately identify the business and provider.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> WEB-017 [P1] MUST publish sites under the client's own domain, with brand-specific preview and staging hosts and brand-specific legal pages, and a per-brand, per-plan option for a "powered by" credit; no page may give a misleading impression about the provider or its independence (BRL-032).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### WEB-018

**Deliverable:** Add the website features each industry needs

**P2 · SHOULD · Pending**

**Check:** P2 industry components follow the source list; regulated launches still require their later compliance gate.

**Owner:** To assign.

**Source:** Technical specification §18.3 Requirements.

**Business links:** [BR-048](#br-048).

**Official acceptance links:** [AT-09](#at-09).

**Full source text:**

> WEB-018 [P2] SHOULD provide vertical parity components per pack, delivered by building, embedding or connecting: accounting (secure client portal through a connector first; newsletters and tax-content library), auto repair (service pages, offers, review display), dental and medical (patient forms, scheduling embed), law (practice-area pages, intake forms), insurance (coverage pages, quote request), restaurants (ordering pages).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ADM-001

**Deliverable:** Provide a protected administration workspace

**P1 · MUST · Pending**

**Check:** Authorised administrators manage clients through a separate protected app with reasoned, audited support access.

**Owner:** To assign.

**Source:** Technical specification §19.3 Admin back-office (ADM).

**Business links:** [BR-070](#br-070).

**Official acceptance links:** [AT-58](#at-58).

**Related source references:** [ACC-002](#acc-002).

**Full source text:**

> ADM-001 [P1] MUST provide an internal admin app (separate deployment and hostname, SSO plus MFA, IP-restricted) to search tenants; view state, config versions, numbers, usage and cost; replay and inspect conversations with reasons; manage plans and entitlements; suspend, unsuspend and close tenants; run support impersonation (ACC-002).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ADM-002

**Deliverable:** Control rollouts and stop faulty features

**P1 · MUST · Pending**

**Check:** Flags support scoped releases and immediate capability/provider kill switches with audit records.

**Owner:** To assign.

**Source:** Technical specification §19.3 Admin back-office (ADM).

**Business links:** [BR-043](#br-043), [BR-070](#br-070).

**Official acceptance links:** [AT-25](#at-25), [AT-55](#at-55), [AT-58](#at-58).

**Full source text:**

> ADM-002 [P1] MUST provide feature flags and staged rollouts (per tenant, per plan, percentage), a kill switch per capability and per vendor, and audit of flag changes. Flags are evaluated via an OpenFeature-compatible interface.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ADM-003

**Deliverable:** Review and release AI policy changes

**P1 · MUST · Pending**

**Check:** Changes have a diff, approval, evaluation result, staged rollout and immediate rollback.

**Owner:** To assign.

**Source:** Technical specification §19.3 Admin back-office (ADM).

**Business links:** [BR-070](#br-070), [BR-076](#br-076).

**Official acceptance links:** [AT-15](#at-15), [AT-54](#at-54), [AT-58](#at-58).

**Full source text:**

> ADM-003 [P1] MUST provide prompt and policy management: versioned platform policy and vertical templates with diff, review and approval, staged rollout with canary tenants, automated eval gate (§24.5), and instant rollback.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ADM-004

**Deliverable:** Track costs and unusual spending

**P1 · MUST · Pending**

**Check:** Client, plan and provider margin views produce the required abnormal-spend alerts.

**Owner:** To assign.

**Source:** Technical specification §19.3 Admin back-office (ADM).

**Business links:** [BR-042](#br-042).

**Official acceptance links:** [AT-56](#at-56).

**Full source text:**

> ADM-004 [P1] MUST provide cost and margin dashboards per tenant, per plan and per vendor, with alerting on abnormal spend.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ADM-005

**Deliverable:** Manage phone numbers and registrations

**P1 · MUST · Pending**

**Check:** Number lifecycle, porting status and messaging registrations are visible and auditable.

**Owner:** To assign.

**Source:** Technical specification §19.3 Admin back-office (ADM).

**Business links:** [BR-070](#br-070).

**Official acceptance links:** [AT-58](#at-58).

**Full source text:**

> ADM-005 [P1] MUST provide number inventory management (search, buy, assign, release, port status), and compliance registration status (A2P 10DLC, toll-free verification).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ADM-006

**Deliverable:** Preview and audit bulk administration

**P2 · SHOULD · Pending**

**Check:** P2 bulk operations show the proposed changes before execution and retain audit records.

**Owner:** To assign.

**Source:** Technical specification §19.3 Admin back-office (ADM).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ADM-006 [P2] SHOULD provide bulk tenant operations with dry-run and audit.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ADM-007

**Deliverable:** Respond to a service incident

**P1 · MUST · Pending**

**Check:** Staff can inform clients, switch to safe fallback and control provider failover through authorised actions.

**Owner:** To assign.

**Source:** Technical specification §19.3 Admin back-office (ADM).

**Business links:** [BR-068](#br-068), [BR-070](#br-070).

**Official acceptance links:** [AT-49](#at-49), [AT-58](#at-58).

**Full source text:**

> ADM-007 [P1] MUST provide an incident toolkit: broadcast banner to tenants, per-tenant fallback switch (route all calls to owner or to message-capture), and vendor failover controls.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ADM-008

**Deliverable:** Manage brands, prospects and migration work

**P1 · MUST · Pending**

**Check:** Only the permitted growth/vertical roles can manage targets, claims and the associated boards.

**Owner:** To assign.

**Source:** Technical specification §19.3 Admin back-office (ADM).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [ACC-006](#acc-006).

**Full source text:**

> ADM-008 [P1] MUST provide administration for brands, vertical packs, targets and prospects: create and configure brands and packs; manage the target registry and the claims register; view the pipeline and migration boards; roles limited to acquisition and vertical staff (ACC-006).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ADM-009

**Deliverable:** Show industry launch-readiness evidence

**P1 · MUST · Pending**

**Check:** Checklist status, approvers and supporting evidence determine whether a pack can launch.

**Owner:** To assign.

**Source:** Technical specification §19.3 Admin back-office (ADM).

**Business links:** [BR-047](#br-047).

**Official acceptance links:** [AT-08](#at-08).

**Related source references:** [VRT-005](#vrt-005).

**Full source text:**

> ADM-009 [P1] MUST provide the readiness-gate console (VRT-005) showing checklist status, approvers and evidence.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ANL-001

**Deliverable:** Show owners the value they receive

**P1 · MUST · Pending**

**Check:** The dashboard and weekly digest report the required outcomes, with revenue estimates and missing baselines clearly identified.

**Owner:** To assign.

**Source:** Technical specification §19.2 Analytics and reporting (ANL).

**Business links:** [BR-039](#br-039).

**Official acceptance links:** [AT-57](#at-57).

**Full source text:**

> ANL-001 [P1] MUST provide an owner dashboard: calls answered, after-hours calls captured, requests created, booked, estimated recovered revenue, average response time, top questions, knowledge gaps, missed-call rate before/after EverOnn (when baseline data exists), and a weekly emailed digest.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ANL-002

**Deliverable:** Build reliable reporting from platform events

**P1 · MUST · Pending**

**Check:** Reporting consumes versioned events without disrupting live services; later datastore exceptions require approval.

**Owner:** To assign.

**Source:** Technical specification §19.2 Analytics and reporting (ANL).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ANL-002 [P1] MUST provide a platform analytics pipeline: events (Appendix C) flow to an analytics store for internal reporting. P1 MAY use MariaDB read replicas and materialized summary tables; P2 SHOULD introduce a columnar store (for example ClickHouse or MariaDB ColumnStore, subject to the RHEL/MariaDB exception process) fed by the outbox stream.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ANL-003

**Deliverable:** Show service quality and provider health

**P1 · MUST · Pending**

**Check:** Dashboards expose required latency, safety, escalation, evaluation, cost and provider-error measures.

**Owner:** To assign.

**Source:** Technical specification §19.2 Analytics and reporting (ANL).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ANL-003 [P1] MUST provide quality dashboards: latency per stage, guardrail hits, escalation rates and reasons, QA scores, eval pass rates by agent version, cost per call and per tenant, and vendor error rates.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ANL-004

**Deliverable:** Understand onboarding conversion

**P2 · SHOULD · Pending**

**Check:** P2 funnel reports distinguish claim, verification, go-live, first call, first booking and payment.

**Owner:** To assign.

**Source:** Technical specification §19.2 Analytics and reporting (ANL).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ANL-004 [P2] SHOULD provide cohort and funnel analysis for onboarding (claim → verified → live → first call → first booked job → paid).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BIL-001

**Deliverable:** Define plans and allowances as data

**P1 · MUST · Pending**

**Check:** Feature access follows dated entitlements and overrides rather than hardcoded plan-name checks.

**Owner:** To assign.

**Source:** Technical specification §19.1 Billing, plans, entitlements and metering (BIL).

**Business links:** [BR-040](#br-040), [BR-043](#br-043).

**Official acceptance links:** [AT-25](#at-25), [AT-55](#at-55), [AT-56](#at-56).

**Full source text:**

> BIL-001 [P1] MUST implement plans and entitlements as data: plan → entitlements (features, limits, included usage, overage rates), with per-tenant overrides, effective dates and full history. Application code checks entitlements, never plan names.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BIL-002

**Deliverable:** Let customers pay through hosted checkout

**P1 · MUST · Pending**

**Check:** The specified subscription, tax, invoice and overdue-payment flows work without EverOnn handling card details.

**Owner:** To assign.

**Source:** Technical specification §19.1 Billing, plans, entitlements and metering (BIL).

**Business links:** [BR-040](#br-040).

**Official acceptance links:** [AT-56](#at-56).

**Full source text:**

> BIL-002 [P1] MUST use Stripe (Billing, Checkout/Customer Portal hosted pages so card data never touches EverOnn systems, SAQ-A scope) behind PaymentProvider. Support monthly and annual, coupons, trials, proration, tax (Stripe Tax), invoices and receipts, and dunning with a grace period before suspension.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BIL-003

**Deliverable:** Keep payment-provider state in sync

**P1 · MUST · Pending**

**Check:** Signed payment events are duplicate-safe and daily reconciliation detects and repairs differences.

**Owner:** To assign.

**Source:** Technical specification §19.1 Billing, plans, entitlements and metering (BIL).

**Business links:** [BR-040](#br-040).

**Official acceptance links:** [AT-56](#at-56).

**Full source text:**

> BIL-003 [P1] MUST implement webhook handling with signature verification, idempotency, replay protection, and reconciliation jobs that compare Stripe state to local state daily.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BIL-004

**Deliverable:** Show accurate usage and allowance alerts

**P1 · MUST · Pending**

**Check:** All required meters are recorded once in effect, shown promptly and produce 80%/100% allowance alerts.

**Owner:** To assign.

**Source:** Technical specification §19.1 Billing, plans, entitlements and metering (BIL).

**Business links:** [BR-041](#br-041).

**Official acceptance links:** [AT-48](#at-48).

**Full source text:**

> BIL-004 [P1] MUST implement usage metering: every billable or cost-bearing action emits an immutable usage_event (tenant_id, meter, quantity, unit, occurred_at, source_id, provider_cost_estimate). Meters: voice minutes (inbound, transfer legs), SMS segments, chat conversations or messages (per policy), HITL minutes, site generation, storage. Aggregation is exactly-once in effect (idempotent keys). Usage is pushed to Stripe metered billing where used, and shown to owners in near-real time with alerts at 80% and 100% of allowance.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BIL-005

**Deliverable:** Apply plan limits without blocking emergencies

**P1 · MUST · Pending**

**Check:** The selected overage/cap policy applies while emergency handling continues and is recorded.

**Owner:** To assign.

**Source:** Technical specification §19.1 Billing, plans, entitlements and metering (BIL).

**Business links:** [BR-041](#br-041).

**Official acceptance links:** [AT-48](#at-48).

**Full source text:**

> BIL-005 [P1] MUST enforce limits without dropping emergencies: at the limit, follow the plan's rule (overage billing, soft cap with notice, or hard cap with safe fallback). P1 severity and emergency flows are never blocked by a cap; they are recorded and billed after.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BIL-006

**Deliverable:** Add approved outcome-based charges

**P2 · SHOULD · Pending**

**Check:** P2 billable outcomes, disputes and owner-visible evidence follow the product-approved definition.

**Owner:** To assign.

**Source:** Technical specification §19.1 Billing, plans, entitlements and metering (BIL).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [D-1](everonn-architecture.md#d-1).

**Full source text:**

> BIL-006 [P2] SHOULD support outcome-based add-ons (for example fee per booked job) with a clear, auditable definition of a billable outcome, dispute handling, and owner-visible logs. Requires product sign-off (Decision D-1).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BIL-007

**Deliverable:** Measure the cost of serving each business

**P1 · MUST · Pending**

**Check:** Telephony, speech, AI, messaging and storage costs support visible margins and cost controls.

**Owner:** To assign.

**Source:** Technical specification §19.1 Billing, plans, entitlements and metering (BIL).

**Business links:** [BR-042](#br-042).

**Official acceptance links:** [AT-56](#at-56).

**Related source references:** [ADM-004](#adm-004), [VOX-026](#vox-026).

**Full source text:**

> BIL-007 [P1] MUST compute and store per-tenant cost of service (telephony, STT, LLM tokens, TTS characters, SMS, storage) to power margin dashboards (ADM-004) and cost circuit breakers (VOX-026).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BIL-008

**Deliverable:** Support reseller billing in the later phase

**P3 · MAY · Pending**

**Check:** P3 wholesale pricing, consolidated invoices and branded receipts follow the agreed reseller model.

**Owner:** To assign.

**Source:** Technical specification §19.1 Billing, plans, entitlements and metering (BIL).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> BIL-008 [P3] MAY support reseller/agency billing (wholesale pricing, consolidated invoices, white-label receipts).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BIL-009

**Deliverable:** Keep brand prices and offers consistent

**P1 · MUST · Pending**

**Check:** Brand price books and dated offers drive both public plan information and enforced entitlements.

**Owner:** To assign.

**Source:** Technical specification §19.1 Billing, plans, entitlements and metering (BIL).

**Business links:** [BR-044](#br-044).

**Official acceptance links:** [AT-06](#at-06).

**Related source references:** [API-001](#api-001).

**Full source text:**

> BIL-009 [P1] MUST hold brand-specific plan catalogs and price books as data, including time-bounded switching offers as entitlements, and expose them through the public plan data (API-001) so that every brand's website shows what the platform enforces (BRL-025).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### BIL-010

**Deliverable:** Add ordering and human-handling fee components

**P2 · SHOULD · Pending**

**Check:** P2 order/minute components are metered and billed alongside subscriptions according to the approved pricing.

**Owner:** To assign.

**Source:** Technical specification §19.1 Billing, plans, entitlements and metering (BIL).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> BIL-010 [P2] SHOULD support per-order and per-handled-minute fee components alongside subscriptions, for restaurant ordering and operator handling.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VRT-001

**Deliverable:** Define each brand's identity

**P1 · MUST · Pending**

**Check:** A brand record contains the required legal identity, domains, theme, sender settings and defaults.

**Owner:** To assign.

**Source:** Technical specification §19.6 Brands and vertical packs (VRT).

**Business links:** [BR-044](#br-044).

**Official acceptance links:** [AT-06](#at-06).

**Full source text:**

> VRT-001 [P1] MUST model a Brand as a first-class entity with: name, contracting legal entity, primary and secondary domains, theme (design tokens, logo, typography), legal documents (terms, privacy, messaging consent, client agreement), sender identities (email domain, text-message sender name, voice caller name), support contacts and physical address, the vertical or verticals it serves, its plan catalog and price book, its default vertical pack, and a status. Every tenant belongs to exactly one brand.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VRT-002

**Deliverable:** Apply the brand throughout the experience

**P1 · MUST · Pending**

**Check:** Pages, login, messages, calls and legal information consistently use the right brand.

**Owner:** To assign.

**Source:** Technical specification §19.6 Brands and vertical packs (VRT).

**Business links:** [BR-044](#br-044), [BR-045](#br-045).

**Official acceptance links:** [AT-06](#at-06).

**Full source text:**

> VRT-002 [P1] MUST apply the brand to everything a client or a client's customer sees: the client application and its login address, emails, texts, invoices, help content, generated websites' preview host, demonstration pages and notices. A user of one brand MUST NOT be able to discover or see another brand's clients, pricing or content.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VRT-003

**Deliverable:** Package an industry as versioned configuration

**P1 · MUST · Pending**

**Check:** The full source pack contents are versioned together and can be reviewed before launch.

**Owner:** To assign.

**Source:** Technical specification §19.6 Brands and vertical packs (VRT).

**Business links:** [BR-046](#br-046), [BR-048](#br-048).

**Official acceptance links:** [AT-07](#at-07), [AT-09](#at-09).

**Related source references:** [COM-014](#com-014), [EVL-005](#evl-005), [INT-002](#int-002), [MIG-010](#mig-010), [VRT-006](#vrt-006).

**Full source text:**

> VRT-003 [P1] MUST define a Vertical pack as a versioned data bundle containing: website templates and section variants; content library (service pages, FAQs, industry explanations); vocabulary and labels; intake playbooks and slot definitions; urgency, escalation and authority defaults; starter knowledge; greeting templates; the vertical's structured request schema (VRT-006); the compliance profile it requires (COM-014); the connector set it uses (INT-002); plans, entitlements and default terms; dashboard and report definitions; the onboarding checklist; and the migration playbooks for its conquest targets (MIG-010). Pack changes are versioned, staged, evaluated (EVL-005) and reversible.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VRT-004

**Deliverable:** Run two brands and two packs in the pilot

**P1 · MUST · Pending**

**Check:** Both operate on the shared platform; an additional configuration can be added without platform code changes.

**Owner:** To assign.

**Source:** Technical specification §19.6 Brands and vertical packs (VRT).

**Business links:** [BR-046](#br-046).

**Official acceptance links:** [AT-07](#at-07).

**Full source text:**

> VRT-004 [P1] MUST support at least two brands and two packs live on one platform at the pilot, and MUST allow a new brand or pack to be added by configuration and content alone for standard cases, without changes to platform code. The elapsed time to create a new standard pack is measured and reported.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VRT-005

**Deliverable:** Approve an industry before launching it

**P1 · MUST · Pending**

**Check:** Every readiness item has an owner, evidence and approval; incomplete items block launch.

**Owner:** To assign.

**Source:** Technical specification §19.6 Brands and vertical packs (VRT).

**Business links:** [BR-047](#br-047).

**Official acceptance links:** [AT-08](#at-08).

**Full source text:**

> VRT-005 [P1] MUST enforce a vertical readiness gate: a checklist per pack whose items (counsel review of terms and disclosures; compliance profile enabled and tested; evaluation set pass thresholds; playbook review by an industry expert; connector and fallback checks; pricing and published-claims check; operator training where the desk will serve the vertical) must each be approved by a named person before the pack can be enabled for production tenants. Approvals are recorded and versioned.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VRT-006

**Deliverable:** Capture industry-specific request details

**P1 · MUST · Pending**

**Check:** Pack-defined fields produce validated requests without modifying the shared database schema.

**Owner:** To assign.

**Source:** Technical specification §19.6 Brands and vertical packs (VRT).

**Business links:** [BR-046](#br-046).

**Official acceptance links:** [AT-07](#at-07).

**Full source text:**

> VRT-006 [P1] MUST support vertical-specific structured data without schema changes: each pack declares the fields of its request object (for example vehicle details for auto repair, entity type and tax years for accounting, an order for a restaurant) in a JSON Schema; the platform validates, stores, displays, searches and reports on them.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VRT-007

**Deliverable:** Provide brand-specific operator defaults

**P2 · SHOULD · Pending**

**Check:** Greetings and desk instructions use brand defaults while authorised reports can compare brands.

**Owner:** To assign.

**Source:** Technical specification §19.6 Brands and vertical packs (VRT).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VRT-007 [P2] SHOULD provide brand-level defaults for operators (greeting and desk-profile templates, notices) and cross-brand analytics for EverOnn with a brand and vertical filter.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VRT-008

**Deliverable:** Share one engine across brands

**P1 · MUST · Pending**

**Check:** The shared inbox, desk, billing and AI engine preserve brand/client isolation and operator grants.

**Owner:** To assign.

**Source:** Technical specification §19.6 Brands and vertical packs (VRT).

**Business links:** [BR-044](#br-044).

**Official acceptance links:** [AT-06](#at-06).

**Related source references:** [DSK-002](#dsk-002).

**Full source text:**

> VRT-008 [P1] MUST share one inbox, one operator desk, one billing engine and one AI runtime across brands. Operators may be granted clients of several brands (DSK-002); the desk shows the client's business name as the primary identity and the brand as a secondary tag.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VRT-009

**Deliverable:** Name the contracting business correctly

**P1 · MUST · Pending**

**Check:** Each brand's documents and footers identify the correct legal entity and approved naming.

**Owner:** To assign.

**Source:** Technical specification §19.6 Brands and vertical packs (VRT).

**Business links:** [BR-044](#br-044), [BR-045](#br-045).

**Official acceptance links:** [AT-06](#at-06).

**Related source references:** [ACQ-008](#acq-008).

**Full source text:**

> VRT-009 [P1] MUST name the contracting entity in every brand's legal documents, footers and client agreement, apply one consistent set of terms, privacy and refund policies across brands, and share a single suppression list across all brands (ACQ-008).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### VRT-010

**Deliverable:** Maintain and review industry packs

**P1 · MUST · Pending**

**Check:** A responsible manager, change log, review calendar and approvals keep time-sensitive content current.

**Owner:** To assign.

**Source:** Technical specification §19.6 Brands and vertical packs (VRT).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> VRT-010 [P1] MUST support pack governance: an owner (vertical manager) per pack, a change log, a review calendar for time-sensitive content (market prices, regulatory notes), and metrics per pack (time to launch, activation, retention, cost to serve, escalation rate).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-001

**Deliverable:** Keep proof of consent and opt-out

**P1 · MUST · Pending**

**Check:** Consent history retains the required purpose, wording, method and timestamps without rewriting past evidence.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-053](#br-053), [BR-064](#br-064).

**Official acceptance links:** [AT-23](#at-23), [AT-44](#at-44).

**Full source text:**

> COM-001 [P1] MUST implement a consent ledger: immutable records of every consent and opt-out (contact_id, channel, purpose, text_shown, method, timestamp, IP/agent, page, tenant_id, revoked_at). Sending logic MUST consult the ledger (fail closed).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-002

**Deliverable:** Enforce texting permissions and STOP

**P1 · MUST · Pending**

**Check:** Messages respect purpose-specific permission, opt-out, quiet-hour and suppression rules at every send.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-012](#br-012), [BR-053](#br-053).

**Official acceptance links:** [AT-20](#at-20), [AT-23](#at-23).

**Full source text:**

> COM-002 [P1] MUST implement SMS/TCPA controls: prior express consent capture for informational and transactional messages, separate consent for marketing, STOP/HELP handling, quiet hours, sender identification, frequency caps, and a full audit trail. Marketing/outbound features are off by default.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-003

**Deliverable:** Disclose AI use as required

**P1 · MUST · Pending**

**Check:** Voice/chat disclosures follow the reviewed policy and answer honestly when asked whether the assistant is AI.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-004](#br-004), [BR-064](#br-064), [BR-066](#br-066).

**Official acceptance links:** [AT-14](#at-14), [AT-15](#at-15), [AT-44](#at-44), [AT-45](#at-45).

**Full source text:**

> COM-003 [P1] MUST implement AI disclosure: voice and chat identify as AI where required or when sincerely asked, in a configurable but policy-bounded manner (state and jurisdiction rules table maintained by EverOnn).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-004

**Deliverable:** Record calls only under the applicable rules

**P1 · MUST · Pending**

**Check:** Jurisdiction and refusal tests apply the reviewed announcement/consent policy and stop recording when required.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-064](#br-064), [BR-066](#br-066).

**Official acceptance links:** [AT-44](#at-44), [AT-45](#at-45).

**Full source text:**

> COM-004 [P1] MUST implement call recording consent logic by jurisdiction (one-party vs all-party regimes, determined from the caller's and business's locations): play an announcement where needed; if consent is refused, stop recording and continue with transcript-only or per policy. The jurisdiction rules table is data, versioned, and reviewed by counsel.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-005

**Deliverable:** Track carrier-compliance work

**P1 · MUST · Pending**

**Check:** Registration, verification and number-reputation states are visible, with required evidence and remediation.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-064](#br-064).

**Official acceptance links:** [AT-44](#at-44).

**Full source text:**

> COM-005 [P1] MUST track carrier compliance (A2P 10DLC brand and campaign registration, toll-free verification, STIR/SHAKEN reputation) as a managed workflow with owner and support visibility.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-006

**Deliverable:** Publish correct client legal pages

**P1 · MUST · Pending**

**Check:** Privacy, terms and messaging pages reflect the right business, brand and configured data-processing behaviour.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-045](#br-045), [BR-066](#br-066).

**Official acceptance links:** [AT-06](#at-06), [AT-45](#at-45).

**Full source text:**

> COM-006 [P1] MUST publish accurate Privacy Policy, Terms, Messaging Terms templates rendered per tenant on their sites, with tenant-specific data controller information.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-007

**Deliverable:** Remove personal details from secondary records

**P1 · MUST · Pending**

**Check:** Logs, traces, analytics and evaluation data follow the required redaction and anonymisation rules.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> COM-007 [P1] MUST implement PII redaction in logs, traces, analytics and eval datasets (names, phones, emails, addresses, card and government IDs), with reversible tokenization only in the primary store. Training or eval use of customer conversations requires opt-in and anonymization.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-008

**Deliverable:** Keep and delete data under approved policies

**P1 · MUST · Pending**

**Check:** Each data class has the correct retention job; holds and exceptions follow the complete source requirement.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> COM-008 [P1] MUST implement data retention policies per data class (default proposals: recordings 90 days, transcripts 24 months, audit logs 7 years, billing 7 years; configurable per plan and tenant), automated deletion, legal hold support, and deletion on account closure after a grace period.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-009

**Deliverable:** Handle customers' privacy-rights requests

**P1 · MUST · Pending**

**Check:** Requests for access, correction, deletion and applicable opt-outs are verified and completed through the defined workflow.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-066](#br-066), [BR-067](#br-067).

**Official acceptance links:** [AT-45](#at-45), [AT-46](#at-46).

**Full source text:**

> COM-009 [P1] MUST support data subject rights (access, deletion, correction, opt-out of sale/sharing where applicable) for tenants' customers via tenant-initiated tooling and an EverOnn intake process, with SLAs.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-010

**Deliverable:** Prepare the later HIPAA-ready mode

**P2 · SHOULD · Pending**

**Check:** P3 mode enables only the required eligible providers and restricted data handling after the compliance gate.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> COM-010 [P2] SHOULD provide a HIPAA-ready mode (BAA-eligible vendors only, restricted logging, encryption, audit) for health-adjacent verticals in P3; scaffold the compliance_profile field on tenants at P1.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-011

**Deliverable:** Track provider agreements

**P2 · SHOULD · Pending**

**Check:** The subprocessor register records the required agreements, review dates and approval state.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> COM-011 [P2] SHOULD maintain a subprocessor register and vendor DPA/BAA tracking; expose it publicly.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-012

**Deliverable:** Require review for high-risk outbound activity

**P3 · MUST · Pending**

**Check:** Outbound automation cannot launch without the source-required compliance review and controls.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> COM-012 [P3] MUST treat outbound calls and marketing texts as high-risk: require a compliance design review, DNC scrubbing, calling-hours windows, revocation handling, and AI-voice consent rules before any outbound automation ships.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-013

**Deliverable:** Make the platform accessible

**P1 · MUST · Pending**

**Check:** Dashboard, widget and sites pass the required automated and manual WCAG 2.1 AA checks.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-074](#br-074).

**Official acceptance links:** [AT-52](#at-52).

**Full source text:**

> COM-013 [P1] MUST support accessibility compliance (WCAG 2.1 AA) for the dashboard, widget and generated sites.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-014

**Deliverable:** Apply the right compliance profile

**P1 · MUST · Pending**

**Check:** The business's profile determines permitted fields, providers, access, retention and advice limits.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-065](#br-065).

**Official acceptance links:** [AT-11](#at-11).

**Full source text:**

> COM-014 [P1] MUST implement a compliance profile framework. Each tenant has a compliance profile (default, hipaa_covered, legal, insurance, tax_accounting, food_ordering, veterinary) that the vertical pack requires and that drives enforced behavior: disclosure texts, recording rules, retention, redaction level, permitted subprocessors, capabilities allowed (for example quoting), prohibited topics, escalation triggers and human gating. Profile changes are audited and cannot be made by the client alone.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-015

**Deliverable:** Gate health-care features on required agreements

**P3 · MUST · Pending**

**Check:** HIPAA-covered use remains unavailable until the client and provider agreement chain and controls are proven.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-065](#br-065).

**Official acceptance links:** [AT-11](#at-11).

**Full source text:**

> COM-015 [P3] MUST provide a health-care privacy mode for HIPAA-covered practices: a workflow for the client to sign the business associate agreement; a subprocessor register that records, per provider and per product or tier, whether an agreement covers it; a patient-information pipeline with no model training, zero-retention or equivalent settings where required, encrypted recordings and transcripts, redacted logs, traces and evaluation data, minimum-necessary capture, short default retention with purge, access logging and a breach-notification workflow. A health-care pack MUST be blocked from going live unless every provider in the call path is covered.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-016

**Deliverable:** Enforce professional-services intake limits

**P2 · MUST · Pending**

**Check:** Law, insurance and tax/accounting flows follow their respective disclosures and prohibited-advice rules.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-065](#br-065).

**Official acceptance links:** [AT-11](#at-11).

**Full source text:**

> COM-016 [P2] MUST apply professional-services guardrails: for law, disclose the AI, state that no attorney-client relationship exists yet, gather party names for conflict checks without advising, never train on client data, and keep transcripts retrievable; for insurance, gate quotes, coverage explanations, claims-status answers and binding to licensed staff; for accounting and tax, give no tax advice or return-specific answers, never collect Social Security numbers or return details by voice or chat, provide secure-upload instructions, and default to not ingesting return data.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-017

**Deliverable:** Use safe advice limits in every industry

**P1 · MUST · Pending**

**Check:** Industry safety tests cover emergency routing and the exact advice restrictions in the source.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-065](#br-065).

**Official acceptance links:** [AT-11](#at-11).

**Full source text:**

> COM-017 [P1] MUST enforce advice limits and safe scripts in every vertical: emergency guidance and routing, no diagnosis or interpretation of results or medication advice, no titles that imply licensure, AI disclosure at the start of every call and chat, and a route to a person.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### COM-018

**Deliverable:** Maintain reviewed state and industry rule tables

**P2 · MUST · Pending**

**Check:** Counsel-reviewed, dated rule data controls disclosures, recording and industry-specific behaviour.

**Owner:** To assign.

**Source:** Technical specification §19.5 Compliance and legal-by-design (COM).

**Business links:** [BR-065](#br-065).

**Official acceptance links:** [AT-11](#at-11).

**Related source references:** [ACQ-008](#acq-008).

**Full source text:**

> COM-018 [P2] MUST hold state and vertical rule tables as data, reviewed by counsel: AI-disclosure and recording rules by state and vertical, and outreach rules (calling hours, frequency limits, registration) used by the acquisition console (ACQ-008).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-001

**Deliverable:** Record competitor targets and playbooks

**P1 · MUST · Pending**

**Check:** A new target can store the complete required evidence, pricing, terms and migration information without development.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Business links:** [BR-050](#br-050).

**Official acceptance links:** [AT-21](#at-21).

**Related source references:** [MIG-010](#mig-010).

**Full source text:**

> ACQ-001 [P1] MUST provide a conquest target registry. A target records: the incumbent provider and the verticals it serves; its detection signatures (technology-list references, "powered by" credit patterns, hosting or domain fingerprints); the source lists and their terms and refresh dates; published pricing snapshots with as-of dates and source links; the feature checklist; contract and lock-in notes (term, renewal, termination fees, ownership of domain and content); known AI features; the migration playbook (MIG-010); offer templates; and status. New targets are created by configuration. Time-sensitive facts carry an as-of date and a review-by date and are flagged when stale (BRL-038).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-002

**Deliverable:** Import prospects from permitted sources

**P1 · MUST · Pending**

**Check:** Imports retain provenance, obey source terms and merge duplicates rather than treating unverified detection as fact.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Business links:** [BR-051](#br-051).

**Official acceptance links:** [AT-22](#at-22).

**Full source text:**

> ACQ-002 [P1] MUST support prospect ingestion from permitted sources (licensed technology lists, public portfolios and directories, EverOnn's own research, inbound forms). Every record keeps provenance: source, list, date, the terms basis for use, and the evidence of the incumbent relationship. Ingestion deduplicates across sources (domain, phone, place identifier), removes redirects, inactive sites, out-of-scope locations and non-target businesses, and tags each field with the uses its source permits (for example, contact numbers from a technology list are flagged "not for marketing"). Records past their retention period are purged.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-003

**Deliverable:** Keep a complete prospect record

**P1 · MUST · Pending**

**Check:** The required business, source, confidence, ownership and next-action fields are recorded with minimal personal data.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Business links:** [BR-051](#br-051).

**Official acceptance links:** [AT-22](#at-22).

**Full source text:**

> ACQ-003 [P1] MUST hold a prospect record with: business name; website; location; incumbent provider; evidence and its date; public business contact; decision-maker role; visible website, chat and ordering features; actual current bill (once obtained); identified gap; current portal, POS or practice-software dependencies; proposed EverOnn package; savings calculation; migration needs; next action; and status. Each field records whether it is verified, estimated or unknown; unknown is never displayed or reported as "no" (BRL-027).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-004

**Deliverable:** Explain how prospects are prioritised

**P1 · SHOULD · Pending**

**Check:** Adjustable qualification rules expose their signals and score rather than inventing verified facts.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Business links:** [BR-052](#br-052).

**Official acceptance links:** [AT-22](#at-22).

**Full source text:**

> ACQ-004 [P1] SHOULD provide qualification and scoring using transparent, adjustable rules (signals of an enquiry-handling gap such as no chat or online booking, size of current spend, migration complexity, regulatory load, location and size). Scores explain their factors, never assert facts, and can be overridden by a person.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-005

**Deliverable:** Track the prospect-to-customer journey

**P1 · MUST · Pending**

**Check:** Each source-defined stage has an owner, next action, evidence and the required conversion links.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Business links:** [BR-052](#br-052).

**Official acceptance links:** [AT-22](#at-22).

**Full source text:**

> ACQ-005 [P1] MUST run a pipeline with defined stages (identified, verified, previewed, contacted, engaged, demonstrated, proposed, agreed, migrating, live, retained or lost), an owner and a next action for each prospect, an audit trail, and views by target, vertical, brand and channel.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-006

**Deliverable:** Prepare a private, personalised demonstration

**P1 · MUST · Pending**

**Check:** The prospect's sourced details drive a private preview and requested demo; unsolicited automated contact is prevented.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Business links:** [BR-054](#br-054).

**Official acceptance links:** [AT-24](#at-24).

**Related source references:** [WEB-003](#web-003).

**Full source text:**

> ACQ-006 [P1] MUST generate a personalized preview and demonstration from a prospect's own public business details: a private, non-indexed website preview using the preview engine (WEB-003), and a demonstration agent, on the prospect's business name, services, hours and handoff rules, that can be tried by chat or a call the prospect requests. Nothing is published without verified owner approval (BRL-006), and no call or text is placed to a prospect without a consent record (BRL-028). Previews expire automatically.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-007

**Deliverable:** Show an honest switching-cost comparison

**P1 · MUST · Pending**

**Check:** Dated inputs include incumbent fees and contract costs; unknowns and assumptions are visible to the prospect.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Business links:** [BR-055](#br-055), [BR-057](#br-057).

**Official acceptance links:** [AT-25](#at-25), [AT-26](#at-26).

**Full source text:**

> ACQ-007 [P1] MUST provide an honest savings comparison calculator. Inputs are the prospect's current monthly cost items, contract term and early-termination fee, the services the prospect must keep, payment-processing costs, and, for providers that charge a percentage of orders, the order volume. Each input is tagged prospect-confirmed, public or estimate. Outputs are total current cost, total EverOnn cost (plan, expected usage and overages), break-even, and clear disclosures. A savings claim may be shared only when its key inputs are confirmed or are clearly labeled as estimates (BRL-030).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-008

**Deliverable:** Use reviewed outreach channels

**P1 · MUST · Pending**

**Check:** Email/manual calling follows the full source rules; AI-voice and automated text outreach remain blocked in P1/P2.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Business links:** [BR-053](#br-053).

**Official acceptance links:** [AT-23](#at-23).

**Related source references:** [COM-001](#com-001), [COM-018](#com-018).

**Full source text:**

> ACQ-008 [P1] MUST run compliant outreach. Channels are email (brand sender identity, physical address, working one-step opt-out honored within 10 business days, accurate headers and subject lines), manually dialed calls (number-type screening, recipient local time, state calling rules, do-not-call scrub, frequency caps, call log) and postal mail. Automated, prerecorded and AI-voice calls and automated texts are disabled by default and can be enabled for a contact only when a prior express consent record exists (COM-001). A global, permanent suppression list (stored as hashes) applies across all brands and is checked before every send. Templates are approved and versioned; every touch is logged; rule tables (state hours, frequency limits) are data (COM-018).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-009

**Deliverable:** Record prospect contact preferences

**P1 · MUST · Pending**

**Check:** Each form captures the correct purpose, consent evidence and preferences in the shared ledger.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Business links:** [BR-053](#br-053).

**Official acceptance links:** [AT-23](#at-23).

**Full source text:**

> ACQ-009 [P1] MUST capture consent and preferences on every prospect-facing form (preview request, demonstration request) using the consent ledger and disclosure texts of the relevant brand.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-010

**Deliverable:** Keep evidence for marketing claims

**P1 · MUST · Pending**

**Check:** Every comparison, saving and testimonial has a dated source and approval before use.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Business links:** [BR-043](#br-043), [BR-055](#br-055).

**Official acceptance links:** [AT-25](#at-25), [AT-55](#at-55).

**Full source text:**

> ACQ-010 [P1] MUST keep a claims register: every comparative statement, savings figure, statistic, customer story or testimonial used in outreach or on any brand's site is recorded with its source, date, approver and expiry. Templates and site content may reference only approved, unexpired claims. Competitor names appear only as plain text, without logos or any implication of affiliation.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-011

**Deliverable:** Protect and expire prospect information

**P1 · SHOULD · Pending**

**Check:** Minimal fields, notices, rights handling, permissions and retention follow the source policy.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Business links:** [BR-051](#br-051).

**Official acceptance links:** [AT-22](#at-22).

**Full source text:**

> ACQ-011 [P1] SHOULD protect prospect data: minimum fields, notice at collection where required, handling of access and deletion requests, a retention schedule with automatic purge of unengaged prospects, role-based access, export controls, and a flag for counsel's determination of whether the dataset is treated as a data-broker list in any state.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-012

**Deliverable:** Measure acquisition results

**P2 · SHOULD · Pending**

**Check:** Reports distinguish funnel stages, costs and results by target, industry, brand and channel.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Business links:** [BR-058](#br-058).

**Official acceptance links:** [AT-27](#at-27).

**Full source text:**

> ACQ-012 [P2] SHOULD provide acquisition analytics: funnel by target, vertical, brand and channel; cost per acquired client; time from first contact to live; savings delivered; retention after switching; and the accuracy of each source list measured by sampling.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ACQ-013

**Deliverable:** Review changing source information

**P2 · MAY · Pending**

**Check:** Permitted refresh jobs flag stale pricing/features and create the required review tasks.

**Owner:** To assign.

**Source:** Technical specification §19.7 Customer acquisition (ACQ).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ACQ-013 [P2] MAY monitor sources on a schedule (list refreshes within license, incumbent price and feature changes) and create review tasks.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### INT-001

**Deliverable:** Use a standard connection framework

**P1 · MUST · Pending**

**Check:** Each connector handles approved authentication, sync, events, errors and revocation through the source-defined contract.

**Owner:** To assign.

**Source:** Technical specification §19.10 Integration framework and vertical connectors (INT).

**Business links:** [BR-049](#br-049).

**Official acceptance links:** [AT-10](#at-10).

**Full source text:**

> INT-001 [P1] MUST provide a connector framework: a standard interface for authentication (OAuth or API key), initial and incremental sync, webhooks, field mapping, retries, rate-limit handling and health reporting; per-tenant credentials held in the secrets vault; a connector development kit; contract tests; versioning; a sandbox mode; failure isolation so that one connector cannot affect others; and audit of every action. Calendar, point-of-sale, field-service, shop-management, practice-management, accounting and agency systems all use it.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### INT-002

**Deliverable:** Show which connections are available

**P1 · SHOULD · Pending**

**Check:** The industry connector catalog distinguishes planned, beta and generally available integrations and actual access restrictions.

**Owner:** To assign.

**Source:** Technical specification §19.10 Integration framework and vertical connectors (INT).

**Business links:** [BR-048](#br-048), [BR-049](#br-049).

**Official acceptance links:** [AT-09](#at-09), [AT-10](#at-10).

**Full source text:**

> INT-002 [P1] SHOULD maintain a connector catalog by vertical, in priority tiers with status (planned, beta, generally available). Candidates, each subject to confirmed access and terms before anything is promised to a client: auto repair (Tekmetric, Shop-Ware, Mitchell1, Shopmonkey and similar); home and urgent services (ServiceTitan, Housecall Pro, Jobber, FieldEdge); accounting (TaxDome, Canopy, Karbon, QuickBooks, Xero, SmartVault); law (Clio, MyCase, Lawmatics, Filevine); insurance (Applied Epic, EZLynx, HawkSoft, AMS360, AgencyZoom); dental (Dentrix, Eaglesoft, Open Dental); chiropractic (ChiroTouch); veterinary (Cornerstone, ezyVet, Shepherd, Neo); medical and med spa (Nextech, Zenoti, Boulevard); restaurants (Square, Toast, Clover). A connector appears in client-facing material only when it is generally available.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### INT-003

**Deliverable:** Keep working when no connector is available

**P1 · MUST · Pending**

**Check:** The business can capture requests, notify staff and use the specified fallback without a third-party connector.

**Owner:** To assign.

**Source:** Technical specification §19.10 Integration framework and vertical connectors (INT).

**Business links:** [BR-049](#br-049).

**Official acceptance links:** [AT-10](#at-10).

**Full source text:**

> INT-003 [P1] MUST ensure every vertical pack works without any connector: requests are captured and structured, the team is notified, calendars and email or text are used, and nothing depends on a third-party system being connected. Connectors add automation; they are never required for the core service.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### INT-004

**Deliverable:** Track provider-access approvals

**P2 · SHOULD · Pending**

**Check:** Applications, terms, certification and commercial restrictions are recorded before claiming a connector is available.

**Owner:** To assign.

**Source:** Technical specification §19.10 Integration framework and vertical connectors (INT).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> INT-004 [P2] SHOULD track integration access as managed work: partner-program applications, terms, certification stages, commercial conditions and owners, visible to the vertical manager.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### INT-005

**Deliverable:** Apply privacy rules to connected services

**P2 · MUST · Pending**

**Check:** Only necessary fields and approved providers cross the connection, including the applicable health-care restrictions.

**Owner:** To assign.

**Source:** Technical specification §19.10 Integration framework and vertical connectors (INT).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [COM-015](#com-015).

**Full source text:**

> INT-005 [P2] MUST apply data minimization and the vertical's compliance profile to connectors, and for health-care connectors permit only subprocessors covered by business associate agreements (COM-015).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### MIG-001

**Deliverable:** Plan the customer's move from an incumbent

**P1 · MUST · Pending**

**Check:** The project records its full asset inventory, authorisation, responsible people and cut-over checklist.

**Owner:** To assign.

**Source:** Technical specification §19.8 Migration (MIG).

**Business links:** [BR-056](#br-056).

**Official acceptance links:** [AT-26](#at-26).

**Full source text:**

> MIG-001 [P1] MUST create a migration project for each switching client, recording the incumbent and an inventory of assets: domain and DNS, email hosting, site content and images, forms, client portal or documents, customer lists, phone numbers and call-tracking numbers, Google Business Profile and ordering or reservation links, and integrations; the owner's authorization for each; status per asset; timeline; risks; and the rollback plan.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### MIG-002

**Deliverable:** Import the customer's permitted website content

**P1 · MUST · Pending**

**Check:** Approved content and assets retain their provenance and rights; unsafe or unsupported claims remain draft.

**Owner:** To assign.

**Source:** Technical specification §19.8 Migration (MIG).

**Business links:** [BR-056](#br-056).

**Official acceptance links:** [AT-26](#at-26).

**Full source text:**

> MIG-002 [P1] MUST support content import from the client's own existing public site (respecting robots directives and the incumbent's terms): pages, text, images (with a rights check), services, hours, FAQs, forms and structured data are mapped to the Site Spec, with a URL map for redirects, and reviewed by the owner. The incumbent's proprietary templates, code and licensed media are never copied.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### MIG-003

**Deliverable:** Guide domain and account ownership changes

**P1 · MUST · Pending**

**Check:** Registrar/DNS control and the required transfer, email and renewal checks are verified before changes.

**Owner:** To assign.

**Source:** Technical specification §19.8 Migration (MIG).

**Business links:** [BR-056](#br-056), [BR-057](#br-057).

**Official acceptance links:** [AT-25](#at-25), [AT-26](#at-26).

**Full source text:**

> MIG-003 [P1] MUST provide a domain workflow: verify who is the registrant and who controls the registrar account; guide the owner through unlocking the domain and obtaining the authorization code, or through repointing DNS where transfer is not needed; copy mail and verification records before any change; confirm that email continues; issue certificates on the new host; cut over only after the checks pass; roll back within a stated time if a check fails.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### MIG-004

**Deliverable:** Run in parallel and switch with rollback

**P1 · MUST · Pending**

**Check:** Staging/shadow checks, owner sign-off and monitoring support cut-over without losing service; rollback is proven.

**Owner:** To assign.

**Source:** Technical specification §19.8 Migration (MIG).

**Business links:** [BR-056](#br-056).

**Official acceptance links:** [AT-26](#at-26).

**Full source text:**

> MIG-004 [P1] MUST support a parallel run and cut-over: the new site and front desk run on a staging address and, where safe, in shadow (calls still reach the old routing) before a scheduled cut-over window; post-cut-over checks cover forms, chat, call routing, tracking, sitemap and email; a hypercare period follows.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### MIG-005

**Deliverable:** Keep the customer's phone service working

**P1 · MUST · Pending**

**Check:** Forwarding is verified before switching; later porting and rollback follow the source phases.

**Owner:** To assign.

**Source:** Technical specification §19.8 Migration (MIG).

**Business links:** [BR-056](#br-056).

**Official acceptance links:** [AT-26](#at-26).

**Full source text:**

> MIG-005 [P1] MUST preserve phone continuity: set up and verify forwarding so that no call is missed during the change; plan what happens to incumbent-owned call-tracking numbers (replace, forward or, from P2, port); confirm numbers and routing before the incumbent service is ended.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### MIG-006

**Deliverable:** Record contract terms and switching fees

**P1 · MUST · Pending**

**Check:** The customer's confirmed term, renewal, notice and fees inform the move without encouraging contract breach.

**Owner:** To assign.

**Source:** Technical specification §19.8 Migration (MIG).

**Business links:** [BR-057](#br-057).

**Official acceptance links:** [AT-25](#at-25), [AT-26](#at-26).

**Full source text:**

> MIG-006 [P1] MUST record the incumbent contract: term, renewal date, notice requirement, early-termination fee and the customer's confirmation. The platform schedules cut-over around notice dates, never cancels or instructs cancellation on the client's behalf without written authorization, and supplies a cancellation-notice template for the client to send.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### MIG-007

**Deliverable:** Move data only with customer authorisation

**P1 · MUST · Pending**

**Check:** Only approved exports and permissions allow sensitive client data to move, under the applicable controls.

**Owner:** To assign.

**Source:** Technical specification §19.8 Migration (MIG).

**Business links:** [BR-056](#br-056).

**Official acceptance links:** [AT-26](#at-26).

**Full source text:**

> MIG-007 [P1] MUST migrate client data only through client-authorized exports (for example accountants' portal documents, patient forms, order history, customer lists), under the vertical's compliance profile, with counts and checksums verified and the source retained until the client signs off.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### MIG-008

**Deliverable:** Preserve useful search and listing links

**P1 · SHOULD · Pending**

**Check:** Redirects, metadata, structured data and authorised listing updates are checked after cut-over.

**Owner:** To assign.

**Source:** Technical specification §19.8 Migration (MIG).

**Business links:** [BR-056](#br-056).

**Official acceptance links:** [AT-26](#at-26).

**Full source text:**

> MIG-008 [P1] SHOULD preserve search and listing value: redirect map, titles and metadata, structured data, and tasks to update Google Business Profile and directory links (including ordering and reservation links).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### MIG-009

**Deliverable:** Measure migration quality

**P2 · SHOULD · Pending**

**Check:** Time, defects, rollbacks and early support contacts are reported by target and improve the playbook.

**Owner:** To assign.

**Source:** Technical specification §19.8 Migration (MIG).

**Business links:** [BR-058](#br-058).

**Official acceptance links:** [AT-27](#at-27).

**Full source text:**

> MIG-009 [P2] SHOULD report migration metrics (time to cut-over, defects, rollbacks, support contacts in the first 30 days) by target and feed them back into the playbooks.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### MIG-010

**Deliverable:** Maintain reusable migration playbooks

**P1 · MUST · Pending**

**Check:** Target-linked steps, checks, templates and known issues can be configured and reviewed without new platform code.

**Owner:** To assign.

**Source:** Technical specification §19.8 Migration (MIG).

**Business links:** [BR-050](#br-050).

**Official acceptance links:** [AT-21](#at-21).

**Related source references:** [ACQ-001](#acq-001).

**Full source text:**

> MIG-010 [P1] MUST hold migration playbooks as data (steps, checks, templates, known incumbent quirks), linked from the target registry (ACQ-001) and selected automatically when a prospect's incumbent is known.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ORD-001

**Deliverable:** Manage the restaurant's real menu

**P2 · MUST · Pending**

**Check:** All source menu fields, modifiers, availability, taxes, language/pronunciation and version/import requirements are verified.

**Owner:** To assign.

**Source:** Technical specification §19.9 Online ordering and restaurant workflow (ORD).

**Business links:** [BR-059](#br-059), [BR-062](#br-062).

**Official acceptance links:** [AT-40](#at-40), [AT-43](#at-43).

**Full source text:**

> ORD-001 [P2] MUST provide menu management: categories, items, sizes, item numbers, combination meals with included sides, modifier groups (spice level, protein, rice, sauce on the side), substitutions and upcharges, bilingual names with romanization and pronunciation hints, dietary and allergen information (displayed for reference only), hours by day and period, availability and sold-out switches, preparation-time rules and tax settings. Menus are versioned and can be imported from an existing site, a document or an incumbent export.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ORD-002

**Deliverable:** Let customers order pickup online

**P2 · MUST · Pending**

**Check:** A mobile order calculates real menu totals and pickup details, follows the restaurant's fees and gets the correct acknowledgement.

**Owner:** To assign.

**Source:** Technical specification §19.9 Online ordering and restaurant workflow (ORD).

**Business links:** [BR-059](#br-059).

**Official acceptance links:** [AT-40](#at-40).

**Full source text:**

> ORD-002 [P2] MUST provide direct web ordering for pickup: mobile-first, pickup time estimates, totals with tax, a tip and fee policy the restaurant sets, guest checkout, payment at pickup or by card through a hosted payment page, confirmation and receipt, order status, and marketing consent kept separate from order confirmations.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ORD-003

**Deliverable:** Take phone orders with full read-back

**P2 · MUST · Pending**

**Check:** Items and modifiers are confirmed; uncertain/allergy questions go to staff and no card data is captured by voice.

**Owner:** To assign.

**Source:** Technical specification §19.9 Online ordering and restaurant workflow (ORD).

**Business links:** [BR-060](#br-060), [BR-062](#br-062).

**Official acceptance links:** [AT-41](#at-41), [AT-43](#at-43).

**Full source text:**

> ORD-003 [P2] MUST provide AI phone ordering from the live menu: capture items and modifiers, accept item numbers ("number 23"), read back the whole order (items, modifiers, total, pickup time) and obtain confirmation before submitting; confirm the callback number; offer payment at pickup or a payment link by text; never take card numbers by voice; transfer allergy and dietary questions and complaints to staff and never answer them (BRL-037); ask or confirm when unsure and hand off to a person when it cannot resolve the request. English is required at P2; Mandarin and Cantonese follow at P3 after testing on real menus and audio.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ORD-004

**Deliverable:** Deliver orders and obtain kitchen acceptance

**P2 · MUST · Pending**

**Check:** The staff screen, printer/receipt path, retries and escalation prevent a failed or unaccepted ticket being presented as a confirmed order.

**Owner:** To assign.

**Source:** Technical specification §19.9 Online ordering and restaurant workflow (ORD).

**Business links:** [BR-061](#br-061), [BR-062](#br-062).

**Official acceptance links:** [AT-40](#at-40), [AT-42](#at-42), [AT-43](#at-43).

**Full source text:**

> ORD-004 [P2] MUST deliver orders to the restaurant reliably: a staff-accept dashboard on a tablet or screen with alerts, accept or decline with a preparation time, and reprint; cloud printing to receipt printers with bilingual kitchen tickets; and text or email fallback. Orders carry idempotent identifiers. An order not accepted within a set time triggers an escalation (a call or text to the restaurant and owner). No order may be lost or duplicated, including across network loss and reconnection.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ORD-005

**Deliverable:** Connect approved point-of-sale systems

**P2 · SHOULD · Pending**

**Check:** Restaurant-authorised connectors follow provider access terms and have a working manual fallback.

**Owner:** To assign.

**Source:** Technical specification §19.9 Online ordering and restaurant workflow (ORD).

**Business links:** [BR-061](#br-061).

**Official acceptance links:** [AT-40](#at-40), [AT-42](#at-42).

**Related source references:** [ORD-004](#ord-004).

**Full source text:**

> ORD-005 [P2] SHOULD provide authorized point-of-sale connectors, granted by the restaurant: Square through OAuth and its ordering and catalog interfaces first; Toast, Clover, MenuSifu, Chowbus and others only after partner access, terms and certification are confirmed. Every connector has contract tests, and any failure falls back to ORD-004.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ORD-006

**Deliverable:** Keep payments on hosted pages

**P2 · MUST · Pending**

**Check:** Payment links/pages and pay-at-pickup avoid card data in EverOnn systems or recordings.

**Owner:** To assign.

**Source:** Technical specification §19.9 Online ordering and restaurant workflow (ORD).

**Business links:** [BR-059](#br-059).

**Official acceptance links:** [AT-40](#at-40).

**Full source text:**

> ORD-006 [P2] MUST handle payments through a payment processor's hosted pages or links so that card data never touches EverOnn systems or recordings (SAQ A scope); funds settle to the restaurant's own merchant account; refunds, reconciliation and tax handling are supported.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ORD-007

**Deliverable:** Review order accuracy before wider launch

**P2 · MUST · Pending**

**Check:** Item/modifier accuracy and missed-order handling meet the pilot thresholds agreed before testing.

**Owner:** To assign.

**Source:** Technical specification §19.9 Online ordering and restaurant workflow (ORD).

**Business links:** [BR-060](#br-060).

**Official acceptance links:** [AT-41](#at-41).

**Full source text:**

> ORD-007 [P2] MUST monitor order accuracy: sampled review of calls against tickets, item-level and modifier-level accuracy, failed or missed orders, handoff rate and correction rate, with thresholds that gate the three-restaurant pilot and each expansion.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ORD-008

**Deliverable:** Update the restaurant's public ordering links

**P2 · SHOULD · Pending**

**Check:** Authorised Google ordering/reservation links point to the approved service after migration.

**Owner:** To assign.

**Source:** Technical specification §19.9 Online ordering and restaurant workflow (ORD).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ORD-008 [P2] SHOULD manage the restaurant's Google ordering and reservation links during migration, with the restaurant's authorization.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ORD-009

**Deliverable:** Apply the agreed restaurant fee model

**P2 · SHOULD · Pending**

**Check:** Subscription/usage and any approved per-order fees reconcile through the shared billing system.

**Owner:** To assign.

**Source:** Technical specification §19.9 Online ordering and restaurant workflow (ORD).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [ACQ-007](#acq-007).

**Full source text:**

> ORD-009 [P2] SHOULD support fee models that are a flat subscription plus usage by default, with optional per-order pricing, and integrate with the savings comparison for providers that charge a percentage of orders (ACQ-007).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### ORD-010

**Deliverable:** Export restaurant data with consent history

**P2 · MUST · Pending**

**Check:** The restaurant can export order/customer data with the correct customer marketing-permission records.

**Owner:** To assign.

**Source:** Technical specification §19.9 Online ordering and restaurant workflow (ORD).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> ORD-010 [P2] MUST give the restaurant its order and customer data for export, with marketing consent recorded per customer.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### API-001

**Deliverable:** Publish a documented integration API

**P1 · MUST · Pending**

**Check:** The required versioned endpoints, errors, pagination, idempotency and generated documentation are consistent with the frontends.

**Owner:** To assign.

**Source:** Technical specification §19.4 Public API, webhooks and integrations (API).

**Business links:** [BR-043](#br-043), [BR-071](#br-071).

**Official acceptance links:** [AT-25](#at-25), [AT-55](#at-55), [AT-59](#at-59).

**Full source text:**

> API-001 [P1] MUST expose a versioned REST API (/v1) described by OpenAPI 3.1, used by EverOnn's own frontends (no private back doors), with resource-oriented design, cursor pagination, idempotency keys on POST, consistent error format (RFC 9457 Problem Details), rate limit headers, and SDK generation (TypeScript first).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### API-002

**Deliverable:** Secure user, integration and widget access

**P1 · MUST · Pending**

**Check:** Each access mechanism is scoped, revocable and appropriate to its user, client or permitted website origin.

**Owner:** To assign.

**Source:** Technical specification §19.4 Public API, webhooks and integrations (API).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> API-002 [P1] MUST support authentication: OAuth2/OIDC for users; API keys (scoped, hashed at rest, rotatable) and short-lived JWTs for tenant integrations; widget keys scoped to allowed origins.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### API-003

**Deliverable:** Notify connected systems reliably

**P1 · MUST · Pending**

**Check:** Signed webhooks retry, record delivery, allow replay and do not duplicate downstream effects.

**Owner:** To assign.

**Source:** Technical specification §19.4 Public API, webhooks and integrations (API).

**Business links:** [BR-071](#br-071).

**Official acceptance links:** [AT-59](#at-59).

**Full source text:**

> API-003 [P1] MUST deliver outbound webhooks for domain events (for example request.created, call.completed, appointment.booked) with HMAC signatures, retries with exponential backoff, dead-letter queues, replay from the dashboard, and per-tenant delivery logs.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### API-004

**Deliverable:** Connect workflow-automation tools

**P1 · SHOULD · Pending**

**Check:** The required Zapier/Make or documented webhook-plus-API path can create the intended client automations.

**Owner:** To assign.

**Source:** Technical specification §19.4 Public API, webhooks and integrations (API).

**Business links:** [BR-071](#br-071).

**Official acceptance links:** [AT-59](#at-59).

**Full source text:**

> API-004 [P1] SHOULD provide native Zapier and Make connectors (or generic webhook triggers plus REST actions) at P1; P2 for listed apps.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### API-005

**Deliverable:** Deliver integrations in their stated phases

**P2 · SHOULD · Pending**

**Check:** The grouped integration roadmap preserves the P1 calendar and later P2/P3 commitments stated in the source.

**Owner:** To assign.

**Source:** Technical specification §19.4 Public API, webhooks and integrations (API).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [BKG-001](#bkg-001), [BKG-005](#bkg-005).

**Full source text:**

> API-005 [P2] SHOULD provide first integrations: Google Calendar and Microsoft 365 (BKG-001), Google Business Profile, QuickBooks (invoice/customer sync, P3), and one field-service system (BKG-005).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### API-006

**Deliverable:** Keep dashboards updated live

**P1 · MUST · Pending**

**Check:** Permitted live call, inbox and escalation updates reach the correct business without manual refresh.

**Owner:** To assign.

**Source:** Technical specification §19.4 Public API, webhooks and integrations (API).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> API-006 [P1] MUST provide realtime channels for the dashboard (WebSocket or SSE) for live call status, inbox updates and escalation alerts.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### API-007

**Deliverable:** Give notice before breaking integrations

**P1 · MUST · Pending**

**Check:** The API change log and deprecation process provide at least the required six months of notice.

**Owner:** To assign.

**Source:** Technical specification §19.4 Public API, webhooks and integrations (API).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> API-007 [P1] MUST publish an API changelog and deprecation policy (minimum 6 months notice for breaking changes).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### API-008

**Deliverable:** Review partner apps before access

**P3 · MAY · Pending**

**Check:** P3 partner applications use approved OAuth scopes and the required marketplace review process.

**Owner:** To assign.

**Source:** Technical specification §19.4 Public API, webhooks and integrations (API).

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> API-008 [P3] MAY provide a partner/marketplace program (OAuth apps, scopes, review process).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-001

**Deliverable:** Review threats throughout development

**P0 · MUST · Pending**

**Check:** Module threat models, the specified security targets and reviewed remediation accompany delivery.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [SEC-015](#sec-015).

**Full source text:**

> SEC-001 [P0] MUST run a secure SDLC: threat model per module (STRIDE plus LLM-specific), OWASP ASVS Level 2 as the target, OWASP Top 10 for LLM Applications mapped to controls (SEC-015), mandatory two-person review, protected branches, signed commits for release branches.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-002

**Deliverable:** Separate network tiers and service access

**P1 · MUST · Pending**

**Check:** Only approved traffic crosses tiers; databases and secrets stay private and internal calls are authenticated.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> SEC-002 [P1] MUST segment networks by tier, allow only required flows, keep the database and Vault private, and use service-to-service authentication (mTLS with SPIFFE-style identities or signed short-lived service tokens at P1; service mesh optional at P2). Egress from application tiers goes through an allow-listed proxy.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-003

**Deliverable:** Secure logins and sessions

**P1 · MUST · Pending**

**Check:** The full source login/session controls protect staff, operator and client identities.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> SEC-003 [P1] MUST implement strong identity: passkeys/TOTP MFA, secure session handling (rotating refresh tokens, idle and absolute timeouts, device binding for operators), brute-force and credential-stuffing protection, breached-password checks, and step-up authentication for sensitive actions (billing changes, data export, number release, API key creation).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-004

**Deliverable:** Encrypt data while it travels

**P1 · MUST · Pending**

**Check:** External and internal links and media use the required secure transport settings.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> SEC-004 [P1] MUST encrypt in transit: TLS 1.2+ (1.3 preferred) everywhere including internal links, HSTS, modern cipher suites, SRTP/DTLS for media, and TLS SIP with carriers where supported.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-005

**Deliverable:** Encrypt stored data with business-specific keys

**P1 · MUST · Pending**

**Check:** Keys are wrapped, rotated and scoped as required, and one business's key cannot expose another's data.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> SEC-005 [P1] MUST encrypt at rest with envelope encryption: per-tenant data encryption keys wrapped by a key-encryption key in Vault Transit or a cloud KMS; applied to recordings, transcripts (at least sensitive fields), OAuth tokens and secrets, uploaded files; full-disk encryption on hosts; MariaDB encryption at rest for tablespaces and binlogs. Every ciphertext carries a key_id/version so keys can rotate and per-tenant (BYOK) keys can be introduced later without migration.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-006

**Deliverable:** Store and rotate secrets securely

**P1 · MUST · Pending**

**Check:** Credentials remain in the approved secrets service with the full required rotation and access controls.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> SEC-006 [P1] MUST manage secrets with Vault/OpenBao: no secrets in git, images or plaintext environment files; dynamic short-lived database credentials; automated rotation; secret scanning in CI and pre-commit.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-007

**Deliverable:** Validate all incoming information

**P1 · MUST · Pending**

**Check:** Boundary checks reject unsafe input, upload and output-handling cases required by the source.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> SEC-007 [P1] MUST validate and sanitize all input at boundaries; encode output; strict CSP on all web properties; SSRF protection for any server-side fetch of user-supplied URLs (resolve-and-check, block private and link-local ranges, redirect limits, size and time limits); file upload security (type sniffing, size limits, AV scanning, image re-encoding, isolated storage, non-executable serving).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-008

**Deliverable:** Limit abuse and fraudulent usage

**P1 · MUST · Pending**

**Check:** IP, session and business quotas, detection and kill switches stop the source-defined abuse cases.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Business links:** [BR-010](#br-010).

**Official acceptance links:** [AT-48](#at-48).

**Full source text:**

> SEC-008 [P1] MUST implement abuse and fraud controls: per-IP, per-session, per-tenant rate limits and quotas; bot management on public forms and the widget; signup velocity and disposable-email checks; premium-rate and geo restrictions; unusual-usage alerts; identity verification (out-of-band OTP) before revealing or changing sensitive data over voice or chat.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-009

**Deliverable:** Keep a tamper-evident audit trail

**P1 · MUST · Pending**

**Check:** Required events form an append-only verifiable history with the specified archive protections.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> SEC-009 [P1] MUST keep an append-only, tamper-evident audit log: hash-chained entries (each includes the hash of the previous), periodic anchoring of the chain head to object storage with object lock (WORM), covering authentication events, permission changes, configuration publishes, staff access to tenant data, HITL actions, exports, deletions and admin actions. Tenants can view their own audit trail (P2).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-010

**Deliverable:** Check software and container provenance

**P1 · MUST · Pending**

**Check:** Dependencies/images are pinned and scanned; signed builds, an SBOM and licence evidence are available.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Business links:** [BR-075](#br-075).

**Official acceptance links:** [AT-60](#at-60).

**Full source text:**

> SEC-010 [P1] MUST secure the software supply chain: minimal base images (Red Hat UBI minimal), pinned image digests, SBOM (Syft/CycloneDX) per build, vulnerability scanning (Trivy or Grype) blocking on critical/high with agreed exceptions, image signing and verification (cosign or Podman signature policy), dependency review and license policy, automated update PRs (Renovate), private registry.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-011

**Deliverable:** Fix vulnerabilities within agreed deadlines

**P1 · MUST · Pending**

**Check:** Critical/high issues meet the stated deadlines or have documented mitigation; platform patching is recorded.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Business links:** [BR-073](#br-073).

**Official acceptance links:** [AT-53](#at-53).

**Full source text:**

> SEC-011 [P1] MUST run vulnerability management: SLAs (critical within 7 days, high within 30 days, or documented mitigation), monthly RHEL patch cycle with emergency path, weekly scans of images and hosts, an external penetration test before P1 launch and again after P2, and a vulnerability disclosure policy (security.txt), with a bug bounty considered at P3.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-012

**Deliverable:** Detect suspicious activity from security logs

**P1 · MUST · Pending**

**Check:** Correlated central records and alerts expose the required login/access/security events.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> SEC-012 [P1] MUST produce structured security logs with correlation ids, centralised and retained per policy, with alerting on suspicious patterns (impossible travel, mass reads, repeated authorization failures, unusual export or impersonation events). Logs are SIEM-ready; fail2ban or equivalent at hosts.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-013

**Deliverable:** Prove backup and recovery protection

**P1 · MUST · Pending**

**Check:** Encrypted, independently protected backups restore successfully within the appropriate phase targets.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> SEC-013 [P1] MUST protect backups: encrypted, access-separated credentials, an immutable copy, tested restores, and documented DR runbooks (§23.5).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-014

**Deliverable:** Continuously test business isolation

**P1 · MUST · Pending**

**Check:** Cross-business API, job and retrieval tests pass and are included in the independent security assessment.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Business links:** [BR-063](#br-063).

**Official acceptance links:** [AT-32](#at-32), [AT-47](#at-47).

**Related source references:** [TEN-001](#ten-001).

**Full source text:**

> SEC-014 [P1] MUST test isolation continuously (TEN-001) and include tenant-isolation cases in the pen-test scope.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-015

**Deliverable:** Test attacks against the AI

**P1 · MUST · Pending**

**Check:** The required adversarial cases cannot bypass permissions, expose secrets or execute unsafe output.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [POL-003](#pol-003).

**Full source text:**

> SEC-015 [P1] MUST implement AI-specific security mapped to the OWASP LLM Top 10: prompt injection (POL-003), insecure output handling (never execute or render model output unsafely), sensitive information disclosure (redaction, retrieval filters, no secrets in prompts), excessive agency (tool scoping, approvals, per-call tool tokens bound to tenant and conversation), model denial of service (token, time and cost budgets), supply chain (provider vetting, model version pinning), overreliance (uncertainty behaviours, human escalation), and model theft/abuse (no system prompt secrets). Maintain a red-team suite and run it in CI and before every release.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-016

**Deliverable:** Prepare the staged compliance programme

**P2 · MUST · Pending**

**Check:** Evidence for policies, testing and SOC 2 readiness follows the source phases without claiming certification early.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Business links:** [BR-073](#br-073).

**Official acceptance links:** [AT-53](#at-53).

**Related source references:** [COM-010](#com-010).

**Full source text:**

> SEC-016 [P2] MUST follow a compliance roadmap: policy pack (access control, change management, incident response, vendor management, BCP/DR, data classification, secure development), evidence collection automated from CI and infrastructure, SOC 2 Type I readiness by end of P2 and Type II observation thereafter; PCI scope kept at SAQ A; HIPAA controls scaffolded (COM-010). ISO 27001 optional.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-017

**Deliverable:** Build privacy into the data lifecycle

**P1 · MUST · Pending**

**Check:** Data inventory, impact assessment, minimisation and automated retention follow the source requirements.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [COM-008](#com-008), [COM-011](#com-011), [TEN-002](#ten-002).

**Full source text:**

> SEC-017 [P1] MUST apply privacy by design: data inventory and map, DPIA template, minimization, purpose limitation, retention automation (COM-008), region tags (TEN-002), and a subprocessor register (COM-011).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### SEC-018

**Deliverable:** Prepare and rehearse incident response

**P1 · MUST · Pending**

**Check:** Named escalation roles, response procedures, notifications and exercises meet the complete incident requirement.

**Owner:** To assign.

**Source:** Technical specification §22.2 Security requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> SEC-018 [P1] MUST define incident response: severity matrix, on-call rotation, runbooks (vendor outage, data exposure, toll fraud spike, prompt-injection incident, credential compromise), breach-notification workflow with statutory deadlines, tenant communication templates, post-incident review process. Run at least one tabletop exercise before launch.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### LT-001

**Deliverable:** Prove the P1 call-load target

**P1 · MUST · Pending**

**Check:** The specified P1 concurrent-call load runs for 60 minutes with no service-target breach and stage percentile evidence.

**Owner:** To assign.

**Source:** Technical specification §23.7 Load and soak testing requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> LT-001 [P1] MUST simulate concurrent calls end to end (synthetic callers over SIP with TTS audio and noise) at 2x P1 design capacity for 60 minutes with no SLO breach, and report per-stage latency percentiles.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### LT-002

**Deliverable:** Prove P2 scale and sustained operation

**P2 · MUST · Pending**

**Check:** The agreed interpretation of the source load target and the 24-hour soak produce recorded pass/fail results.

**Owner:** To assign.

**Source:** Technical specification §23.7 Load and soak testing requirements.

**Business links:** [BR-072](#br-072).

**Official acceptance links:** [AT-51](#at-51).

**Full source text:**

> LT-002 [P2] MUST repeat at 3x projected P2 peak (about 200 concurrent calls) plus a 24-hour soak test to detect leaks.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### LT-003

**Deliverable:** Prove large-scale website generation

**P2 · MUST · Pending**

**Check:** P2 sustained and burst runs meet 1,000 sites/day and 300/hour while recording rate limits and cost.

**Owner:** To assign.

**Source:** Technical specification §23.7 Load and soak testing requirements.

**Business links:** [BR-018](#br-018).

**Official acceptance links:** [AT-05](#at-05).

**Full source text:**

> LT-003 [P2] MUST load-test the generation pipeline at 1,000 sites/day with bursts of 300/hour, including provider rate-limit behavior and cost accounting.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### LT-004

**Deliverable:** Prove inbox and API performance at scale

**P2 · MUST · Pending**

**Check:** The required large tenant/history dataset completes the source performance tests.

**Owner:** To assign.

**Source:** Technical specification §23.7 Load and soak testing requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> LT-004 [P2] MUST load-test the API and inbox with 100,000 conversations per tenant on the largest tenant profile, and 10,000 tenants of synthetic data.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### LT-005

**Deliverable:** Test service failures under load

**P1 · MUST · Pending**

**Check:** P1 staging failure tests exercise the source recovery scenarios and record the actual outcomes.

**Owner:** To assign.

**Source:** Technical specification §23.7 Load and soak testing requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> LT-005 [P1] MUST run chaos scenarios from §23.5 in staging during load tests.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### LT-006

**Deliverable:** Prove the operator desk under heavy load

**P2 · MUST · Pending**

**Check:** P2 tests cover 300 sessions, 100 offers/minute, acceptance races and forced reconnects against desk targets.

**Owner:** To assign.

**Source:** Technical specification §23.7 Load and soak testing requirements.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> LT-006 [P2] MUST load-test the Live Agent Desk with 300 concurrent operator sessions, 100 offers per minute, simultaneous acceptance races, and forced reconnects, verifying the desk performance targets in §16.7.4.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CST-001

**Deliverable:** Measure voice cost before choosing vendors

**P0 · MUST · Pending**

**Check:** The P0 spike compares at least three combinations using measured cost, quality and latency.

**Owner:** To assign.

**Source:** Technical specification §23.6 Unit economics and cost controls.

**Business links:** [BR-042](#br-042).

**Official acceptance links:** [AT-56](#at-56).

**Full source text:**

> CST-001 [P0] MUST produce a cost model and measured per-minute cost in the P0 spike for at least three vendor combinations, and recommend the default stack by cost and quality.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CST-002

**Deliverable:** Control budgets and show margins

**P1 · MUST · Pending**

**Check:** Call, client and platform budgets alert or switch safely according to the defined rules.

**Owner:** To assign.

**Source:** Technical specification §23.6 Unit economics and cost controls.

**Business links:** [BR-042](#br-042).

**Official acceptance links:** [AT-56](#at-56).

**Related source references:** [ADM-004](#adm-004), [VOX-026](#vox-026).

**Full source text:**

> CST-002 [P1] MUST implement per-call, per-tenant and global cost budgets with alerts and circuit breakers (VOX-026), and dashboards for margin by tenant (ADM-004).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CST-003

**Deliverable:** Reduce AI costs without losing quality

**P1 · MUST · Pending**

**Check:** Caching and prompt/retrieval limits reduce measured consumption while evaluations protect required quality.

**Owner:** To assign.

**Source:** Technical specification §23.6 Unit economics and cost controls.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> CST-003 [P1] MUST use prompt caching, compact prompts, retrieval limits, and short-turn design to minimize tokens; record tokens and cost per turn.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CST-004

**Deliverable:** Avoid charging for abandoned calls

**P1 · MUST · Pending**

**Check:** Silence and voicemail handling ends unwanted billable time according to the approved rules.

**Owner:** To assign.

**Source:** Technical specification §23.6 Unit economics and cost controls.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> CST-004 [P1] MUST avoid paying for silence: end calls on abandonment quickly, no long dead-air billing, and detect voicemail or automated systems early.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CST-005

**Deliverable:** Evaluate later self-hosted AI options

**P2 · SHOULD · Pending**

**Check:** A later-phase comparison uses the evaluation harness, measured volume economics and the required decision process.

**Owner:** To assign.

**Source:** Technical specification §23.6 Unit economics and cost controls.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> CST-005 [P2] SHOULD evaluate self-hosted STT and open-weight LLMs and speech-to-speech models once volume justifies, guided by the eval harness so quality does not regress.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CST-006

**Deliverable:** Define included minutes and fair use

**P1 · MUST · Pending**

**Check:** Approved allowances, overage and fair-use rules are consistent in the platform and public offer.

**Owner:** To assign.

**Source:** Technical specification §23.6 Unit economics and cost controls.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [BIL-004](#bil-004), [D-1](everonn-architecture.md#d-1).

**Full source text:**

> CST-006 [P1] MUST set plan-level minute allowances and overage (Decision D-1) and fair-use rules; enforce through BIL-004/005.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### CST-007

**Deliverable:** Measure the cost of human handling

**P2 · MUST · Pending**

**Check:** Client, industry and escalation-level operator costs support staffing and viable pricing.

**Owner:** To assign.

**Source:** Technical specification §23.6 Unit economics and cost controls.

**Business links:** [BR-042](#br-042).

**Official acceptance links:** [AT-56](#at-56).

**Related source references:** [D-1](everonn-architecture.md#d-1).

**Full source text:**

> CST-007 [P2] MUST model, meter and report the cost of operator-handled time per client, vertical and escalation reason (§16.7.5), so that operator add-on pricing (D-1) covers it and escalation rate can be managed as a margin lever.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### EVL-001

**Deliverable:** Build text and phone evaluation tools

**P0 · MUST · Pending**

**Check:** Versioned text checks run in CI and audio simulations run nightly/pre-release as required.

**Owner:** To assign.

**Source:** Technical specification §24.5 AI evaluation and safety framework.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> EVL-001 [P0] MUST deliver an eval harness in the repo that can run (a) text-level simulations (fast, in CI on every prompt/policy/model change) and (b) audio-level simulations (synthetic caller over SIP, nightly and pre-release).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### EVL-002

**Deliverable:** Create realistic industry test conversations

**P1 · MUST · Pending**

**Check:** Dataset sizes and scenario coverage meet the exact P1/P2 thresholds in the source.

**Owner:** To assign.

**Source:** Technical specification §24.5 AI evaluation and safety framework.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> EVL-002 [P1] MUST ship versioned datasets per vertical: at least 150 scripted scenarios for the first vertical (locksmith) by P1 exit and 500 or more per vertical by P2, covering: happy paths; ambiguous or rambling callers; noisy/mis-transcribed speech; Spanish and code-switching; emergencies and safety triggers; price traps ("just give me a number"); out-of-scope requests; angry callers; repeated "I want a person"; prompt-injection and social-engineering attempts; tool failures; calendar conflicts; and returning callers.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### EVL-003

**Deliverable:** Measure AI accuracy, safety, speed and cost

**P1 · MUST · Pending**

**Check:** Reports contain every required metric and retain the tested agent/provider versions.

**Owner:** To assign.

**Source:** Technical specification §24.5 AI evaluation and safety framework.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> EVL-003 [P1] MUST measure: task success and outcome correctness, slot-fill accuracy and extraction F1, correct-escalation rate and false-escalation rate, hallucination rate (claims unsupported by profile or KB), guardrail violation rate (critical/major/minor), tool-call correctness, conversation length and turns, tone/brand adherence, and latency and cost per scenario.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### EVL-004

**Deliverable:** Check automated judges against people

**P1 · MUST · Pending**

**Check:** Human calibration and agreement evidence justify judge results; critical rules use deterministic checks where possible.

**Owner:** To assign.

**Source:** Technical specification §24.5 AI evaluation and safety framework.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> EVL-004 [P1] MUST use LLM-as-judge only with calibration to human labels (inter-rater agreement reported; judge prompts versioned); safety-critical checks use deterministic rules where possible.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### EVL-005

**Deliverable:** Block AI releases that fail quality gates

**P1 · MUST · Pending**

**Check:** Every relevant change passes safety, regression, cost and latency gates, with results attached to the change record.

**Owner:** To assign.

**Source:** Technical specification §24.5 AI evaluation and safety framework.

**Business links:** [BR-076](#br-076).

**Official acceptance links:** [AT-15](#at-15), [AT-54](#at-54).

**Related source references:** [ADM-003](#adm-003).

**Full source text:**

> EVL-005 [P1] MUST enforce release gates: any change to models, prompts, policies, playbooks, retrieval settings or providers MUST pass (a) zero critical safety failures on the safety set, (b) no statistically significant regression on core metrics, and (c) cost and latency budgets. Gate results are attached to the change record (ADM-003).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### EVL-006

**Deliverable:** Try AI changes safely before wide release

**P1 · MUST · Pending**

**Check:** Shadow/canary tests and automatic rollback prevent a failing candidate being promoted widely.

**Owner:** To assign.

**Source:** Technical specification §24.5 AI evaluation and safety framework.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Full source text:**

> EVL-006 [P1] MUST support shadow and canary evaluation in production: run a candidate agent version against a sample of live traffic offline (shadow) or on a small tenant subset (canary) before full rollout, with automatic rollback triggers.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### EVL-007

**Deliverable:** Monitor AI quality after launch

**P2 · MUST · Pending**

**Check:** P2 sampling and drift alerts detect regressions, including provider-model changes.

**Owner:** To assign.

**Source:** Technical specification §24.5 AI evaluation and safety framework.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [HIL-009](#hil-009).

**Full source text:**

> EVL-007 [P2] MUST run continuous online quality monitoring: sampled QA (HIL-009), drift detection on intents, escalation rates, sentiment and guardrail hits, and alerting on regressions after provider model updates (pin model versions; test before upgrading).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### EVL-008

**Deliverable:** Add approved corrections to test data

**P2 · MUST · Pending**

**Check:** Owner/operator examples enter versioned datasets only with the required consent and anonymisation.

**Owner:** To assign.

**Source:** Technical specification §24.5 AI evaluation and safety framework.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [COM-007](#com-007), [HIL-010](#hil-010).

**Full source text:**

> EVL-008 [P2] MUST feed owner corrections and operator resolutions into datasets (HIL-010) with anonymization and consent (COM-007).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### EVL-009

**Deliverable:** Review adversarial-test results before release

**P1 · MUST · Pending**

**Check:** A human reviews the required red-team report before production promotion.

**Owner:** To assign.

**Source:** Technical specification §24.5 AI evaluation and safety framework.

**Acceptance:** Ticket-specific check above; no direct source AT mapping.

**Related source references:** [SEC-015](#sec-015).

**Full source text:**

> EVL-009 [P1] MUST maintain a red-team suite (SEC-015) executed on every release, with a report that a human reviews before production promotion.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### EVL-010

**Deliverable:** Verify every new industry's AI readiness

**P1 · MUST · Pending**

**Check:** Each pack meets launch/P2 dataset sizes and vertical safety thresholds before its readiness gate passes.

**Owner:** To assign.

**Source:** Technical specification §24.5 AI evaluation and safety framework.

**Business links:** [BR-047](#br-047).

**Official acceptance links:** [AT-08](#at-08).

**Related source references:** [VRT-005](#vrt-005).

**Full source text:**

> EVL-010 [P1] MUST maintain an evaluation dataset per vertical pack (at least 150 scenarios at pack launch and 500 by P2), including vertical-specific safety cases: allergy and dietary questions, clinical advice requests, legal advice and conflicts, coverage and claims-status questions, tax-return details and payment-card disclosure. A pack cannot pass the readiness gate below its thresholds (VRT-005).

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DEL-001

**Deliverable:** Automate the required build checks

**P0 · Supporting task · Pending**

**Check:** Required CI checks, scans, image evidence and SBOM block a build that fails its applicable gates.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §24.1 Delivery pipeline.

**Complete source deliverable text:**

> Source control: EverOnn-owned GitHub organization; protected main; trunk-based development with short-lived branches; PRs require review by a second engineer, passing checks, and linked requirement IDs.

> CI (every PR): lint, type-check, unit tests, contract tests, migration checks, SAST (CodeQL/Semgrep), secret scanning (gitleaks), dependency and license scanning, container build, image scan, SBOM generation, and preview environment deployment where feasible.

> CD: build once, promote the same signed image through dev → staging → prod; automated smoke tests and synthetic call checks after deploy; zero-downtime deploys with voice-worker draining (AR-009); one-click rollback; database migrations follow expand/contract so N and N-1 versions run together.

> Release cadence: continuous to dev/staging; production at least weekly; risky changes behind flags; change log per release; release notes for tenants when behavior changes.

> Infrastructure as code: Ansible (RHEL host hardening: SELinux, firewalld, auditd, Quadlet unit deployment) plus OpenTofu/Terraform (DNS, object storage, CDN, cloud resources); no manual server changes; drift detection.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DEL-002

**Deliverable:** Promote releases with tests and rollback

**P0 / P1 / P2 · Supporting task · Pending**

**Check:** The same signed artifact moves through environments; smoke/synthetic-call checks, compatible migrations and rollback are demonstrated.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §24.1 Delivery pipeline.

**Complete source deliverable text:**

> Source control: EverOnn-owned GitHub organization; protected main; trunk-based development with short-lived branches; PRs require review by a second engineer, passing checks, and linked requirement IDs.

> CI (every PR): lint, type-check, unit tests, contract tests, migration checks, SAST (CodeQL/Semgrep), secret scanning (gitleaks), dependency and license scanning, container build, image scan, SBOM generation, and preview environment deployment where feasible.

> CD: build once, promote the same signed image through dev → staging → prod; automated smoke tests and synthetic call checks after deploy; zero-downtime deploys with voice-worker draining (AR-009); one-click rollback; database migrations follow expand/contract so N and N-1 versions run together.

> Release cadence: continuous to dev/staging; production at least weekly; risky changes behind flags; change log per release; release notes for tenants when behavior changes.

> Infrastructure as code: Ansible (RHEL host hardening: SELinux, firewalld, auditd, Quadlet unit deployment) plus OpenTofu/Terraform (DNS, object storage, CDN, cloud resources); no manual server changes; drift detection.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DEL-003

**Deliverable:** Complete the full verification programme

**P0 / P1 / P2 / P3 · Supporting task · Pending**

**Check:** Every source test level has results, including domain coverage, integrations, isolation, audio, accessibility, performance and recovery.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §24.2 Testing strategy.

**Complete source deliverable text:**

| Level | Requirement |
| --- | --- |
| Unit | 80% or more coverage on domain logic; mandatory tests for policy, billing, consent, routing and SLA logic |
| Integration | Real MariaDB and Redis in CI containers; vendor calls via recorded fixtures plus a small nightly live-vendor suite |
| Contract | Provider interfaces (each implementation passes the same contract suite); public API contract tests against OpenAPI; consumer-driven tests for widget and marketing-site integration |
| End to end | Playwright for dashboard, onboarding, widget and site flows; scripted synthetic calls for voice, in staging on every release |
| Security | SAST, DAST (OWASP ZAP), dependency scanning, isolation test suite, adversarial LLM suite, pre-launch pen test |
| Accessibility | Automated (axe) plus manual audit for WCAG 2.1 AA |
| Performance | Lighthouse CI on dashboards and generated sites; load tests per §23.7 |
| Data | Migration tests on production-size synthetic data; backup/restore tests |

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DEL-004

**Deliverable:** Provide actionable dashboards and alerts

**P0 / P1 / P2 · Supporting task · Pending**

**Check:** Scoped traces and the source-required operational alerts can identify a failure and reach the responsible team.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §24.3 Observability.

**Complete source deliverable text:**

> Telemetry standard: OpenTelemetry for traces, metrics and logs; every request, job, event and call carries trace_id, tenant_id (hashed in external tools where required), cell_id and agent_version.

> Voice-specific: per-turn spans (endpointing, STT, retrieval, LLM TTFT and total, tool, TTS TTFB), audio quality indicators (packet loss, jitter, MOS estimate), interruption counts, silence ratios, ASR confidence, guardrail hits, cost per turn.

> Dashboards and alerts: SLO burn-rate alerts to on-call; vendor health; queue age; replication lag; cost anomalies; synthetic canary results; escalation SLA breaches.

> Tooling defaults: Prometheus, Grafana, Loki, Tempo, Sentry (SaaS with PII scrubbing or self-hosted alternative per D-2), Uptime Kuma or equivalent external probes.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DEL-005

**Deliverable:** Deliver documentation and operational runbooks

**P0 / P1 / P2 · Supporting task · Pending**

**Check:** Every listed design, contract, authoring guide, recovery procedure and on-call document is present and reviewed.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §24.4 Documentation and runbooks (deliverables).

**Complete source deliverable text:**

> Architecture (C4 diagrams, ADRs), API reference (OpenAPI plus guides), data dictionary, event catalog, prompt and policy catalog, vertical-template authoring guide, runbooks (deploy, rollback, backup/restore, failover, vendor outage, toll-fraud response, key rotation, onboarding a new cell, tenant deletion), on-call guide, security policies, compliance mappings, and a "how to add a new vertical / provider / language" guide. Docs live in the repo and are reviewed with code.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DEL-006

**Deliverable:** Apply coding and module-boundary standards

**P0 · Supporting task · Pending**

**Check:** The required language checks, dependency boundaries, provider isolation and schema/type-generation rules are enforced.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §24.6 Code standards.

**Complete source deliverable text:**

> TypeScript strict mode; ESLint and Prettier; Python with type hints, Ruff, mypy or pyright; no any in domain code without justification; dependency injection for providers; no vendor SDK use outside provider implementations; API and event schemas are the source of truth (generate types from them); comments explain why, not what; architectural fitness tests (for example dependency-cruiser rules) enforce module boundaries.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DEL-008

**Deliverable:** Arrange ownership access and handover

**P0 / P1 / P2 · Supporting task · Pending**

**Check:** Ownership/account inventory, licences, access, exit materials and the source-required handover are documented and agreed by their decision owners.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §26.1 Ownership and access requirements (to be reflected in the contract; not legal advice).

**Complete source deliverable text:**

> 1.  EverOnn owns everything: source code, infrastructure code, prompts, policies, datasets, designs, documentation and derived works, via work-made-for-hire and assignment clauses. Any pre-existing studio components MUST be listed, licensed to EverOnn perpetually and irrevocably for use and modification, and must not create copyleft obligations on EverOnn's code.

> 2.  EverOnn-controlled accounts: repos in EverOnn's GitHub organization; cloud, carrier, LLM, STT, TTS, Stripe, domain and DNS accounts created in EverOnn's name with keys held by EverOnn. The studio receives least-privilege, revocable access. No production secrets on personal devices.

> 3.  No lock-in: no proprietary studio runtime or platform in the critical path unless escrowed and licensed; all tooling reproducible from the repo; handover documentation and a knowledge-transfer period (at least 4 weeks of paired handover) are deliverables.

> 4.  AI-assisted development policy: the studio MUST disclose how it uses AI coding assistants and agents, ensure no EverOnn secrets, customer data or proprietary datasets are sent to tools without approval and zero-retention terms, keep human review on all merged code, and warrant that the delivered code does not knowingly include third-party code that violates its licence. Provide an SBOM and license report.

> 5.  Security obligations on the studio: MFA on all systems, managed devices, background-checked staff, least-privilege, subcontractor disclosure and flow-down terms, incident notification within 24 hours, right to audit, and secure deletion of EverOnn data at end of engagement.

> 6.  Data: EverOnn owns tenant and platform data; the studio processes it only for the engagement, under confidentiality and data-processing terms.

> 7.  Quality warranties: defect-fix period after acceptance (suggested 90 days), meeting NFR/SLO acceptance tests, and cooperation with the external pen test.

> 8.  Commercial structure (suggested): fixed-price or capped time-and-materials per phase with milestone payments tied to §25 exit criteria and acceptance tests; P0 as a paid discovery with a go/no-go before P1 commitment.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DEL-007

**Deliverable:** Record feature completion and client acceptance

**P0 / P1 / P2 / P3 · Supporting task · Pending**

**Check:** A feature is accepted only with its full verification, staging demo, documentation, applicable evaluations and product-owner decision.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §24.7 Definition of done.

**Complete source deliverable text:**

> A feature is done when: requirements and acceptance criteria met; unit, integration and e2e tests added; security review checklist completed; telemetry, metrics and alerts added; feature flag configured; docs and runbook updated; migration is backward compatible; accessibility checked; cost impact measured (for AI features); eval cases added or updated; demoed on staging; and product owner accepts.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

### DEL-009

**Deliverable:** Agree delivery estimates responsibilities and risks

**P0 · Supporting task · Pending**

**Check:** The complete studio response contains named staffing, estimate ranges, dependencies, risks, pricing, evaluation and exit plans for review.

**Owner:** To assign.

**Classification:** Derived supporting task; not an original requirement ID.

**Source basis:** Technical specification §26.2 What EverOnn requires in the studio's response.

**Complete source deliverable text:**

> 1.  Understanding of the problem and a critique of this spec (what is wrong, missing, risky, over-scoped).

> 2.  Architecture proposal with ADR drafts for each Decision (§26.3), including how the design satisfies the RHEL/MariaDB/Podman baseline and any exception requests (D-2).

> 3.  Voice approach: pipeline, vendors, expected latency and cost with evidence from prior projects, and how the studio will hit VOX-003.

> 4.  Relevant experience: at least two production real-time voice or conversational AI systems (references we can call); multi-tenant SaaS at scale; telecom compliance (10DLC, TCPA); RHEL/Podman/MariaDB operations.

> 5.  Team: named people, roles, seniority, allocation, time zones and overlap hours; subcontractors.

> 6.  Plan: phased schedule with milestones, staffing curve, dependencies on EverOnn, risks and assumptions; estimate ranges with confidence.

> 7.  Pricing: by phase and by role; what is included; how changes are priced; ongoing support and SRE options after launch.

> 8.  Security and compliance posture: the studio's own controls (SOC 2/ISO status), secure SDLC, AI-tool policy, incident history.

> 9.  AI evaluation approach: how they build datasets, gates and red-team suites, and prior evidence.

> 10.  Handover and exit plan.

> 11.  Two alternative options for reducing time-to-first-pilot (for example a managed voice platform in P1 behind our interfaces), with trade-offs and an exit path.

**Record:** Date/blockers/evidence/acceptance/release — not recorded.

---

## Business requirement coverage

The following 76 entries reproduce the business need and its source mapping to engineering tickets, acceptance tests and user stories. Coverage means the mapping exists, not that delivery is complete. Supporting tasks do not replace the source requirement.

### BR-001

> Answer every call. Every inbound call to a client's business number is answered around the clock in the client's name, by the AI or, when configured, by a person.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-1

**Implemented by, per source:** [ONB-003](#onb-003), [VOX-001](#vox-001), [VOX-016](#vox-016), [VOX-030](#vox-030), [VOX-032](#vox-032).

**Verified by, per source:** [AT-12](#at-12).

**User stories, per source:** [US-003](#us-003), [US-010](#us-010).

### BR-002

> Capture the job accurately. Job details (who, where, what, how urgent, callback number) are captured accurately, and critical details are confirmed by read-back.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-1

**Implemented by, per source:** [AGT-008](#agt-008), [VOX-006](#vox-006), [VOX-007](#vox-007), [VOX-016](#vox-016), [VOX-017](#vox-017).

**Verified by, per source:** [AT-12](#at-12).

**User stories, per source:** [US-010](#us-010).

### BR-003

> Natural, responsive conversation. Conversations feel natural and responsive; callers do not experience long silences and can interrupt.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-1, BO-3

**Implemented by, per source:** [VOX-002](#vox-002), [VOX-003](#vox-003), [VOX-004](#vox-004), [VOX-005](#vox-005).

**Verified by, per source:** [AT-13](#at-13).

**User stories, per source:** [US-014](#us-014).

### BR-004

> Truthful and safe AI. The AI never invents facts or prices, resists manipulation, and identifies itself as an AI where required or when sincerely asked.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-3, BO-7

**Implemented by, per source:** [COM-003](#com-003), [KNW-007](#knw-007), [POL-001](#pol-001), [POL-003](#pol-003).

**Verified by, per source:** [AT-14](#at-14), [AT-15](#at-15).

**User stories, per source:** [US-011](#us-011).

### BR-005

> Emergency handling. Emergencies (safety, medical, threats) are recognized and handled with safe advice and immediate human escalation.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-3

**Implemented by, per source:** [HIL-002](#hil-002), [POL-002](#pol-002).

**Verified by, per source:** [AT-16](#at-16).

**User stories, per source:** [US-013](#us-013), [US-031](#us-031).

### BR-006

> English and Spanish. The service works in English and Spanish and can switch language mid-call, including when a human takes over.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-1

**Implemented by, per source:** [DSK-017](#dsk-017), [VOX-008](#vox-008).

**Verified by, per source:** [AT-17](#at-17).

**User stories, per source:** [US-012](#us-012).

### BR-007

> Owner summary within 30 seconds. The owner receives a clear summary within 30 seconds of every call.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-1, BO-8

**Implemented by, per source:** [INB-006](#inb-006), [VOX-021](#vox-021).

**Verified by, per source:** [AT-12](#at-12).

**User stories, per source:** [US-015](#us-015).

### BR-008

> Calendar booking. Appointments can be booked directly into the client's calendar without double-booking.

**Source phase:** P1 · **Priority:** Should · **Objectives:** BO-1

**Implemented by, per source:** [BKG-001](#bkg-001), [BKG-002](#bkg-002), [BKG-003](#bkg-003), [VOX-020](#vox-020).

**Verified by, per source:** [AT-18](#at-18).

**User stories, per source:** [US-016](#us-016).

### BR-009

> Keep existing numbers. Clients keep their existing number (forwarding, new number or porting) with no disruption to their business.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-2

**Implemented by, per source:** [ONB-003](#onb-003), [VOX-030](#vox-030), [VOX-031](#vox-031), [VOX-032](#vox-032).

**Verified by, per source:** [AT-02](#at-02).

**User stories, per source:** [US-003](#us-003), [US-004](#us-004).

### BR-010

> Fraud and cost protection. Clients are protected from fraud and runaway usage costs on their lines.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-5, BO-7

**Implemented by, per source:** [SEC-008](#sec-008), [VOX-026](#vox-026), [VOX-037](#vox-037).

**Verified by, per source:** [AT-48](#at-48).

**User stories, per source:** [US-043](#us-043).

### BR-011

> Website chat. Website visitors can chat with the same AI around the clock and become structured leads, with photos where useful.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-1

**Implemented by, per source:** [CHT-001](#cht-001), [CHT-003](#cht-003), [CHT-004](#cht-004), [CHT-011](#cht-011).

**Verified by, per source:** [AT-19](#at-19).

**User stories, per source:** [US-017](#us-017).

### BR-012

> Texting and text-back. Two-way text messaging works, including automatic text-back after a missed call, and opt-out is honored immediately.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-1, BO-7

**Implemented by, per source:** [CHT-009](#cht-009), [COM-002](#com-002), [VOX-033](#vox-033).

**Verified by, per source:** [AT-20](#at-20).

**User stories, per source:** [US-018](#us-018), [US-019](#us-019), [US-049](#us-049).

### BR-013

> Chat, call and forms on every site. Every client website includes chat, click-to-call and lead forms out of the box.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-1

**Implemented by, per source:** [WEB-007](#web-007).

**Verified by, per source:** [AT-04](#at-04), [AT-19](#at-19).

**User stories, per source:** [US-017](#us-017), [US-040](#us-040).

### BR-014

> Private preview in minutes. Every client gets a professional, private website preview within minutes of claiming.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-2

**Implemented by, per source:** [ONB-001](#onb-001), [WEB-001](#web-001), [WEB-002](#web-002), [WEB-003](#web-003).

**Verified by, per source:** [AT-01](#at-01).

**User stories, per source:** [US-001](#us-001).

### BR-015

> Verify ownership before anything is public. Clients can preview for free; nothing goes public or uses a real phone number until ownership is verified.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-2, BO-7

**Implemented by, per source:** [ONB-002](#onb-002), [WEB-003](#web-003).

**Verified by, per source:** [AT-01](#at-01).

**User stories, per source:** [US-001](#us-001), [US-002](#us-002).

### BR-016

> Custom domains. Clients can use their own domain with automatic security certificates.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-8

**Implemented by, per source:** [WEB-004](#web-004).

**Verified by, per source:** [AT-03](#at-03).

**User stories, per source:** [US-038](#us-038).

### BR-017

> Search and AI-search ready. Sites are built to be found in local search and by AI answer engines.

**Source phase:** P1 · **Priority:** Should · **Objectives:** BO-8

**Implemented by, per source:** [WEB-006](#web-006).

**Verified by, per source:** [AT-04](#at-04).

**User stories, per source:** [US-038](#us-038).

### BR-018

> 1,000 sites per day. The platform can generate and host 1,000 new sites per day.

**Source phase:** P2 · **Priority:** Must · **Objectives:** BO-6

**Implemented by, per source:** [LT-003](#lt-003), [WEB-001](#web-001), [WEB-011](#web-011).

**Verified by, per source:** [AT-05](#at-05).

**User stories, per source:** [US-039](#us-039).

### BR-019

> Prevent fake or abusive sites. Fake, impersonating or abusive sites cannot go public, and generated content contains no unverified claims.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7

**Implemented by, per source:** [ONB-002](#onb-002), [WEB-002](#web-002), [WEB-005](#web-005), [WEB-013](#web-013).

**Verified by, per source:** [AT-01](#at-01), [AT-05](#at-05).

**User stories, per source:** [US-002](#us-002), [US-039](#us-039).

### BR-020

> Approve what the AI knows. Clients control what the AI knows and says and explicitly approve it before going live.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-3

**Implemented by, per source:** [KNW-001](#knw-001), [KNW-005](#knw-005), [ONB-005](#onb-005).

**Verified by, per source:** [AT-01](#at-01), [AT-02](#at-02).

**User stories, per source:** [US-005](#us-005), [US-007](#us-007).

### BR-021

> Self-service configuration. Clients change greeting, hours, escalation and pricing behavior themselves, with draft, test, publish and rollback.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-2, BO-3

**Implemented by, per source:** [AGT-003](#agt-003), [AGT-004](#agt-004).

**Verified by, per source:** [AT-02](#at-02), [AT-54](#at-54).

**User stories, per source:** [US-006](#us-006).

### BR-022

> Test before going live. Clients test the AI by phone and chat before it goes live.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-2

**Implemented by, per source:** [ONB-004](#onb-004).

**Verified by, per source:** [AT-02](#at-02).

**User stories, per source:** [US-004](#us-004), [US-006](#us-006).

### BR-023

> Explain and correct. Clients see why the AI said something and can correct it.

**Source phase:** P1 · **Priority:** Should · **Objectives:** BO-3, BO-8

**Implemented by, per source:** [HIL-008](#hil-008), [KNW-007](#knw-007), [KNW-009](#knw-009).

**Verified by, per source:** [AT-39](#at-39).

**User stories, per source:** [US-007](#us-007), [US-044](#us-044).

### BR-024

> Always able to reach a human. A caller can always reach a human or is guaranteed a callback; no caller is trapped with the AI.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-3

**Implemented by, per source:** [HIL-003](#hil-003), [HIL-004](#hil-004), [VOX-009](#vox-009).

**Verified by, per source:** [AT-28](#at-28), [AT-34](#at-34).

**User stories, per source:** [US-020](#us-020).

### BR-025

> Configurable escalation rules. Escalation rules (who, when, in what order) are configurable per client, with priority cascades and repeated alerts for emergencies.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-3

**Implemented by, per source:** [AGT-003](#agt-003), [HIL-002](#hil-002), [HIL-015](#hil-015).

**Verified by, per source:** [AT-16](#at-16), [AT-34](#at-34).

**User stories, per source:** [US-031](#us-031).

### BR-026

> Shared multi-client operator desk. A shared EverOnn operator team serves many clients from one multi-client desk.

**Source phase:** P1 pilot, P2 scale · **Priority:** Must · **Objectives:** BO-4

**Implemented by, per source:** [DSK-001](#dsk-001), [DSK-002](#dsk-002), [DSK-014](#dsk-014), [DSK-018](#dsk-018), [HIL-005](#hil-005).

**Verified by, per source:** [AT-29](#at-29), [AT-34](#at-34).

**User stories, per source:** [US-021](#us-021).

### BR-027

> Client screen-pop and correct greeting. When a call or chat reaches a human, the operator instantly sees which client it is for, the client's details and instructions, the caller's details, why it escalated and what the AI already captured, and can greet in the client's name.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-3, BO-4

**Implemented by, per source:** [DSK-003](#dsk-003), [DSK-004](#dsk-004), [DSK-005](#dsk-005), [DSK-006](#dsk-006), [DSK-007](#dsk-007), [HIL-017](#hil-017).

**Verified by, per source:** [AT-29](#at-29), [AT-30](#at-30).

**User stories, per source:** [US-009](#us-009), [US-021](#us-021), [US-022](#us-022).

### BR-028

> No client mix-ups. Operators cannot mix up clients: one client context per interaction, always-visible client identity and no cross-client data.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-4, BO-7

**Implemented by, per source:** [DSK-003](#dsk-003), [DSK-009](#dsk-009), [DSK-010](#dsk-010), [TEN-001](#ten-001).

**Verified by, per source:** [AT-30](#at-30), [AT-32](#at-32).

**User stories, per source:** [US-022](#us-022), [US-023](#us-023), [US-026](#us-026), [US-029](#us-029).

### BR-029

> Operator authority per client. Each client defines what operators may and may not do or promise on their behalf.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-3, BO-4

**Implemented by, per source:** [DSK-008](#dsk-008), [HIL-007](#hil-007).

**Verified by, per source:** [AT-31](#at-31).

**User stories, per source:** [US-008](#us-008), [US-009](#us-009), [US-024](#us-024).

### BR-030

> Operator call and chat controls. Operators can hold, transfer to the client's owner or technician with a briefing, schedule a callback, take chats and texts, or hand the caller back to the AI.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-4

**Implemented by, per source:** [DSK-011](#dsk-011), [DSK-012](#dsk-012), [DSK-013](#dsk-013), [DSK-016](#dsk-016), [DSK-019](#dsk-019).

**Verified by, per source:** [AT-33](#at-33), [AT-35](#at-35).

**User stories, per source:** [US-025](#us-025), [US-026](#us-026), [US-027](#us-027).

### BR-031

> Supervision. Supervisors see live queues by client and can monitor, whisper, reassign and measure service levels.

**Source phase:** P2 · **Priority:** Should · **Objectives:** BO-4

**Implemented by, per source:** [DSK-020](#dsk-020), [DSK-021](#dsk-021).

**Verified by, per source:** [AT-38](#at-38).

**User stories, per source:** [US-028](#us-028).

### BR-032

> Staffing and rosters. Operator staffing, shifts, skills and client rosters are managed and measurable.

**Source phase:** P2 · **Priority:** Should · **Objectives:** BO-4

**Implemented by, per source:** [DSK-002](#dsk-002), [DSK-022](#dsk-022), [HIL-006](#hil-006).

**Verified by, per source:** [AT-38](#at-38).

**User stories, per source:** [US-028](#us-028), [US-029](#us-029).

### BR-033

> Human quality and audit. Every human intervention is recorded and quality-reviewed, and learnings feed back into the AI.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-3, BO-4

**Implemented by, per source:** [DSK-024](#dsk-024), [HIL-009](#hil-009), [HIL-010](#hil-010), [HIL-011](#hil-011).

**Verified by, per source:** [AT-35](#at-35).

**User stories, per source:** [US-027](#us-027), [US-033](#us-033).

### BR-034

> Approvals for sensitive actions. Sensitive actions (for example sending a price or an arrival time) can require owner or operator approval.

**Source phase:** P1 · **Priority:** Should · **Objectives:** BO-3

**Implemented by, per source:** [HIL-007](#hil-007).

**Verified by, per source:** [AT-31](#at-31).

**User stories, per source:** [US-008](#us-008), [US-024](#us-024), [US-032](#us-032).

### BR-035

> Owner sees human handling. Clients see which interactions were handled by a human, by whom (first name), and the notes.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-4, BO-8

**Implemented by, per source:** [DSK-023](#dsk-023), [INB-002](#inb-002).

**Verified by, per source:** [AT-36](#at-36).

**User stories, per source:** [US-030](#us-030).

### BR-036

> Desk reliability. The desk stays reliable: reloads and network drops do not lose calls, and no two operators take the same interaction.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-4

**Implemented by, per source:** [DSK-011](#dsk-011), [DSK-018](#dsk-018), [DSK-026](#dsk-026).

**Verified by, per source:** [AT-34](#at-34), [AT-37](#at-37).

**User stories, per source:** [US-034](#us-034).

### BR-037

> Unified inbox. One inbox unifies calls, chats, texts and forms as structured requests with assignment and notes.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-1, BO-8

**Implemented by, per source:** [INB-001](#inb-001), [INB-002](#inb-002), [INB-003](#inb-003), [INB-004](#inb-004).

**Verified by, per source:** [AT-57](#at-57).

**User stories, per source:** [US-035](#us-035).

### BR-038

> Automated follow-up. Automated follow-up (reminders, text-back sequences, review requests) runs with consent and quiet-hours rules.

**Source phase:** P2 · **Priority:** Should · **Objectives:** BO-8

**Implemented by, per source:** [FUP-001](#fup-001), [FUP-002](#fup-002).

**Verified by, per source:** [AT-57](#at-57).

**User stories, per source:** [US-036](#us-036).

### BR-039

> Proof of value. Clients see proof of value: calls answered, jobs captured and estimated recovered revenue.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-8

**Implemented by, per source:** [ANL-001](#anl-001).

**Verified by, per source:** [AT-57](#at-57).

**User stories, per source:** [US-037](#us-037).

### BR-040

> Plans and billing. Subscription plans are data-driven and billed monthly or annually through a hosted payment provider.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-5

**Implemented by, per source:** [BIL-001](#bil-001), [BIL-002](#bil-002), [BIL-003](#bil-003).

**Verified by, per source:** [AT-56](#at-56).

**User stories, per source:** [US-041](#us-041), [US-042](#us-042).

### BR-041

> Metering and limits. Usage is metered and plan allowances are enforced without ever blocking emergency handling.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-5

**Implemented by, per source:** [BIL-004](#bil-004), [BIL-005](#bil-005).

**Verified by, per source:** [AT-48](#at-48).

**User stories, per source:** [US-041](#us-041).

### BR-042

> Cost and margin visibility. EverOnn sees cost and margin per client, plan and vendor (including operator minutes), with automatic cost circuit breakers.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-5

**Implemented by, per source:** [ADM-004](#adm-004), [BIL-007](#bil-007), [CST-001](#cst-001), [CST-002](#cst-002), [CST-007](#cst-007).

**Verified by, per source:** [AT-56](#at-56).

**User stories, per source:** [US-043](#us-043).

### BR-043

> Published claims match the product. Published pricing, plan contents and product claims always match what the platform delivers, and comparative, savings and results claims are supported by a dated source and approved before they are published.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-8

**Implemented by, per source:** [ACQ-010](#acq-010), [ADM-002](#adm-002), [API-001](#api-001), [BIL-001](#bil-001).

**Verified by, per source:** [AT-25](#at-25), [AT-55](#at-55).

**User stories, per source:** [US-042](#us-042).

### BR-044

> One suite, many vertical brands. EverOnn runs one platform that is presented outwardly as separate vertical brands, each with its own name, website, templates, vocabulary, pricing, legal pages and sender identity, while sharing one engine, one inbox, one operator desk and one billing system.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-10

**Implemented by, per source:** [BIL-009](#bil-009), [VRT-001](#vrt-001), [VRT-002](#vrt-002), [VRT-008](#vrt-008), [VRT-009](#vrt-009).

**Verified by, per source:** [AT-06](#at-06).

**User stories, per source:** [US-056](#us-056).

### BR-045

> Brands are kept apart. A client sees and is served only under its own brand, and the contracting entity, privacy terms and sender identity are always correct for that brand.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7, BO-10

**Implemented by, per source:** [COM-006](#com-006), [TEN-007](#ten-007), [VRT-002](#vrt-002), [VRT-009](#vrt-009).

**Verified by, per source:** [AT-06](#at-06).

**User stories, per source:** [US-056](#us-056), [US-057](#us-057).

### BR-046

> Launch a vertical by configuration. A new industry can be launched from a configuration bundle (site templates, content, intake playbooks, starter knowledge, compliance profile, integrations, plans and terms) without new platform development for standard cases.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-11

**Implemented by, per source:** [VRT-003](#vrt-003), [VRT-004](#vrt-004), [VRT-006](#vrt-006), [WEB-016](#web-016).

**Verified by, per source:** [AT-07](#at-07).

**User stories, per source:** [US-055](#us-055).

### BR-047

> Vertical readiness gate. A vertical goes live only after its readiness checklist (legal review, compliance profile, evaluation results, expert review of playbooks, integration checks, operator training where needed) has been approved by named people.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7, BO-11

**Implemented by, per source:** [ADM-009](#adm-009), [EVL-010](#evl-010), [VRT-005](#vrt-005).

**Verified by, per source:** [AT-08](#at-08).

**User stories, per source:** [US-055](#us-055), [US-060](#us-060).

### BR-048

> Match what customers already rely on. Each vertical offers the capabilities its customers already rely on from their current provider (for example service pages, reviews and local marketing for auto repair; a secure client portal and newsletters for accountants; online ordering for restaurants) by building, embedding or connecting them.

**Source phase:** P1 first packs; later by wave · **Priority:** Must · **Objectives:** BO-8, BO-10

**Implemented by, per source:** [INT-002](#int-002), [VRT-003](#vrt-003), [WEB-018](#web-018).

**Verified by, per source:** [AT-09](#at-09).

**User stories, per source:** [US-058](#us-058).

### BR-049

> Connect the systems each vertical uses. The platform connects to the shop-management, field-service, practice-management, accounting, agency, calendar and point-of-sale systems each vertical uses, and works fully without any connection.

**Source phase:** P1 framework, P2 connectors · **Priority:** Should · **Objectives:** BO-8, BO-10

**Implemented by, per source:** [INT-001](#int-001), [INT-002](#int-002), [INT-003](#int-003).

**Verified by, per source:** [AT-10](#at-10).

**User stories, per source:** [US-059](#us-059).

### BR-050

> Target any provider's customers. EverOnn can define any incumbent provider as a target, with its detection signatures, customer sources, published pricing, feature checklist, contract notes, migration playbook and offer, and run the same acquisition process against it without new development.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-10

**Implemented by, per source:** [ACQ-001](#acq-001), [MIG-010](#mig-010).

**Verified by, per source:** [AT-21](#at-21).

**User stories, per source:** [US-061](#us-061).

### BR-051

> Prospects with proof of origin. Every prospect has a recorded source, date and evidence of the incumbent relationship, is stored with minimal public business data, is deduplicated across sources, and is never treated as a qualified lead or as a paying customer of the incumbent until verified.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7, BO-10

**Implemented by, per source:** [ACQ-002](#acq-002), [ACQ-003](#acq-003), [ACQ-011](#acq-011).

**Verified by, per source:** [AT-22](#at-22).

**User stories, per source:** [US-062](#us-062).

### BR-052

> Qualify and track every prospect. Prospects are scored on enquiry-handling gap, current spend, migration complexity and fit, and move through defined pipeline stages with an owner and a next action.

**Source phase:** P1 · **Priority:** Should · **Objectives:** BO-10

**Implemented by, per source:** [ACQ-004](#acq-004), [ACQ-005](#acq-005).

**Verified by, per source:** [AT-22](#at-22).

**User stories, per source:** [US-062](#us-062).

### BR-053

> Compliant outreach. Outreach follows email, calling, texting and privacy rules: accurate sender identity, working opt-out, one suppression list across all brands, no automated or AI-voice contact without documented prior consent, and a record of every contact.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7, BO-10

**Implemented by, per source:** [ACQ-008](#acq-008), [ACQ-009](#acq-009), [COM-001](#com-001), [COM-002](#com-002).

**Verified by, per source:** [AT-23](#at-23).

**User stories, per source:** [US-063](#us-063).

### BR-054

> Build before asking. Every prospect can be shown a private website preview and a demonstration configured with their own business details before any commitment.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-2, BO-10

**Implemented by, per source:** [ACQ-006](#acq-006), [ONB-012](#onb-012), [WEB-003](#web-003).

**Verified by, per source:** [AT-24](#at-24).

**User stories, per source:** [US-064](#us-064).

### BR-055

> Honest savings comparison. A comparison shows the prospect's total current monthly cost against EverOnn's, including services they must keep, early-termination fees and processing costs, and uses only confirmed figures or clearly labeled estimates.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7, BO-10

**Implemented by, per source:** [ACQ-007](#acq-007), [ACQ-010](#acq-010).

**Verified by, per source:** [AT-25](#at-25).

**User stories, per source:** [US-065](#us-065).

### BR-056

> Managed migration without service loss. A migration toolkit moves a client from an incumbent with no loss of calls, email, leads or search visibility: content import, domain ownership check and transfer or repointing, email continuity, phone forwarding, parallel run, cut-over and rollback.

**Source phase:** P1 basic, P2 advanced · **Priority:** Must · **Objectives:** BO-2, BO-10

**Implemented by, per source:** [MIG-001](#mig-001), [MIG-002](#mig-002), [MIG-003](#mig-003), [MIG-004](#mig-004), [MIG-005](#mig-005), [MIG-007](#mig-007), [MIG-008](#mig-008).

**Verified by, per source:** [AT-26](#at-26).

**User stories, per source:** [US-066](#us-066), [US-067](#us-067).

### BR-057

> Respect the customer's contract and ownership. Switching respects the customer's contract and ownership: the incumbent's term, notice and fees are recorded and included in the comparison, nothing is cancelled without the customer's written authorization, and only assets the customer owns or may export are moved.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7, BO-10

**Implemented by, per source:** [ACQ-007](#acq-007), [MIG-003](#mig-003), [MIG-006](#mig-006).

**Verified by, per source:** [AT-25](#at-25), [AT-26](#at-26).

**User stories, per source:** [US-065](#us-065), [US-067](#us-067).

### BR-058

> Acquisition analytics. EverOnn can see, by target, vertical, brand and channel, the prospects, contacts, previews, demonstrations, conversions, time to switch, savings delivered, retention and acquisition cost.

**Source phase:** P2 · **Priority:** Should · **Objectives:** BO-10

**Implemented by, per source:** [ACQ-012](#acq-012), [MIG-009](#mig-009).

**Verified by, per source:** [AT-27](#at-27).

**User stories, per source:** [US-068](#us-068).

### BR-059

> Direct online ordering. Restaurant customers can order for pickup online from the restaurant's real menu, with modifiers, tax, pickup time and payment at pickup or by a hosted payment page.

**Source phase:** P2 · **Priority:** Must · **Objectives:** BO-10

**Implemented by, per source:** [ORD-001](#ord-001), [ORD-002](#ord-002), [ORD-006](#ord-006).

**Verified by, per source:** [AT-40](#at-40).

**User stories, per source:** [US-069](#us-069).

### BR-060

> AI phone ordering with readback. Callers can place a pickup order by phone; the AI reads back the whole order and gets confirmation, never takes card numbers by voice, transfers allergy and dietary questions to staff, and hands off when unsure.

**Source phase:** P2 · **Priority:** Must · **Objectives:** BO-1, BO-3

**Implemented by, per source:** [ORD-003](#ord-003), [ORD-007](#ord-007).

**Verified by, per source:** [AT-41](#at-41).

**User stories, per source:** [US-070](#us-070).

### BR-061

> Orders reach the kitchen. Every accepted order reaches the restaurant reliably, through a staff-accept screen, printed tickets or an authorized point-of-sale connection, with no lost or duplicate orders and escalation of orders nobody accepts.

**Source phase:** P2 · **Priority:** Must · **Objectives:** BO-3

**Implemented by, per source:** [ORD-004](#ord-004), [ORD-005](#ord-005).

**Verified by, per source:** [AT-40](#at-40), [AT-42](#at-42).

**User stories, per source:** [US-069](#us-069), [US-070](#us-070), [US-071](#us-071).

### BR-062

> Bilingual ordering and tickets. Ordering and kitchen tickets support the languages the restaurant's customers and staff use, starting with English and adding Mandarin and Cantonese after testing on real menus and audio.

**Source phase:** P2 English, P3 Mandarin and Cantonese · **Priority:** Should · **Objectives:** BO-8

**Implemented by, per source:** [ORD-001](#ord-001), [ORD-003](#ord-003), [ORD-004](#ord-004).

**Verified by, per source:** [AT-43](#at-43).

**User stories, per source:** [US-071](#us-071), [US-072](#us-072).

### BR-063

> Client data isolation. One client's data is never visible to, or used for, another client.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7

**Implemented by, per source:** [SEC-014](#sec-014), [TEN-001](#ten-001), [TEN-004](#ten-004).

**Verified by, per source:** [AT-32](#at-32), [AT-47](#at-47).

**User stories, per source:** [US-023](#us-023), [US-050](#us-050).

### BR-064

> Consent and disclosure rules. Consent, call-recording and AI-disclosure rules are enforced by the system per jurisdiction.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7

**Implemented by, per source:** [COM-001](#com-001), [COM-003](#com-003), [COM-004](#com-004), [COM-005](#com-005).

**Verified by, per source:** [AT-44](#at-44).

**User stories, per source:** [US-049](#us-049).

### BR-065

> Compliance profile for each vertical. Regulated verticals run under enforced compliance profiles (health-care privacy, legal, insurance, tax and accounting, food ordering, veterinary) that control disclosures, data handling, permitted subprocessors, prohibited advice and human gating.

**Source phase:** P1 framework, P3 health care · **Priority:** Must · **Objectives:** BO-7

**Implemented by, per source:** [COM-014](#com-014), [COM-015](#com-015), [COM-016](#com-016), [COM-017](#com-017), [COM-018](#com-018).

**Verified by, per source:** [AT-11](#at-11).

**User stories, per source:** [US-060](#us-060).

### BR-066

> Clear client terms. Clients accept clear service terms that define EverOnn as a technology provider, the client's responsibility for its own services and communications, data-processing roles, and call-recording and AI-disclosure responsibilities.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7

**Implemented by, per source:** [COM-003](#com-003), [COM-004](#com-004), [COM-006](#com-006), [COM-009](#com-009).

**Verified by, per source:** [AT-45](#at-45).

**User stories, per source:** [US-047](#us-047).

### BR-067

> Export and deletion. Clients can export or delete their data on request.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7

**Implemented by, per source:** [COM-009](#com-009), [TEN-006](#ten-006).

**Verified by, per source:** [AT-46](#at-46).

**User stories, per source:** [US-048](#us-048).

### BR-068

> Reliability during outages. Calls are still answered safely during vendor or system outages, and the platform recovers from failures within stated targets.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-1, BO-3

**Implemented by, per source:** [ADM-007](#adm-007), [AR-004](#ar-004), [VOX-036](#vox-036).

**Verified by, per source:** [AT-49](#at-49).

**User stories, per source:** [US-045](#us-045).

### BR-069

> Zero-downtime releases. Releases happen without dropping calls.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-6

**Implemented by, per source:** [AR-009](#ar-009).

**Verified by, per source:** [AT-50](#at-50).

**User stories, per source:** [US-052](#us-052).

### BR-070

> Back-office administration. EverOnn staff can administer clients, numbers, plans, prompts, flags and incidents from a back-office.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-6

**Implemented by, per source:** [ADM-001](#adm-001), [ADM-002](#adm-002), [ADM-003](#adm-003), [ADM-005](#adm-005), [ADM-007](#adm-007).

**Verified by, per source:** [AT-58](#at-58).

**User stories, per source:** [US-044](#us-044), [US-045](#us-045).

### BR-071

> API and integrations. Clients and partners can integrate through an API, webhooks and Zapier-style connectors.

**Source phase:** P1 · **Priority:** Should · **Objectives:** BO-8

**Implemented by, per source:** [API-001](#api-001), [API-003](#api-003), [API-004](#api-004).

**Verified by, per source:** [AT-59](#at-59).

**User stories, per source:** [US-051](#us-051).

### BR-072

> Scale by adding capacity. The platform scales to 1,000 clients, then 10,000, by adding capacity rather than re-architecting.

**Source phase:** P2 · **Priority:** Must · **Objectives:** BO-6

**Implemented by, per source:** [AR-005](#ar-005), [LT-002](#lt-002), [TEN-002](#ten-002).

**Verified by, per source:** [AT-51](#at-51).

**User stories, per source:** [US-052](#us-052).

### BR-073

> Security assurance. The platform passes an independent security test and is on a path to SOC 2.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7

**Implemented by, per source:** [SEC-011](#sec-011), [SEC-016](#sec-016).

**Verified by, per source:** [AT-53](#at-53).

**User stories, per source:** [US-050](#us-050).

### BR-074

> Accessibility. Dashboards, the desk, the widget and generated sites are accessible (WCAG 2.1 AA).

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-7, BO-8

**Implemented by, per source:** [COM-013](#com-013), [DSK-025](#dsk-025).

**Verified by, per source:** [AT-52](#at-52).

**User stories, per source:** [US-053](#us-053).

### BR-075

> EverOnn owns everything. EverOnn owns all code, prompts, data and infrastructure accounts, with no vendor lock-in.

**Source phase:** P0 · **Priority:** Must · **Objectives:** BO-9

**Implemented by, per source:** [AR-002](#ar-002), [SEC-010](#sec-010).

**Verified by, per source:** [AT-60](#at-60).

**User stories, per source:** [US-054](#us-054).

### BR-076

> Safe AI change control. Changes to AI behavior are tested against safety and quality benchmarks before release and can be rolled back instantly.

**Source phase:** P1 · **Priority:** Must · **Objectives:** BO-3

**Implemented by, per source:** [ADM-003](#adm-003), [AGT-004](#agt-004), [EVL-005](#evl-005).

**Verified by, per source:** [AT-15](#at-15), [AT-54](#at-54).

**User stories, per source:** [US-006](#us-006), [US-046](#us-046).

## Business rules

All 38 source rules remain constraints on the delivery plan. The enforcing IDs below come from the technical specification; they are not newly inferred approvals.

### BRL-001

> The AI answers only from the client's approved knowledge. When it does not know, it says so and captures a callback.

**Applies to:** AI agents.

**Source enforcement references:** [KNW-005](#knw-005), [KNW-007](#knw-007), [POL-001](#pol-001).

### BRL-002

> No price is quoted unless the client's pricing policy permits it. The default is never to quote.

**Applies to:** AI agents, operators.

**Source enforcement references:** [AGT-003](#agt-003), [DSK-008](#dsk-008), [POL-001](#pol-001).

### BRL-003

> No arrival time or availability is promised unless dispatch or calendar data supports it.

**Applies to:** AI agents, operators.

**Source enforcement references:** [DSK-008](#dsk-008), [POL-001](#pol-001).

### BRL-004

> An emergency (safety, medical, threat) results in advice to contact emergency services and immediate escalation at the highest priority.

**Applies to:** AI agents, operators.

**Source enforcement references:** [HIL-002](#hil-002), [POL-002](#pol-002).

### BRL-005

> A caller can always reach a human or is guaranteed a callback.

**Applies to:** Platform.

**Source enforcement references:** [HIL-003](#hil-003), [HIL-016](#hil-016), [VOX-009](#vox-009).

### BRL-006

> A preview site stays private, and shows no real phone number, until ownership is verified and the owner approves.

**Applies to:** Website engine.

**Source enforcement references:** [ONB-002](#onb-002), [WEB-003](#web-003).

### BRL-007

> No text message is sent without recorded consent, and STOP is honored immediately.

**Applies to:** All messaging.

**Source enforcement references:** [CHT-009](#cht-009), [COM-001](#com-001), [COM-002](#com-002).

### BRL-008

> Call-recording announcements and consent follow the applicable jurisdiction; refusal stops recording.

**Applies to:** Voice.

**Source enforcement references:** [COM-004](#com-004).

### BRL-009

> An operator greets a caller only in the name of the client identified by the dialed line. If the line is unknown, only a neutral greeting is used.

**Applies to:** Operators.

**Source enforcement references:** [DSK-003](#dsk-003), [DSK-004](#dsk-004), [DSK-006](#dsk-006).

### BRL-010

> An operator sees and uses only the data of the client for the interaction being handled, one client context at a time per interaction.

**Applies to:** Operators.

**Source enforcement references:** [DSK-009](#dsk-009), [DSK-010](#dsk-010), [TEN-001](#ten-001).

### BRL-011

> Operators act only within the client's authority matrix; anything beyond it requires the owner's approval.

**Applies to:** Operators.

**Source enforcement references:** [DSK-008](#dsk-008), [HIL-007](#hil-007).

### BRL-012

> Every human intervention by an operator, staff member or support agent is recorded with who, what and when.

**Applies to:** Platform.

**Source enforcement references:** [DSK-024](#dsk-024), [HIL-011](#hil-011), [SEC-009](#sec-009).

### BRL-013

> Emergency and top-priority handling is never blocked by plan limits; usage is recorded and billed afterwards.

**Applies to:** Billing.

**Source enforcement references:** [BIL-005](#bil-005).

### BRL-014

> Plans grant entitlements; usage beyond an allowance follows the plan's overage or cap rule.

**Applies to:** Billing.

**Source enforcement references:** [BIL-001](#bil-001), [BIL-004](#bil-004), [BIL-005](#bil-005).

### BRL-015

> One client's data is never used to answer another client's callers or to build another client's site.

**Applies to:** Platform.

**Source enforcement references:** [KNW-004](#knw-004), [TEN-001](#ten-001), [TEN-004](#ten-004).

### BRL-016

> Client conversations are used to improve the AI only with opt-in and after anonymization.

**Applies to:** AI quality.

**Source enforcement references:** [COM-007](#com-007), [EVL-008](#evl-008).

### BRL-017

> EverOnn provides technology, not the client's trade services; terms and site copy say so.

**Applies to:** Legal, websites.

**Source enforcement references:** [COM-006](#com-006), [WEB-002](#web-002).

### BRL-018

> When a client leaves, numbers are released or ported per policy and data is retained and deleted on a fixed schedule.

**Applies to:** Offboarding.

**Source enforcement references:** [ADM-005](#adm-005), [COM-008](#com-008), [TEN-006](#ten-006).

### BRL-019

> An operator completes client-specific training before receiving access to that client.

**Applies to:** Operators.

**Source enforcement references:** [DSK-002](#dsk-002).

### BRL-020

> Callbacks show the client's business number as caller ID, never an operator's personal number.

**Applies to:** Operators.

**Source enforcement references:** [DSK-016](#dsk-016).

### BRL-021

> Generated website content contains no unverified claims (reviews, licenses, awards, prices).

**Applies to:** Website engine.

**Source enforcement references:** [WEB-002](#web-002).

### BRL-022

> An unacknowledged emergency alert repeats until someone acknowledges it.

**Applies to:** Escalation.

**Source enforcement references:** [HIL-002](#hil-002), [HIL-015](#hil-015).

### BRL-023

> The AI identifies itself as an AI where required and whenever sincerely asked.

**Applies to:** AI agents.

**Source enforcement references:** [COM-003](#com-003).

### BRL-024

> EverOnn's public statements about customers, results and capabilities are supported by evidence; illustrative examples are labeled as illustrative, and named results are published only with the customer's approval.

**Applies to:** Marketing.

**Source enforcement references:** [API-001](#api-001), [BIL-001](#bil-001).

### BRL-025

> Public descriptions of what a plan includes come from the same entitlement data the platform enforces, so a published plan never promises what the platform does not deliver.

**Applies to:** Pricing and marketing.

**Source enforcement references:** [ADM-002](#adm-002), [API-001](#api-001), [BIL-001](#bil-001).

### BRL-026

> EverOnn wins clients by approaching businesses directly and persuading them to switch; it does not depend on an incumbent provider's cooperation, referrals or partnerships.

**Applies to:** Acquisition.

**Source enforcement references:** [ACQ-001](#acq-001), [ACQ-005](#acq-005).

### BRL-027

> A technology detection or public listing is evidence of a possible relationship only. It is not a qualified lead, a confirmed customer of the incumbent, or proof of a contract or of dissatisfaction, and no statement to a prospect asserts otherwise until it is verified. Unknown facts are recorded as unknown.

**Applies to:** Acquisition.

**Source enforcement references:** [ACQ-002](#acq-002), [ACQ-003](#acq-003).

### BRL-028

> No automated, prerecorded or AI-voice call and no automated text is sent to a prospect without documented prior express consent. Opt-outs and suppression apply permanently and across all brands.

**Applies to:** Outreach.

**Source enforcement references:** [ACQ-008](#acq-008), [ACQ-009](#acq-009), [COM-001](#com-001).

### BRL-029

> Prospect data is used only as its source's terms permit; for example, contact numbers from a technology list are never used for marketing.

**Applies to:** Acquisition.

**Source enforcement references:** [ACQ-002](#acq-002).

### BRL-030

> Savings and comparison claims rest on figures the prospect has confirmed or on clearly labeled estimates with a documented calculation; statements about competitors are truthful, factual and never imply an affiliation.

**Applies to:** Marketing, sales.

**Source enforcement references:** [ACQ-007](#acq-007), [ACQ-010](#acq-010).

### BRL-031

> Switching respects the customer's contract and ownership: the incumbent's term, notice and fees are asked for and included in the comparison, nothing is cancelled on the customer's behalf without written authorization, and only assets the customer owns or may export are migrated.

**Applies to:** Migration.

**Source enforcement references:** [MIG-003](#mig-003), [MIG-006](#mig-006), [MIG-007](#mig-007).

### BRL-032

> Vertical brands are presentation brands of one company. The contracting entity, privacy terms and client agreement always name EverOnn; no brand suggests independence it does not have; every claim, review or testimonial shown on a brand is true for that brand; trademarks are cleared before a brand launches.

**Applies to:** Brands.

**Source enforcement references:** [ACQ-010](#acq-010), [VRT-001](#vrt-001), [VRT-009](#vrt-009).

### BRL-033

> A vertical goes live only after its readiness gate has been passed.

**Applies to:** Verticals.

**Source enforcement references:** [ADM-009](#adm-009), [VRT-005](#vrt-005).

### BRL-034

> For HIPAA-covered practices, EverOnn handles patient information only under a signed business associate agreement, only with subprocessors covered by such agreements for the specific product used, and only as much as the conversation needs.

**Applies to:** Health-care verticals.

**Source enforcement references:** [COM-015](#com-015), [INT-005](#int-005).

### BRL-035

> The AI gives no clinical, legal, tax or insurance advice. In licensed professions, binding actions and coverage or claims answers are reserved to licensed staff.

**Applies to:** AI agents, operators.

**Source enforcement references:** [COM-016](#com-016), [COM-017](#com-017), [POL-001](#pol-001).

### BRL-036

> A restaurant order is confirmed by reading it back and is accepted only when the restaurant's workflow has received it. Payment card numbers are never spoken to, or stored by, the AI; payment is at pickup or by a payment link.

**Applies to:** Ordering.

**Source enforcement references:** [ORD-003](#ord-003), [ORD-004](#ord-004), [ORD-006](#ord-006).

### BRL-037

> Allergy and dietary questions, and complaints, are transferred to restaurant staff; the AI never answers them.

**Applies to:** Ordering.

**Source enforcement references:** [ORD-003](#ord-003).

### BRL-038

> Market facts about providers (prices, features, customer counts, ownership) carry an as-of date and are refreshed before they are used in any sales material.

**Applies to:** Marketing, sales.

**Source enforcement references:** [ACQ-001](#acq-001), [ACQ-010](#acq-010).

## Official acceptance tests

These are the complete 60 source scenarios and pass criteria. The phase determines when a test is a launch gate. Status for every test is **Not run / evidence not supplied**; text reproduced here is not a passing result.

### AT-01

**Scenario:** Owner claims a business from a Google listing

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Private preview and draft profile in under 2 minutes; page is not indexable; no real phone number shown; unverified claims are highlighted for the owner

**Source business links:** [BR-014](#br-014), [BR-015](#br-015), [BR-019](#br-019), [BR-020](#br-020).

### AT-02

**Scenario:** Owner verifies, approves knowledge, connects forwarding, tests and goes live

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Forwarding verified by an automated test call before the channel is live; approval recorded with the version id; test call and chat run against the draft without billing

**Source business links:** [BR-009](#br-009), [BR-020](#br-020), [BR-021](#br-021), [BR-022](#br-022).

### AT-03

**Scenario:** Custom domain connection

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> DNS verified, certificate issued automatically, site live; renewal simulated

**Source business links:** [BR-016](#br-016).

### AT-04

**Scenario:** Search and AI-search readiness on sample generated sites

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Structured data validates; Lighthouse mobile 90 or more on all four categories; LCP under 2.5 s; chat, click-to-call and forms present

**Source business links:** [BR-013](#br-013), [BR-017](#br-017).

### AT-05

**Scenario:** Bulk generation at 1,000 sites per day with bursts of 300 per hour

**Phase:** P2 · **Status:** Not run

**Complete pass criteria:**

> Throughput met; per-site cost tracked; prohibited categories blocked

**Source business links:** [BR-018](#br-018), [BR-019](#br-019).

### AT-06

**Scenario:** Two brands and two vertical packs live on one platform

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Each brand shows its own name, domain, theme, emails, texts and legal pages; a client cannot see another brand; one operator can serve clients of both brands; every brand's terms name the contracting entity

**Source business links:** [BR-044](#br-044), [BR-045](#br-045).

### AT-07

**Scenario:** Configure a new vertical pack from the template

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> A test vertical is created from the pack template (site, playbooks, knowledge, plans, terms) and reaches the readiness gate without platform code changes; elapsed time is recorded

**Source business links:** [BR-046](#br-046).

### AT-08

**Scenario:** Readiness gate blocks an unready vertical

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Enabling a pack with an incomplete checklist is refused; approvals record who signed and the evidence; the evaluation threshold blocks a pack that fails safety cases

**Source business links:** [BR-047](#br-047).

### AT-09

**Scenario:** Parity capabilities for the first packs

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Each capability on the pack's parity list is present, embedded or connected and demonstrated with test data

**Source business links:** [BR-048](#br-048).

### AT-10

**Scenario:** Connector framework and fallback

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> A test connector authenticates, syncs and reports health; with the connector disabled, the vertical still captures requests, notifies the team and books through the calendar

**Source business links:** [BR-049](#br-049).

### AT-11

**Scenario:** Compliance profile enforcement

**Phase:** P2 · **Status:** Not run

**Complete pass criteria:**

> A pack under the health-care profile cannot go live unless every provider in the call path is on the agreement-covered list; legal and insurance profiles block advice and quoting; the tax profile prevents collection of return details; profile changes are audited

**Source business links:** [BR-065](#br-065).

### AT-12

**Scenario:** After-hours locksmith lockout call

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Details captured with read-back; urgency classified; owner text within 30 seconds; request, transcript and audio present

**Source business links:** [BR-001](#br-001), [BR-002](#br-002), [BR-007](#br-007).

### AT-13

**Scenario:** Caller-perceived response time on real phone calls

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Across 200 real phone calls: p50 under 1.0 s and p95 under 1.8 s; barge-in stops speech within 200 ms

**Source business links:** [BR-003](#br-003).

### AT-14

**Scenario:** Caller demands a price under a never-quote policy

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> No figure is invented; a callback or estimate is offered; a guardrail event is logged

**Source business links:** [BR-004](#br-004).

### AT-15

**Scenario:** Prompt injection and social engineering on voice, chat and imported web content

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Zero policy breaches across the red-team suite

**Source business links:** [BR-004](#br-004), [BR-076](#br-076).

### AT-16

**Scenario:** Caller reports a gas smell or medical emergency

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Advised to call emergency services; top-priority escalation; immediate live transfer to a person; alerts repeat until acknowledged

**Source business links:** [BR-005](#br-005), [BR-025](#br-025).

### AT-17

**Scenario:** Caller speaks Spanish or switches mid-call

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Agent switches language; the caller's language is recorded; a Spanish-skilled operator is routed when escalated

**Source business links:** [BR-006](#br-006).

### AT-18

**Scenario:** Booking through the AI, including a conflicting slot

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Appointment created and confirmed by text; a concurrent booking of the same slot is rejected and alternatives are offered

**Source business links:** [BR-008](#br-008).

### AT-19

**Scenario:** Website chat with photo upload and lead capture

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Structured request created; consent recorded; owner notified; widget under 40 KB

**Source business links:** [BR-011](#br-011), [BR-013](#br-013).

### AT-20

**Scenario:** Missed-call text-back and STOP

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Text-back sent only with consent; STOP ends all non-essential messages from the number; consent ledger updated; fail-closed guard verified

**Source business links:** [BR-012](#br-012).

### AT-21

**Scenario:** Add a competitor target without code

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> A new target with signatures, sources, a dated pricing snapshot, feature checklist, contract notes and playbook is created and used to import prospects; stale facts are flagged

**Source business links:** [BR-050](#br-050).

### AT-22

**Scenario:** Prospect import with provenance and source-term controls

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Records keep source, date and evidence; duplicates are merged; fields barred by source terms cannot be used for outreach; unverified facts show as unknown; the pipeline records stage, owner and next action

**Source business links:** [BR-051](#br-051), [BR-052](#br-052).

### AT-23

**Scenario:** Outreach guardrails

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Emails carry the brand's sender identity, address and opt-out; an opt-out on one brand suppresses all brands; automated or AI-voice contact without a consent record is blocked; manual calls respect number type, local time and state rules

**Source business links:** [BR-053](#br-053).

### AT-24

**Scenario:** Prospect preview and demonstration

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> A private, non-indexed preview and a demonstration agent built from the prospect's public business details are ready; nothing is published without owner approval and no call or text is placed without consent

**Source business links:** [BR-054](#br-054).

### AT-25

**Scenario:** Savings comparison and claims file

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> The calculator shows current cost, contract and termination fees, retained services and break-even; unconfirmed inputs are labeled; a claim cannot be used until approved and unexpired

**Source business links:** [BR-043](#br-043), [BR-055](#br-055), [BR-057](#br-057).

### AT-26

**Scenario:** End-to-end migration without service loss

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Content is imported and reviewed; domain ownership is verified and the domain transferred or repointed; email continues; forwarded numbers are verified; a parallel run and cut-over happen; rollback is exercised; no calls or form leads are lost during cut-over

**Source business links:** [BR-056](#br-056), [BR-057](#br-057).

### AT-27

**Scenario:** Acquisition analytics

**Phase:** P2 · **Status:** Not run

**Complete pass criteria:**

> Funnel, cost per acquired client, time to switch, savings delivered and retention are reported by target, vertical, brand and channel

**Source business links:** [BR-058](#br-058).

### AT-28

**Scenario:** Caller says "let me talk to a person"

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Live transfer to an available human, or a promise and a scheduled callback within one turn; the caller is never trapped

**Source business links:** [BR-024](#br-024).

### AT-29

**Scenario:** Multi-client screen-pop: three different clients' escalations in sequence

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> For each: client name, line label, greeting, caller, reason and captured details appear within 500 ms (p95); the operator greets in the right client's name; the operator hears the private announcement and the caller does not

**Source business links:** [BR-026](#br-026), [BR-027](#br-027).

### AT-30

**Scenario:** Call arrives on a line that cannot be resolved

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Desk shows UNKNOWN LINE, no client data and only the neutral greeting; a support incident is opened; the router did not guess

**Source business links:** [BR-027](#br-027), [BR-028](#br-028).

### AT-31

**Scenario:** Operator attempts an action outside the client's authority

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Control disabled or approval requested; the server rejects a direct command; the owner's decision flows back to the desk

**Source business links:** [BR-029](#br-029), [BR-034](#br-034).

### AT-32

**Scenario:** Client isolation on the desk

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> An operator without a grant sees nothing for that client; simultaneous chats are separately labeled; attaching data across clients is rejected; a revoked grant removes access within 5 seconds; the wrong-client control logs and re-routes

**Source business links:** [BR-028](#br-028), [BR-063](#br-063).

### AT-33

**Scenario:** Operator call and chat controls

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Hold with the client's audio; warm transfer with a briefing to the owner; conference a technician; callback showing the client's number; hand back to the AI; chats parked while on a call

**Source business links:** [BR-030](#br-030).

### AT-34

**Scenario:** No operator accepts in time, and simultaneous acceptance

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Cascade proceeds (next operator, then owner, then message capture with a promised callback); two simultaneous acceptances result in exactly one assignment

**Source business links:** [BR-024](#br-024), [BR-025](#br-025), [BR-026](#br-026), [BR-036](#br-036).

### AT-35

**Scenario:** Wrap-up, handling record and quality sampling

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Disposition and notes recorded; handling timestamps stored; operator minutes metered; the interaction enters the sampling queue by risk

**Source business links:** [BR-030](#br-030), [BR-033](#br-033).

### AT-36

**Scenario:** Owner reviews a human-handled interaction

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Inbox flags the interaction as handled by the EverOnn team with the operator's first name, duration, disposition and notes; recording per policy; the owner can rate it

**Source business links:** [BR-035](#br-035).

### AT-37

**Scenario:** Desk reload, network loss and a second browser tab

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> State restored within 3 seconds with no dropped call; disconnect detected within 5 seconds and handled per policy; a second session supersedes the first; telephone fallback works

**Source business links:** [BR-036](#br-036).

### AT-38

**Scenario:** Supervisor wall board, coaching and roster changes

**Phase:** P2 · **Status:** Not run

**Complete pass criteria:**

> Wall board shows queues by client; silent monitor, whisper and reassign work and are logged; roster and grant changes take effect immediately

**Source business links:** [BR-031](#br-031), [BR-032](#br-032).

### AT-39

**Scenario:** Explainability and correction

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> The owner opens a call, sees the knowledge sources, tools and rules used, flags a wrong answer, and a knowledge proposal and an evaluation case are created

**Source business links:** [BR-023](#br-023).

### AT-40

**Scenario:** Menu, web order and pay-at-pickup

**Phase:** P2 · **Status:** Not run

**Complete pass criteria:**

> A menu with combinations, sizes and modifiers is imported and published; a web order is placed with pickup time and correct tax; confirmation is received; the ticket appears on the staff screen and prints

**Source business links:** [BR-059](#br-059), [BR-061](#br-061).

### AT-41

**Scenario:** AI phone order with readback

**Phase:** P2 · **Status:** Not run

**Complete pass criteria:**

> Across scripted and real test calls including accents and noise, orders are read back and confirmed; item-level and modifier-level accuracy meet the pilot thresholds; allergy questions transfer to staff; no card number is spoken or stored

**Source business links:** [BR-060](#br-060).

### AT-42

**Scenario:** Order routing reliability

**Phase:** P2 · **Status:** Not run

**Complete pass criteria:**

> Orders are never lost or duplicated across network loss and reconnection; an order nobody accepts escalates to a call to the restaurant within the service level

**Source business links:** [BR-061](#br-061).

### AT-43

**Scenario:** Mandarin and Cantonese ordering with bilingual tickets

**Phase:** P3 · **Status:** Not run

**Complete pass criteria:**

> Test calls in each language on real menus meet the accuracy thresholds; kitchen tickets print bilingual names

**Source business links:** [BR-062](#br-062).

### AT-44

**Scenario:** Recording regime by jurisdiction

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Announcement and recording behavior match the rules table for one-party and all-party cases; refusal stops recording

**Source business links:** [BR-064](#br-064).

### AT-45

**Scenario:** Client terms and disclosures at onboarding

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> A new client cannot go live without accepting the terms; recording and AI-disclosure settings are explained and recorded; the data-processing terms are available to the client

**Source business links:** [BR-066](#br-066).

### AT-46

**Scenario:** Data export and deletion

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Complete export delivered; deletion and cryptographic erasure verified

**Source business links:** [BR-067](#br-067).

### AT-47

**Scenario:** Cross-client isolation suite

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Zero leaks across API routes, jobs and retrieval

**Source business links:** [BR-063](#br-063).

### AT-48

**Scenario:** Plan limit reached mid-month, and a toll-fraud attempt

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Overage or cap rule applied without dropping emergencies; alerts at 80% and 100%; caps and the kill switch stop abusive traffic

**Source business links:** [BR-010](#br-010), [BR-041](#br-041).

### AT-49

**Scenario:** Language-model or carrier outage during live calls, and a backup restore

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Fallback within 1.2 s or a safe flow; carrier reroute within 60 s; message captured; restore into an isolated environment within the target recovery time

**Source business links:** [BR-068](#br-068).

### AT-50

**Scenario:** Deployment during live calls

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Zero dropped calls; workers drain before restart

**Source business links:** [BR-069](#br-069).

### AT-51

**Scenario:** Load at twice the P1 design capacity

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Service levels met; per-stage latency reported; desk offers keep their p95 targets

**Source business links:** [BR-072](#br-072).

### AT-52

**Scenario:** Accessibility audit

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> WCAG 2.1 AA on dashboard, desk, widget and generated site templates

**Source business links:** [BR-074](#br-074).

### AT-53

**Scenario:** Independent penetration test

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> No open critical or high findings; client isolation and operator access are in scope

**Source business links:** [BR-073](#br-073).

### AT-54

**Scenario:** AI change blocked on regression

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> A prompt change that regresses safety or core metrics is blocked; a passing change can be canaried and rolled back instantly

**Source business links:** [BR-021](#br-021), [BR-076](#br-076).

### AT-55

**Scenario:** Published plans match enforced entitlements

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> The public plan data and the marketing pricing page are generated from the same entitlement data; a contradiction between a plan card, a comparison table and the entitlements fails the release checks

**Source business links:** [BR-043](#br-043).

### AT-56

**Scenario:** Subscription, entitlements and margin

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> A plan change reaches entitlements without a deployment; Stripe reconciliation is clean; margin per client including operator minutes is visible

**Source business links:** [BR-040](#br-040), [BR-042](#br-042).

### AT-57

**Scenario:** Inbox, dashboard and follow-up

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Calls, chats, texts and forms appear as requests with assignment and notes; the dashboard shows calls answered, jobs and recovered revenue; sequences respect consent and quiet hours

**Source business links:** [BR-037](#br-037), [BR-038](#br-038), [BR-039](#br-039).

### AT-58

**Scenario:** Administration and incident controls

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Support finds a client, replays a call and impersonates with a visible banner; kill switch and vendor failover work

**Source business links:** [BR-070](#br-070).

### AT-59

**Scenario:** API and webhooks

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> OpenAPI contract tests pass; webhook signatures, retries and replay verified; a Zapier-style trigger works

**Source business links:** [BR-071](#br-071).

### AT-60

**Scenario:** Ownership and handover

**Phase:** P1 · **Status:** Not run

**Complete pass criteria:**

> Repositories, accounts, keys and documentation are in EverOnn's control; EverOnn staff can build and deploy from the repository; software bill of materials and license report delivered

**Source business links:** [BR-075](#br-075).

## User stories and acceptance criteria

All 72 source stories are retained so a client can review the required experience in business language.

### US-001

> As a prospect, I want to see a private preview of my website within two minutes of entering my business name, so that I can judge the offer without committing.

**Complete source acceptance criteria:**

> Given a valid business name and phone, when I submit, then a private preview and draft profile are ready within 2 minutes, are not indexable, and do not show my phone number

**Business requirements:** [BR-014](#br-014), [BR-015](#br-015).

### US-002

> As an owner, I want to verify that I own the business before anything goes public, so that nobody else can publish under my name.

**Complete source acceptance criteria:**

> Given a claimed preview, when ownership is not verified, then no public site exists and no real number is attached

**Business requirements:** [BR-015](#br-015), [BR-019](#br-019).

### US-003

> As an owner, I want to connect my existing number by forwarding and have the platform confirm it works, so that calls are answered without changing my number.

**Complete source acceptance criteria:**

> Given forwarding is configured, when the platform places a test call, then the channel is marked live only after the test passes

**Business requirements:** [BR-001](#br-001), [BR-009](#br-009).

### US-004

> As an owner, I want to finish setup in a few guided steps from my phone, so that I am live within minutes.

**Complete source acceptance criteria:**

> Given the setup wizard, when I complete all steps, then my first AI-answered call happens within 15 minutes of claiming

**Business requirements:** [BR-009](#br-009), [BR-022](#br-022).

### US-005

> As an owner, I want to approve exactly what the AI knows and says before it answers a call, so that it never states something I have not approved.

**Complete source acceptance criteria:**

> Given imported knowledge, when I have not approved it, then the agent cannot go live; approval is recorded with the version

**Business requirements:** [BR-020](#br-020).

### US-006

> As an owner, I want to change my greeting, hours, escalation and pricing behavior and test it before publishing, so that I stay in control without a developer.

**Complete source acceptance criteria:**

> Given a draft change, when I test and publish it, then callers hear the new behavior; I can roll back in one click

**Business requirements:** [BR-021](#br-021), [BR-022](#br-022), [BR-076](#br-076).

### US-007

> As an owner, I want to see the questions the AI could not answer and add the answers, so that it improves every week.

**Complete source acceptance criteria:**

> Given a knowledge gap, when I answer it and approve, then the agent uses the answer on the next call

**Business requirements:** [BR-020](#br-020), [BR-023](#br-023).

### US-008

> As an owner, I want to set what EverOnn operators may and may not do for my business, so that they never promise what I would not.

**Complete source acceptance criteria:**

> Given my authority settings, when an operator attempts a restricted action, then it is blocked or sent to me for approval

**Business requirements:** [BR-029](#br-029), [BR-034](#br-034).

### US-009

> As an owner, I want to give operators my greeting, how to say my business name, and special instructions such as VIP customers, so that callers hear my business, not a generic call center.

**Complete source acceptance criteria:**

> Given my desk profile, when an operator receives my call, then my greeting, spoken name and notes are shown

**Business requirements:** [BR-027](#br-027), [BR-029](#br-029).

### US-010

> As a caller, I want to have my request understood and confirmed when I call a business at night, so that I know someone is coming.

**Complete source acceptance criteria:**

> Given an after-hours call, when I give my details, then the agent reads back my address and number and I receive a confirmation

**Business requirements:** [BR-001](#br-001), [BR-002](#br-002).

### US-011

> As a caller, I want to be told the truth and not be given invented prices, so that I can trust what I hear.

**Complete source acceptance criteria:**

> Given a price question under a never-quote policy, when I ask, then no figure is stated and a callback is offered

**Business requirements:** [BR-004](#br-004).

### US-012

> As a caller, I want to talk in Spanish, so that I can be helped in my language.

**Complete source acceptance criteria:**

> Given a Spanish-speaking caller, when the call starts or switches, then the agent responds in Spanish

**Business requirements:** [BR-006](#br-006).

### US-013

> As a caller, I want to be advised to call emergency services and reach a person immediately in an emergency, so that I am safe.

**Complete source acceptance criteria:**

> Given an emergency phrase, when detected, then advice is given and a person is connected with the highest priority

**Business requirements:** [BR-005](#br-005).

### US-014

> As a caller, I want to speak naturally and interrupt without long silences, so that the call feels like talking to a person.

**Complete source acceptance criteria:**

> Given a live call, when I interrupt, then the agent stops within 200 ms; response gap is under 1.8 s at p95

**Business requirements:** [BR-003](#br-003).

### US-015

> As an owner, I want to receive a text summary within 30 seconds of every call, so that I can act while I am on a job.

**Complete source acceptance criteria:**

> Given a finished call, then the summary arrives within 30 seconds with who, what, where, urgency and a link

**Business requirements:** [BR-007](#br-007).

### US-016

> As an owner, I want to have the AI book appointments into my calendar, so that jobs are scheduled without me.

**Complete source acceptance criteria:**

> Given availability rules, when a caller accepts a slot, then it is booked once and confirmed

**Business requirements:** [BR-008](#br-008).

### US-017

> As a website visitor, I want to chat with the business at any hour and send a photo, so that I get help without calling.

**Complete source acceptance criteria:**

> Given the site widget, when I chat and upload a photo, then a structured request is created and the owner is notified

**Business requirements:** [BR-011](#br-011), [BR-013](#br-013).

### US-018

> As a customer, I want to text the business and stop messages by replying STOP, so that I control what I receive.

**Complete source acceptance criteria:**

> Given consent is on record, when I reply STOP, then no further messages are sent

**Business requirements:** [BR-012](#br-012).

### US-019

> As an owner, I want to have missed calls followed by an automatic text, so that callers who hung up still reach me.

**Complete source acceptance criteria:**

> Given an abandoned call and valid consent, then a text is sent inviting the caller to continue

**Business requirements:** [BR-012](#br-012).

### US-020

> As a caller, I want to reach a person whenever I ask, or be guaranteed a callback, so that I am never trapped with an automated system.

**Complete source acceptance criteria:**

> Given I say "let me talk to a person", when an operator is available, then I am connected; otherwise a callback is scheduled within one turn

**Business requirements:** [BR-024](#br-024).

### US-021

> As an operator, I want to see the client name in large type, the line dialed, the exact greeting to say, the caller, why the call reached me and what the AI captured, the moment the call rings, so that I greet the caller in the right client's name and carry on where the AI left off.

**Complete source acceptance criteria:**

> Given an escalation for Acme Locksmith, when the offer rings, then within 500 ms the offer card shows Acme Locksmith, the line label, the greeting text, the caller, the trigger and the captured details

**Business requirements:** [BR-026](#br-026), [BR-027](#br-027).

### US-022

> As an operator, I want to be warned when the line cannot be identified, so that I never greet a caller as the wrong business.

**Complete source acceptance criteria:**

> Given an unresolved line, then the desk shows UNKNOWN LINE with no client data and only a neutral greeting

**Business requirements:** [BR-027](#br-027), [BR-028](#br-028).

### US-023

> As an operator, I want to see only the current client's data and always see which client I am serving, so that I cannot mix clients up.

**Complete source acceptance criteria:**

> Given several open interactions, then each is labeled with its client and no panel shows two clients' data

**Business requirements:** [BR-028](#br-028), [BR-063](#br-063).

### US-024

> As an operator, I want to know what I may promise for this client, so that I stay within their rules.

**Complete source acceptance criteria:**

> Given the authority matrix, then restricted actions are disabled or request approval

**Business requirements:** [BR-029](#br-029), [BR-034](#br-034).

### US-025

> As an operator, I want to hold, transfer to the owner with a briefing, conference a technician, schedule a callback, or hand the caller back to the AI, so that I can resolve the call however it needs.

**Complete source acceptance criteria:**

> Given an active call, when I use each control, then it works and is logged

**Business requirements:** [BR-030](#br-030).

### US-026

> As an operator, I want to handle chats and texts in the same desk, each clearly labeled by client, so that I stay productive between calls.

**Complete source acceptance criteria:**

> Given a call is accepted, then open chats are parked and restored after wrap-up

**Business requirements:** [BR-028](#br-028), [BR-030](#br-030).

### US-027

> As an operator, I want to finish each interaction with a quick wrap-up, so that the client gets a clear record.

**Complete source acceptance criteria:**

> Given an ended interaction, when I submit disposition and notes, then the request is updated and the owner is notified

**Business requirements:** [BR-030](#br-030), [BR-033](#br-033).

### US-028

> As an operator lead, I want to see queues by client and monitor, whisper to and reassign operators, so that service levels hold and quality improves.

**Complete source acceptance criteria:**

> Given the wall board, then queues, waits and operators are visible by client; monitoring actions are logged

**Business requirements:** [BR-031](#br-031), [BR-032](#br-032).

### US-029

> As an operator lead, I want to grant, change and revoke operators' access to clients, so that only trained operators handle each client.

**Complete source acceptance criteria:**

> Given a revoked grant, then the operator loses access within 5 seconds

**Business requirements:** [BR-028](#br-028), [BR-032](#br-032).

### US-030

> As an owner, I want to see which interactions were handled by the EverOnn team, by whom, and what they noted, so that I can verify the service.

**Complete source acceptance criteria:**

> Given a human-handled call, then my inbox flags it with the operator's first name, duration, disposition and notes

**Business requirements:** [BR-035](#br-035).

### US-031

> As an owner, I want to choose who is called first, who next and when EverOnn operators join, so that escalation matches how my business works.

**Complete source acceptance criteria:**

> Given my escalation settings, then the cascade runs in that order and emergencies alert until acknowledged

**Business requirements:** [BR-005](#br-005), [BR-025](#br-025).

### US-032

> As an owner, I want to approve sensitive actions such as sending a price, so that nothing binding is promised without me.

**Complete source acceptance criteria:**

> Given a restricted action, when requested, then I receive an approval request and the result flows to the operator

**Business requirements:** [BR-034](#br-034).

### US-033

> As a quality reviewer, I want to review sampled interactions, including whether the right greeting was used, so that quality and correctness stay high.

**Complete source acceptance criteria:**

> Given the sampling queue, then interactions appear by risk and my scores are recorded

**Business requirements:** [BR-033](#br-033).

### US-034

> As an operator, I want to keep working through a page reload or brief network drop, so that no caller is lost.

**Complete source acceptance criteria:**

> Given a reload, then the desk restores state within 3 seconds and the call continues

**Business requirements:** [BR-036](#br-036).

### US-035

> As a staff member, I want to work one inbox of calls, chats, texts and forms, so that nothing falls through the cracks.

**Complete source acceptance criteria:**

> Given new interactions, then each appears as a request with assignment, notes and status

**Business requirements:** [BR-037](#br-037).

### US-036

> As an owner, I want to have reminders, text-back sequences and review requests sent automatically, so that customers come back and I get reviews.

**Complete source acceptance criteria:**

> Given a sequence, then messages respect consent and quiet hours

**Business requirements:** [BR-038](#br-038).

### US-037

> As an owner, I want to see calls answered, jobs captured and estimated recovered revenue, so that I know EverOnn is paying for itself.

**Complete source acceptance criteria:**

> Given the dashboard, then figures and a weekly digest are shown

**Business requirements:** [BR-039](#br-039).

### US-038

> As an owner, I want to edit my website easily and use my own domain, so that it looks like my business.

**Complete source acceptance criteria:**

> Given the editor, when I publish, then the site updates; my domain gets a certificate automatically

**Business requirements:** [BR-016](#br-016), [BR-017](#br-017).

### US-039

> As an EverOnn product owner, I want to generate 1,000 websites per day without publishing fake or impersonating sites, so that growth is safe.

**Complete source acceptance criteria:**

> Given a bulk run, then throughput is met and prohibited or impersonating sites are blocked

**Business requirements:** [BR-018](#br-018), [BR-019](#br-019).

### US-040

> As an owner, I want to have chat, click-to-call and forms on my site by default, so that visitors can always reach me.

**Complete source acceptance criteria:**

> Given a published site, then the widget, call button and form are present

**Business requirements:** [BR-013](#br-013).

### US-041

> As an owner, I want to choose a plan and pay securely, and see my usage and alerts, so that there are no billing surprises.

**Complete source acceptance criteria:**

> Given a plan, then usage meters and 80% and 100% alerts are visible; emergencies are never blocked at limits

**Business requirements:** [BR-040](#br-040), [BR-041](#br-041).

### US-042

> As a prospect, I want to see plan prices and contents that are accurate and consistent everywhere I look, so that I can trust what I am buying.

**Complete source acceptance criteria:**

> Given the pricing page, then plan cards, comparison table and checkout show the same contents, generated from one source

**Business requirements:** [BR-040](#br-040), [BR-043](#br-043).

### US-043

> As an EverOnn finance, I want to see cost and margin per client, plan and vendor, including operator minutes, so that we keep healthy margins.

**Complete source acceptance criteria:**

> Given the cost dashboard, then per-client margin is shown and circuit breakers are configured

**Business requirements:** [BR-010](#br-010), [BR-042](#br-042).

### US-044

> As a support agent, I want to find a client, replay a call and see why the AI said something, so that I can resolve issues quickly.

**Complete source acceptance criteria:**

> Given a client, then I can replay and view sources, tools and rules; impersonation shows a banner

**Business requirements:** [BR-023](#br-023), [BR-070](#br-070).

### US-045

> As a platform admin, I want to switch off a capability or a vendor instantly and fail over, so that an outage does not stop calls.

**Complete source acceptance criteria:**

> Given a vendor outage, then failover happens and calls complete or capture safely

**Business requirements:** [BR-068](#br-068), [BR-070](#br-070).

### US-046

> As a product owner, I want to release prompt and policy changes safely with automatic checks, so that quality never regresses.

**Complete source acceptance criteria:**

> Given a change, then it must pass the evaluation gate and can be rolled back instantly

**Business requirements:** [BR-076](#br-076).

### US-047

> As an owner, I want to read and accept plain terms that say what EverOnn does and what my business remains responsible for, so that I understand my obligations before I go live.

**Complete source acceptance criteria:**

> Given onboarding, when I have not accepted the terms, then I cannot go live; recording and AI-disclosure choices are explained and recorded

**Business requirements:** [BR-066](#br-066).

### US-048

> As an owner, I want to export or delete my data, so that I control my information.

**Complete source acceptance criteria:**

> Given a request, then a complete export or verified deletion is delivered on time

**Business requirements:** [BR-067](#br-067).

### US-049

> As an EverOnn product owner, I want to have consent, recording and disclosure rules enforced automatically, so that we stay compliant.

**Complete source acceptance criteria:**

> Given jurisdiction rules, then announcements, consent and sending guards behave accordingly

**Business requirements:** [BR-012](#br-012), [BR-064](#br-064).

### US-050

> As an EverOnn product owner, I want to guarantee that no client can see or affect another client's data, verified by an independent test, so that trust is protected.

**Complete source acceptance criteria:**

> Given the isolation suite and penetration test, then there are no leaks and no open high findings

**Business requirements:** [BR-063](#br-063), [BR-073](#br-073).

### US-051

> As a partner developer, I want to use an API and webhooks, so that I can connect other tools.

**Complete source acceptance criteria:**

> Given API keys, then documented endpoints and signed webhooks work

**Business requirements:** [BR-071](#br-071).

### US-052

> As an EverOnn product owner, I want to grow to 1,000 and then 10,000 clients by adding capacity, with releases that never drop calls, so that growth does not need a rebuild.

**Complete source acceptance criteria:**

> Given load and deployment tests, then service levels hold and no calls drop

**Business requirements:** [BR-069](#br-069), [BR-072](#br-072).

### US-053

> As an user of any EverOnn screen, I want to use an accessible interface, so that everyone can use it.

**Complete source acceptance criteria:**

> Given an audit, then WCAG 2.1 AA is met

**Business requirements:** [BR-074](#br-074).

### US-054

> As an EverOnn owner, I want to own all code, data, prompts and accounts, so that I am never locked in.

**Complete source acceptance criteria:**

> Given handover, then EverOnn staff can build and deploy from EverOnn-owned repositories and accounts

**Business requirements:** [BR-075](#br-075).

### US-055

> As an EverOnn product owner, I want to launch a new industry from a configuration bundle after a readiness review, so that we can grow quickly without risking quality or compliance.

**Complete source acceptance criteria:**

> Given a new pack, when the readiness checklist is approved, then the industry goes live without platform code changes; an incomplete checklist blocks it

**Business requirements:** [BR-046](#br-046), [BR-047](#br-047).

### US-056

> As an EverOnn owner, I want to present each vertical as its own brand with its own name, site and legal identity, all on one platform, so that each audience sees a solution made for it and we run one business.

**Complete source acceptance criteria:**

> Given two brands, then each shows its own identity and pricing, and every legal page names EverOnn as the contracting entity

**Business requirements:** [BR-044](#br-044), [BR-045](#br-045).

### US-057

> As a client owner, I want to receive a dashboard, emails and texts under my industry's brand, so that the service feels made for my business.

**Complete source acceptance criteria:**

> Given my brand, then all client-facing surfaces use its name, theme and sender identity and never expose another brand

**Business requirements:** [BR-045](#br-045).

### US-058

> As an owner switching from another provider, I want to keep the capabilities my current provider gave me, so that I lose nothing by moving.

**Complete source acceptance criteria:**

> Given my industry's parity list, then each capability is present, embedded or connected before I go live

**Business requirements:** [BR-048](#br-048).

### US-059

> As an owner, I want to have EverOnn connect to the software I already use, and still work well if it cannot, so that my daily tools keep working.

**Complete source acceptance criteria:**

> Given a supported system, when I connect it, then data syncs and health is visible; without it the front desk still captures and notifies

**Business requirements:** [BR-049](#br-049).

### US-060

> As an EverOnn compliance lead, I want to run regulated industries under enforced compliance profiles, so that we handle patient, legal, tax and insurance conversations safely.

**Complete source acceptance criteria:**

> Given a regulated pack, then disclosures, data handling, subprocessors and advice limits are enforced and a pack that cannot meet them cannot go live

**Business requirements:** [BR-047](#br-047), [BR-065](#br-065).

### US-061

> As an acquisition manager, I want to add any competitor as a target with its signatures, sources, pricing, features, contract notes and migration playbook, so that the same process works against any provider.

**Complete source acceptance criteria:**

> Given a new target, then prospects can be imported and the playbook is selected automatically

**Business requirements:** [BR-050](#br-050).

### US-062

> As an acquisition analyst, I want to import prospects with their source, date and evidence and see unknowns as unknown, so that we never treat a detection as a confirmed customer.

**Complete source acceptance criteria:**

> Given an import, then duplicates merge, provenance is stored, and unverified facts show as unknown

**Business requirements:** [BR-051](#br-051), [BR-052](#br-052).

### US-063

> As a salesperson, I want to send compliant outreach that respects opt-outs across every brand, so that we protect prospects and the company.

**Complete source acceptance criteria:**

> Given an opt-out on any brand, then no brand contacts that person again; blocked channels stay blocked without consent

**Business requirements:** [BR-053](#br-053).

### US-064

> As a salesperson, I want to show a prospect a private preview and a demonstration built from their own business, so that they can judge the offer before committing.

**Complete source acceptance criteria:**

> Given a prospect, then a private, non-indexed preview and a demo agent are ready and nothing is published or dialed without approval or consent

**Business requirements:** [BR-054](#br-054).

### US-065

> As a salesperson, I want to show an honest all-in comparison of what the prospect pays now and would pay with EverOnn, so that the prospect can trust the numbers.

**Complete source acceptance criteria:**

> Given confirmed inputs, then the comparison includes contract term, termination fee, retained services and break-even; estimates are labeled

**Business requirements:** [BR-055](#br-055), [BR-057](#br-057).

### US-066

> As a prospect owner, I want to switch providers without losing calls, email or my website's search visibility, so that my business is not disrupted.

**Complete source acceptance criteria:**

> Given a cut-over, then calls and forms keep working, email continues, redirects are in place and rollback is available

**Business requirements:** [BR-056](#br-056).

### US-067

> As a migration specialist, I want to follow a checklist that verifies domain ownership, email continuity, phone forwarding and rollback, so that every switch is safe.

**Complete source acceptance criteria:**

> Given a migration project, then each asset is inventoried and checked and cut-over is blocked until checks pass

**Business requirements:** [BR-056](#br-056), [BR-057](#br-057).

### US-068

> As an acquisition manager, I want to see funnel, cost, time to switch, savings and retention by target and vertical, so that we invest in what works.

**Complete source acceptance criteria:**

> Given the analytics, then figures are shown by target, vertical, brand and channel

**Business requirements:** [BR-058](#br-058).

### US-069

> As a restaurant owner, I want to let customers order for pickup online from my real menu, so that I keep my sales without a percentage fee.

**Complete source acceptance criteria:**

> Given my menu, when a customer orders, then tax, pickup time and payment work and the ticket reaches my kitchen

**Business requirements:** [BR-059](#br-059), [BR-061](#br-061).

### US-070

> As a restaurant owner, I want to have phone orders read back accurately and sent to my kitchen, so that I can serve callers during the rush.

**Complete source acceptance criteria:**

> Given a phone order, then the AI reads back the whole order, gets confirmation and the ticket arrives; allergy questions go to staff

**Business requirements:** [BR-060](#br-060), [BR-061](#br-061).

### US-071

> As a restaurant staff member, I want to accept orders on a screen, print bilingual tickets and be alerted to unaccepted orders, so that no order is missed.

**Complete source acceptance criteria:**

> Given a new order, then an alert sounds, I can accept with a prep time, and a ticket prints

**Business requirements:** [BR-061](#br-061), [BR-062](#br-062).

### US-072

> As a restaurant owner, I want to be able to take orders in the languages my customers use, so that no customer is turned away.

**Complete source acceptance criteria:**

> Given tested languages, then orders in those languages meet accuracy thresholds

**Business requirements:** [BR-062](#br-062).

## Source and maintenance record

| Source document | Version / date |
| --- | --- |
| EverOnn-Business-Requirements-Document.docx | 1.0 / 26 September 2026 |
| EverOnn-Platform-BRD-and-Technical-Specification.docx | 1.0 / 26 September 2026 |

Source engineering wording, phase and priority are retained. Supporting-task breakdown, plain-language labels, suggested roles, verification prompts and sequencing are delivery guidance. Resolve source ambiguities through recorded decisions; do not shorten away conditions or claim approvals from this plan.

When a card changes: update its diagram column, table status and delivery record; link the evidence and approver; update applicable acceptance-test results; record the production release separately. When source scope changes: update the exact requirement, business mapping, phase gates, architecture and data flow together.

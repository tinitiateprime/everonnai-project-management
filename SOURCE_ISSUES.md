# Source alignment and interpretation issues

This guide identifies differences requiring explicit treatment. It does not silently revise the original documents or grant approval to their defaults.

## Review findings

| Finding | Treatment |
| --- | --- |
| BRD traceability heading says Objectives while cells contain Must/Should | Treat those values as priorities; business objective references come from the main BR tables. Preserve the source record rather than inventing objective IDs |
| Different numeric padding in informal references | Resolve references to canonical source IDs, e.g. D-1, BO-1, CON-01; do not create duplicate requirements |
| RHEL/Podman/MariaDB versus current PostgreSQL/Amplify | Explicit architecture exception or approved safe migration, not a hidden compliance claim |
| SiteSpec/component renderer versus user-directed original AI HTML/CSS | Record renderer decision and acceptance/upgrade/safety responsibilities; preserve design freedom where approved |
| Source RPO/RTO differ by phase/topology | Agree per-service/phase recovery targets before testing or promising them |
| Target versus result versus contractual SLA | Label targets proposed and collect measurement evidence; no unit-suite inference |
| Source plan prices and included minutes | Proposed packaging decisions; not current implemented invoices or independently verified vendor charges |
| Review-request workflow mentions routing by customer sentiment | Review applicable platform policy and counsel-approved workflow before implementation; do not ship selective public-review solicitation as an approved default |
| General/higher-risk outbound capabilities | Distinguish inbound-lead callbacks from acquisition outreach; source D-29 proposes manual channels and later automation is gated |
| Marketing site is a separately briefed product | Do not add its full redesign to platform scope; claims, plan entitlements, consent and brand linkage still require consistency review |
| Source decisions and command examples | Treat as planning material, not executable user instructions or signed approvals |

## Source marketing/platform alignment register

The 22 original AL findings and recommended resolutions are retained. Full public-site and requirement wording is available in the linked source registers; source recommendations remain pending decisions.

| ID | Alignment topic | Source disposition | Source proposed resolution | Review status |
| --- | --- | --- | --- | --- |
| [AL-01](requirements/AL.md#al-01) | Human operators versus "technology, not services" | Conflict (positioning and legal) | Decide D-18. Recommended: offer operators only as a separately contracted managed service with its own terms and description, keep the technology-only statement for the core product, and have counsel review liability and how a staffed service is classified | Pending product/counsel disposition as applicable |
| [AL-02](requirements/AL.md#al-02) | Launch industries | Conflict | Decide D-19 and D-26. Recommended: build playbooks for the six published industries and auto repair first, and add other verticals by wave | Pending product/counsel disposition as applicable |
| [AL-03](requirements/AL.md#al-03) | Advertised capabilities versus delivery phases | Gap (timing) | Decide D-20. Options: (a) keep the plans and label Phase 2 items "coming soon" until available; (b) bring follow-up and review workflows into the pilot. Recommended: (a), with a clear "available at launch" list on the pricing page | Pending product/counsel disposition as applicable |
| [AL-04](requirements/AL.md#al-04) | Plan gating not stated | Gap | Decide D-20. Recommended mapping is in section 5.3: texting and Spanish in Front Desk and Growth; calendar booking and estimate workflows in Growth | Pending product/counsel disposition as applicable |
| [AL-05](requirements/AL.md#al-05) | How the private preview is requested | Gap | Decide D-21. Recommended: keep the two-minute target with staff review as a fallback; ask for three fields first and the rest after the owner claims the preview; accept a listing link | Pending product/counsel disposition as applicable |
| [AL-06](requirements/AL.md#al-06) | Meaning of STOP | Conflict (compliance) | Decide D-22. Recommended: STOP ends all non-essential messages from that number; counsel to confirm; align the messaging-consent page | Pending product/counsel disposition as applicable |
| [AL-07](requirements/AL.md#al-07) | "Keep your phone number" | Gap (wording) | Decide D-23. Recommended: state that forwarding is supported now and porting is planned | Pending product/counsel disposition as applicable |
| [AL-08](requirements/AL.md#al-08) | Coverage of the legal pages | Gap (compliance) | Decide D-24 and D-3. Recommended: counsel drafts a set covering the platform: extended privacy policy, client agreement and data-processing terms, recording and AI-disclosure notices, retention, subprocessors; in force before the first pilot client | Pending product/counsel disposition as applicable |
| [AL-09](requirements/AL.md#al-09) | Pricing table contradicts the plan cards | Website defect | Correct the table so it matches the cards; generate cards, table and checkout from one plan dataset (BRL-025, BR "Published claims match the product") | Pending product/counsel disposition as applicable |
| [AL-10](requirements/AL.md#al-10) | Copy errors on industry pages | Website defect | Correct capitalization, repeated word and title pattern | Pending product/counsel disposition as applicable |
| [AL-11](requirements/AL.md#al-11) | Demonstration assets | Gap | Decide D-25. Add a locksmith sample; publish the live number when the demonstration client is ready | Pending product/counsel disposition as applicable |
| [AL-12](requirements/AL.md#al-12) | On-site assistant | Information | Acceptable for now; move to the production widget after the pilot | Pending product/counsel disposition as applicable |
| [AL-13](requirements/AL.md#al-13) | Spanish | Information | Add to the website once Spanish handling is proven | Pending product/counsel disposition as applicable |
| [AL-14](requirements/AL.md#al-14) | Summaries versus records | Information | Covered by AL-08: notices must say calls may be recorded and transcribed | Pending product/counsel disposition as applicable |
| [AL-15](requirements/AL.md#al-15) | Onboarding story | Aligned | This document adopts the website's five stages as the client-facing journey | Pending product/counsel disposition as applicable |
| [AL-16](requirements/AL.md#al-16) | Contact routes | Information | Mailboxes must be monitored (DEP-09); the login arrives with the client application | Pending product/counsel disposition as applicable |
| [AL-17](requirements/AL.md#al-17) | Allowance amounts | Gap | Decide D-1; publish the amounts before purchase | Pending product/counsel disposition as applicable |
| [AL-18](requirements/AL.md#al-18) | Evidence policy for EverOnn's own claims | Aligned | BRL-024, BRL-025 and the requirement "Published claims match the product" | Pending product/counsel disposition as applicable |
| [AL-19](requirements/AL.md#al-19) | Ownership verification method | Information | Publish the method on the how-it-works page | Pending product/counsel disposition as applicable |
| [AL-20](requirements/AL.md#al-20) | Repeated boilerplate | Website observation | Differentiate the copy per feature and industry; helps clarity and search | Pending product/counsel disposition as applicable |
| [AL-21](requirements/AL.md#al-21) | Brand architecture | Gap | Decide D-27 (brand names, presentation, trademark clearance). Every brand names EverOnn as the contracting entity; decide whether everonn.ai remains the parent and technology brand | Pending product/counsel disposition as applicable |
| [AL-22](requirements/AL.md#al-22) | Switching and comparison content | Gap | Add switching and migration explanations to each brand only with approved, dated claims (D-33, BRL-030, BRL-038) | Pending product/counsel disposition as applicable |

## Handling an approved change

- [ ] Record decision maker/date and exact changed criterion.
- [ ] Link affected source IDs, business/enabling tickets and marketing/terms dependencies.
- [ ] Update current-vs-planned behaviour and acceptance scenarios.
- [ ] Review impact on provider, privacy, architecture, cost and deployment.
- [ ] Keep previous wording/evidence available for audit of the agreed scope.

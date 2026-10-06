# Acceptance scenarios, QA evidence and client sign-off

This register preserves all 60 source AT scenarios. Their full business acceptance has not been evidenced in the supplied/current review records. Existing unit/browser/provider checks are narrower and are qualified in [CURRENT_STATE.md](CURRENT_STATE.md). No scenario is checked as client-accepted.

## Definition of done for a business ticket

- [ ] Client outcome and acceptance owner agreed; scope/architecture decisions resolved.
- [ ] Technical contracts and tenant/access boundaries reviewed.
- [ ] Required DB changes, UI, business mapping, backend and AI components delivered or justified as N/A.
- [ ] Meaningful tests cover success, failure, malformed input, forbidden role and tenant isolation.
- [ ] Actual provider effects have receipts; uncertain results are reconciled safely.
- [ ] AI text/audio/visual evaluation passes the agreed criteria where applicable.
- [ ] Accessibility/performance/security and operating-cost gates pass for the delivered scope.
- [ ] Staging/hosted deployment, monitoring, rollback and recovery evidence recorded.
- [ ] User-facing documentation, runbooks and owned access handed over.
- [ ] Client signs the specified released version; approved deferrals are written down.

## Evidence record format

For each test: scenario ID; ticket/source IDs; steps and expected result; tenant/role and safe test dataset; environment; app/config/prompt/provider versions; execution timestamp; actual result; sanitised evidence link; defect/deviation; reviewer; re-test result. Use an authorised evidence store for audio/customer material, not this GitHub repository.

Unit/mock success is labelled deterministic evidence. Real provider/call success includes receipts/traces. Visual review uses actual generated release screenshots. Client acceptance is a distinct dated review. Avoid unsupported marks such as Done, Production Ready or Accepted.

## Release blocking defects

| Severity | Example | Gate |
| --- | --- | --- |
| Critical | Tenant/audio/secret leak, unsafe emergency advice, unconsented required-channel use, false confirmed booking/payment, destructive data loss | Stop rollout, mitigate and re-run affected gates before release |
| High | Required business workflow unusable, transfer/fallback broken, materially incorrect billing, inaccessible key task | Block acceptance until fixed or contract scope explicitly changed |
| Medium | Recoverable workflow/visual defect with documented workaround | Client decides disposition and due date; no implicit acceptance |
| Low | Minor cosmetic/documentation issue without lost task | Track separately with review priority |

The source AI launch datasets call for 150 scenarios at launch and 500 at scale; those are separate from the 60 business AT records and from the 127 current automated tests. A safety-critical regression cannot be averaged away by a passing overall score.

## Source acceptance register



### AT-01 - Owner claims a business from a Google listing

Source: [AT-01](requirements/AT.md#at-01). Source phase: **P1**. Business requirements: [BR-014](requirements/BR.md#br-014), [BR-015](requirements/BR.md#br-015), [BR-019](requirements/BR.md#br-019), [BR-020](requirements/BR.md#br-020).

Delivery tickets: [EVN-KNW-020](modules/02-knowledge-agent-configuration/tickets/EVN-KNW-020.md), [EVN-ONB-015](modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-015.md), [EVN-WEB-014](modules/06-website-generation-hosting/tickets/EVN-WEB-014.md), [EVN-WEB-019](modules/06-website-generation-hosting/tickets/EVN-WEB-019.md).

**Required pass criteria:** Private preview and draft profile in under 2 minutes; page is not indexable; no real phone number shown; unverified claims are highlighted for the owner

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-02 - Owner verifies, approves knowledge, connects forwarding, tests and goes live

Source: [AT-02](requirements/AT.md#at-02). Source phase: **P1**. Business requirements: [BR-009](requirements/BR.md#br-009), [BR-020](requirements/BR.md#br-020), [BR-021](requirements/BR.md#br-021), [BR-022](requirements/BR.md#br-022).

Delivery tickets: [EVN-KNW-020](modules/02-knowledge-agent-configuration/tickets/EVN-KNW-020.md), [EVN-KNW-021](modules/02-knowledge-agent-configuration/tickets/EVN-KNW-021.md), [EVN-ONB-022](modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-022.md), [EVN-VOX-009](modules/04-telephone-voice-language/tickets/EVN-VOX-009.md).

**Required pass criteria:** Forwarding verified by an automated test call before the channel is live; approval recorded with the version id; test call and chat run against the draft without billing

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-03 - Custom domain connection

Source: [AT-03](requirements/AT.md#at-03). Source phase: **P1**. Business requirements: [BR-016](requirements/BR.md#br-016).

Delivery tickets: [EVN-WEB-016](modules/06-website-generation-hosting/tickets/EVN-WEB-016.md).

**Required pass criteria:** DNS verified, certificate issued automatically, site live; renewal simulated

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-04 - Search and AI-search readiness on sample generated sites

Source: [AT-04](requirements/AT.md#at-04). Source phase: **P1**. Business requirements: [BR-013](requirements/BR.md#br-013), [BR-017](requirements/BR.md#br-017).

Delivery tickets: [EVN-WEB-013](modules/06-website-generation-hosting/tickets/EVN-WEB-013.md), [EVN-WEB-017](modules/06-website-generation-hosting/tickets/EVN-WEB-017.md).

**Required pass criteria:** Structured data validates; Lighthouse mobile 90 or more on all four categories; LCP under 2.5 s; chat, click-to-call and forms present

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-05 - Bulk generation at 1,000 sites per day with bursts of 300 per hour

Source: [AT-05](requirements/AT.md#at-05). Source phase: **P2**. Business requirements: [BR-018](requirements/BR.md#br-018), [BR-019](requirements/BR.md#br-019).

Delivery tickets: [EVN-WEB-018](modules/06-website-generation-hosting/tickets/EVN-WEB-018.md), [EVN-WEB-019](modules/06-website-generation-hosting/tickets/EVN-WEB-019.md).

**Required pass criteria:** Throughput met; per-site cost tracked; prohibited categories blocked

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-06 - Two brands and two vertical packs live on one platform

Source: [AT-06](requirements/AT.md#at-06). Source phase: **P1**. Business requirements: [BR-044](requirements/BR.md#br-044), [BR-045](requirements/BR.md#br-045).

Delivery tickets: [EVN-VRT-044](modules/10-brands-vertical-packs/tickets/EVN-VRT-044.md), [EVN-VRT-045](modules/10-brands-vertical-packs/tickets/EVN-VRT-045.md).

**Required pass criteria:** Each brand shows its own name, domain, theme, emails, texts and legal pages; a client cannot see another brand; one operator can serve clients of both brands; every brand's terms name the contracting entity

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-07 - Configure a new vertical pack from the template

Source: [AT-07](requirements/AT.md#at-07). Source phase: **P1**. Business requirements: [BR-046](requirements/BR.md#br-046).

Delivery tickets: [EVN-VRT-046](modules/10-brands-vertical-packs/tickets/EVN-VRT-046.md).

**Required pass criteria:** A test vertical is created from the pack template (site, playbooks, knowledge, plans, terms) and reaches the readiness gate without platform code changes; elapsed time is recorded

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-08 - Readiness gate blocks an unready vertical

Source: [AT-08](requirements/AT.md#at-08). Source phase: **P1**. Business requirements: [BR-047](requirements/BR.md#br-047).

Delivery tickets: [EVN-VRT-047](modules/10-brands-vertical-packs/tickets/EVN-VRT-047.md).

**Required pass criteria:** Enabling a pack with an incomplete checklist is refused; approvals record who signed and the evidence; the evaluation threshold blocks a pack that fails safety cases

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-09 - Parity capabilities for the first packs

Source: [AT-09](requirements/AT.md#at-09). Source phase: **P1**. Business requirements: [BR-048](requirements/BR.md#br-048).

Delivery tickets: [EVN-VRT-048](modules/10-brands-vertical-packs/tickets/EVN-VRT-048.md).

**Required pass criteria:** Each capability on the pack's parity list is present, embedded or connected and demonstrated with test data

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-10 - Connector framework and fallback

Source: [AT-10](requirements/AT.md#at-10). Source phase: **P1**. Business requirements: [BR-049](requirements/BR.md#br-049).

Delivery tickets: [EVN-INT-049](modules/11-api-connectors-integrations/tickets/EVN-INT-049.md).

**Required pass criteria:** A test connector authenticates, syncs and reports health; with the connector disabled, the vertical still captures requests, notifies the team and books through the calendar

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-11 - Compliance profile enforcement

Source: [AT-11](requirements/AT.md#at-11). Source phase: **P2**. Business requirements: [BR-065](requirements/BR.md#br-065).

Delivery tickets: [EVN-SEC-065](modules/15-security-privacy-compliance/tickets/EVN-SEC-065.md).

**Required pass criteria:** A pack under the health-care profile cannot go live unless every provider in the call path is on the agreement-covered list; legal and insurance profiles block advice and quoting; the tax profile prevents collection of return details; profile changes are audited

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-12 - After-hours locksmith lockout call

Source: [AT-12](requirements/AT.md#at-12). Source phase: **P1**. Business requirements: [BR-001](requirements/BR.md#br-001), [BR-002](requirements/BR.md#br-002), [BR-007](requirements/BR.md#br-007).

Delivery tickets: [EVN-INB-007](modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-007.md), [EVN-VOX-001](modules/04-telephone-voice-language/tickets/EVN-VOX-001.md), [EVN-VOX-002](modules/04-telephone-voice-language/tickets/EVN-VOX-002.md).

**Required pass criteria:** Details captured with read-back; urgency classified; owner text within 30 seconds; request, transcript and audio present

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-13 - Caller-perceived response time on real phone calls

Source: [AT-13](requirements/AT.md#at-13). Source phase: **P1**. Business requirements: [BR-003](requirements/BR.md#br-003).

Delivery tickets: [EVN-VOX-003](modules/04-telephone-voice-language/tickets/EVN-VOX-003.md).

**Required pass criteria:** Across 200 real phone calls: p50 under 1.0 s and p95 under 1.8 s; barge-in stops speech within 200 ms

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-14 - Caller demands a price under a never-quote policy

Source: [AT-14](requirements/AT.md#at-14). Source phase: **P1**. Business requirements: [BR-004](requirements/BR.md#br-004).

Delivery tickets: [EVN-AIQ-004](modules/03-ai-governance-evaluation/tickets/EVN-AIQ-004.md).

**Required pass criteria:** No figure is invented; a callback or estimate is offered; a guardrail event is logged

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-15 - Prompt injection and social engineering on voice, chat and imported web content

Source: [AT-15](requirements/AT.md#at-15). Source phase: **P1**. Business requirements: [BR-004](requirements/BR.md#br-004), [BR-076](requirements/BR.md#br-076).

Delivery tickets: [EVN-AIQ-004](modules/03-ai-governance-evaluation/tickets/EVN-AIQ-004.md), [EVN-AIQ-076](modules/03-ai-governance-evaluation/tickets/EVN-AIQ-076.md).

**Required pass criteria:** Zero policy breaches across the red-team suite

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-16 - Caller reports a gas smell or medical emergency

Source: [AT-16](requirements/AT.md#at-16). Source phase: **P1**. Business requirements: [BR-005](requirements/BR.md#br-005), [BR-025](requirements/BR.md#br-025).

Delivery tickets: [EVN-HIL-025](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-025.md), [EVN-VOX-005](modules/04-telephone-voice-language/tickets/EVN-VOX-005.md).

**Required pass criteria:** Advised to call emergency services; top-priority escalation; immediate live transfer to a person; alerts repeat until acknowledged

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-17 - Caller speaks Spanish or switches mid-call

Source: [AT-17](requirements/AT.md#at-17). Source phase: **P1**. Business requirements: [BR-006](requirements/BR.md#br-006).

Delivery tickets: [EVN-VOX-006](modules/04-telephone-voice-language/tickets/EVN-VOX-006.md).

**Required pass criteria:** Agent switches language; the caller's language is recorded; a Spanish-skilled operator is routed when escalated

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-18 - Booking through the AI, including a conflicting slot

Source: [AT-18](requirements/AT.md#at-18). Source phase: **P1**. Business requirements: [BR-008](requirements/BR.md#br-008).

Delivery tickets: [EVN-INB-008](modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-008.md).

**Required pass criteria:** Appointment created and confirmed by text; a concurrent booking of the same slot is rejected and alternatives are offered

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-19 - Website chat with photo upload and lead capture

Source: [AT-19](requirements/AT.md#at-19). Source phase: **P1**. Business requirements: [BR-011](requirements/BR.md#br-011), [BR-013](requirements/BR.md#br-013).

Delivery tickets: [EVN-CHT-011](modules/05-chat-widget-sms/tickets/EVN-CHT-011.md), [EVN-WEB-013](modules/06-website-generation-hosting/tickets/EVN-WEB-013.md).

**Required pass criteria:** Structured request created; consent recorded; owner notified; widget under 40 KB

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-20 - Missed-call text-back and STOP

Source: [AT-20](requirements/AT.md#at-20). Source phase: **P1**. Business requirements: [BR-012](requirements/BR.md#br-012).

Delivery tickets: [EVN-CHT-012](modules/05-chat-widget-sms/tickets/EVN-CHT-012.md).

**Required pass criteria:** Text-back sent only with consent; STOP ends all non-essential messages from the number; consent ledger updated; fail-closed guard verified

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-21 - Add a competitor target without code

Source: [AT-21](requirements/AT.md#at-21). Source phase: **P1**. Business requirements: [BR-050](requirements/BR.md#br-050).

Delivery tickets: [EVN-ACQ-050](modules/12-customer-acquisition-claims/tickets/EVN-ACQ-050.md).

**Required pass criteria:** A new target with signatures, sources, a dated pricing snapshot, feature checklist, contract notes and playbook is created and used to import prospects; stale facts are flagged

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-22 - Prospect import with provenance and source-term controls

Source: [AT-22](requirements/AT.md#at-22). Source phase: **P1**. Business requirements: [BR-051](requirements/BR.md#br-051), [BR-052](requirements/BR.md#br-052).

Delivery tickets: [EVN-ACQ-051](modules/12-customer-acquisition-claims/tickets/EVN-ACQ-051.md), [EVN-ACQ-052](modules/12-customer-acquisition-claims/tickets/EVN-ACQ-052.md).

**Required pass criteria:** Records keep source, date and evidence; duplicates are merged; fields barred by source terms cannot be used for outreach; unverified facts show as unknown; the pipeline records stage, owner and next action

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-23 - Outreach guardrails

Source: [AT-23](requirements/AT.md#at-23). Source phase: **P1**. Business requirements: [BR-053](requirements/BR.md#br-053).

Delivery tickets: [EVN-ACQ-053](modules/12-customer-acquisition-claims/tickets/EVN-ACQ-053.md).

**Required pass criteria:** Emails carry the brand's sender identity, address and opt-out; an opt-out on one brand suppresses all brands; automated or AI-voice contact without a consent record is blocked; manual calls respect number type, local time and state rules

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-24 - Prospect preview and demonstration

Source: [AT-24](requirements/AT.md#at-24). Source phase: **P1**. Business requirements: [BR-054](requirements/BR.md#br-054).

Delivery tickets: [EVN-ACQ-054](modules/12-customer-acquisition-claims/tickets/EVN-ACQ-054.md).

**Required pass criteria:** A private, non-indexed preview and a demonstration agent built from the prospect's public business details are ready; nothing is published without owner approval and no call or text is placed without consent

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-25 - Savings comparison and claims file

Source: [AT-25](requirements/AT.md#at-25). Source phase: **P1**. Business requirements: [BR-043](requirements/BR.md#br-043), [BR-055](requirements/BR.md#br-055), [BR-057](requirements/BR.md#br-057).

Delivery tickets: [EVN-ACQ-055](modules/12-customer-acquisition-claims/tickets/EVN-ACQ-055.md), [EVN-BIL-043](modules/09-plans-billing-usage-margin/tickets/EVN-BIL-043.md), [EVN-MIG-057](modules/13-customer-migration-offboarding/tickets/EVN-MIG-057.md).

**Required pass criteria:** The calculator shows current cost, contract and termination fees, retained services and break-even; unconfirmed inputs are labeled; a claim cannot be used until approved and unexpired

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-26 - End-to-end migration without service loss

Source: [AT-26](requirements/AT.md#at-26). Source phase: **P1**. Business requirements: [BR-056](requirements/BR.md#br-056), [BR-057](requirements/BR.md#br-057).

Delivery tickets: [EVN-MIG-056](modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md), [EVN-MIG-057](modules/13-customer-migration-offboarding/tickets/EVN-MIG-057.md).

**Required pass criteria:** Content is imported and reviewed; domain ownership is verified and the domain transferred or repointed; email continues; forwarded numbers are verified; a parallel run and cut-over happen; rollback is exercised; no calls or form leads are lost during cut-over

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-27 - Acquisition analytics

Source: [AT-27](requirements/AT.md#at-27). Source phase: **P2**. Business requirements: [BR-058](requirements/BR.md#br-058).

Delivery tickets: [EVN-ANL-058](modules/16-business-value-analytics/tickets/EVN-ANL-058.md).

**Required pass criteria:** Funnel, cost per acquired client, time to switch, savings delivered and retention are reported by target, vertical, brand and channel

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-28 - Caller says "let me talk to a person"

Source: [AT-28](requirements/AT.md#at-28). Source phase: **P1**. Business requirements: [BR-024](requirements/BR.md#br-024).

Delivery tickets: [EVN-HIL-024](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md).

**Required pass criteria:** Live transfer to an available human, or a promise and a scheduled callback within one turn; the caller is never trapped

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-29 - Multi-client screen-pop: three different clients' escalations in sequence

Source: [AT-29](requirements/AT.md#at-29). Source phase: **P1**. Business requirements: [BR-026](requirements/BR.md#br-026), [BR-027](requirements/BR.md#br-027).

Delivery tickets: [EVN-HIL-026](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-026.md), [EVN-HIL-027](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md).

**Required pass criteria:** For each: client name, line label, greeting, caller, reason and captured details appear within 500 ms (p95); the operator greets in the right client's name; the operator hears the private announcement and the caller does not

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-30 - Call arrives on a line that cannot be resolved

Source: [AT-30](requirements/AT.md#at-30). Source phase: **P1**. Business requirements: [BR-027](requirements/BR.md#br-027), [BR-028](requirements/BR.md#br-028).

Delivery tickets: [EVN-HIL-027](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md), [EVN-HIL-028](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md).

**Required pass criteria:** Desk shows UNKNOWN LINE, no client data and only the neutral greeting; a support incident is opened; the router did not guess

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-31 - Operator attempts an action outside the client's authority

Source: [AT-31](requirements/AT.md#at-31). Source phase: **P1**. Business requirements: [BR-029](requirements/BR.md#br-029), [BR-034](requirements/BR.md#br-034).

Delivery tickets: [EVN-HIL-029](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-029.md), [EVN-HIL-034](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-034.md).

**Required pass criteria:** Control disabled or approval requested; the server rejects a direct command; the owner's decision flows back to the desk

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-32 - Client isolation on the desk

Source: [AT-32](requirements/AT.md#at-32). Source phase: **P1**. Business requirements: [BR-028](requirements/BR.md#br-028), [BR-063](requirements/BR.md#br-063).

Delivery tickets: [EVN-HIL-028](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md), [EVN-SEC-063](modules/15-security-privacy-compliance/tickets/EVN-SEC-063.md).

**Required pass criteria:** An operator without a grant sees nothing for that client; simultaneous chats are separately labeled; attaching data across clients is rejected; a revoked grant removes access within 5 seconds; the wrong-client control logs and re-routes

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-33 - Operator call and chat controls

Source: [AT-33](requirements/AT.md#at-33). Source phase: **P1**. Business requirements: [BR-030](requirements/BR.md#br-030).

Delivery tickets: [EVN-HIL-030](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md).

**Required pass criteria:** Hold with the client's audio; warm transfer with a briefing to the owner; conference a technician; callback showing the client's number; hand back to the AI; chats parked while on a call

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-34 - No operator accepts in time, and simultaneous acceptance

Source: [AT-34](requirements/AT.md#at-34). Source phase: **P1**. Business requirements: [BR-024](requirements/BR.md#br-024), [BR-025](requirements/BR.md#br-025), [BR-026](requirements/BR.md#br-026), [BR-036](requirements/BR.md#br-036).

Delivery tickets: [EVN-HIL-024](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md), [EVN-HIL-025](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-025.md), [EVN-HIL-026](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-026.md), [EVN-HIL-036](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-036.md).

**Required pass criteria:** Cascade proceeds (next operator, then owner, then message capture with a promised callback); two simultaneous acceptances result in exactly one assignment

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-35 - Wrap-up, handling record and quality sampling

Source: [AT-35](requirements/AT.md#at-35). Source phase: **P1**. Business requirements: [BR-030](requirements/BR.md#br-030), [BR-033](requirements/BR.md#br-033).

Delivery tickets: [EVN-HIL-030](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md), [EVN-HIL-033](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-033.md).

**Required pass criteria:** Disposition and notes recorded; handling timestamps stored; operator minutes metered; the interaction enters the sampling queue by risk

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-36 - Owner reviews a human-handled interaction

Source: [AT-36](requirements/AT.md#at-36). Source phase: **P1**. Business requirements: [BR-035](requirements/BR.md#br-035).

Delivery tickets: [EVN-INB-035](modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-035.md).

**Required pass criteria:** Inbox flags the interaction as handled by the EverOnn team with the operator's first name, duration, disposition and notes; recording per policy; the owner can rate it

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-37 - Desk reload, network loss and a second browser tab

Source: [AT-37](requirements/AT.md#at-37). Source phase: **P1**. Business requirements: [BR-036](requirements/BR.md#br-036).

Delivery tickets: [EVN-HIL-036](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-036.md).

**Required pass criteria:** State restored within 3 seconds with no dropped call; disconnect detected within 5 seconds and handled per policy; a second session supersedes the first; telephone fallback works

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-38 - Supervisor wall board, coaching and roster changes

Source: [AT-38](requirements/AT.md#at-38). Source phase: **P2**. Business requirements: [BR-031](requirements/BR.md#br-031), [BR-032](requirements/BR.md#br-032).

Delivery tickets: [EVN-HIL-031](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-031.md), [EVN-HIL-032](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-032.md).

**Required pass criteria:** Wall board shows queues by client; silent monitor, whisper and reassign work and are logged; roster and grant changes take effect immediately

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-39 - Explainability and correction

Source: [AT-39](requirements/AT.md#at-39). Source phase: **P1**. Business requirements: [BR-023](requirements/BR.md#br-023).

Delivery tickets: [EVN-KNW-023](modules/02-knowledge-agent-configuration/tickets/EVN-KNW-023.md).

**Required pass criteria:** The owner opens a call, sees the knowledge sources, tools and rules used, flags a wrong answer, and a knowledge proposal and an evaluation case are created

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-40 - Menu, web order and pay-at-pickup

Source: [AT-40](requirements/AT.md#at-40). Source phase: **P2**. Business requirements: [BR-059](requirements/BR.md#br-059), [BR-061](requirements/BR.md#br-061).

Delivery tickets: [EVN-ORD-059](modules/14-restaurant-ordering/tickets/EVN-ORD-059.md), [EVN-ORD-061](modules/14-restaurant-ordering/tickets/EVN-ORD-061.md).

**Required pass criteria:** A menu with combinations, sizes and modifiers is imported and published; a web order is placed with pickup time and correct tax; confirmation is received; the ticket appears on the staff screen and prints

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-41 - AI phone order with readback

Source: [AT-41](requirements/AT.md#at-41). Source phase: **P2**. Business requirements: [BR-060](requirements/BR.md#br-060).

Delivery tickets: [EVN-ORD-060](modules/14-restaurant-ordering/tickets/EVN-ORD-060.md).

**Required pass criteria:** Across scripted and real test calls including accents and noise, orders are read back and confirmed; item-level and modifier-level accuracy meet the pilot thresholds; allergy questions transfer to staff; no card number is spoken or stored

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-42 - Order routing reliability

Source: [AT-42](requirements/AT.md#at-42). Source phase: **P2**. Business requirements: [BR-061](requirements/BR.md#br-061).

Delivery tickets: [EVN-ORD-061](modules/14-restaurant-ordering/tickets/EVN-ORD-061.md).

**Required pass criteria:** Orders are never lost or duplicated across network loss and reconnection; an order nobody accepts escalates to a call to the restaurant within the service level

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-43 - Mandarin and Cantonese ordering with bilingual tickets

Source: [AT-43](requirements/AT.md#at-43). Source phase: **P3**. Business requirements: [BR-062](requirements/BR.md#br-062).

Delivery tickets: [EVN-ORD-062](modules/14-restaurant-ordering/tickets/EVN-ORD-062.md).

**Required pass criteria:** Test calls in each language on real menus meet the accuracy thresholds; kitchen tickets print bilingual names

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-44 - Recording regime by jurisdiction

Source: [AT-44](requirements/AT.md#at-44). Source phase: **P1**. Business requirements: [BR-064](requirements/BR.md#br-064).

Delivery tickets: [EVN-SEC-064](modules/15-security-privacy-compliance/tickets/EVN-SEC-064.md).

**Required pass criteria:** Announcement and recording behavior match the rules table for one-party and all-party cases; refusal stops recording

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-45 - Client terms and disclosures at onboarding

Source: [AT-45](requirements/AT.md#at-45). Source phase: **P1**. Business requirements: [BR-066](requirements/BR.md#br-066).

Delivery tickets: [EVN-SEC-066](modules/15-security-privacy-compliance/tickets/EVN-SEC-066.md).

**Required pass criteria:** A new client cannot go live without accepting the terms; recording and AI-disclosure settings are explained and recorded; the data-processing terms are available to the client

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-46 - Data export and deletion

Source: [AT-46](requirements/AT.md#at-46). Source phase: **P1**. Business requirements: [BR-067](requirements/BR.md#br-067).

Delivery tickets: [EVN-SEC-067](modules/15-security-privacy-compliance/tickets/EVN-SEC-067.md).

**Required pass criteria:** Complete export delivered; deletion and cryptographic erasure verified

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-47 - Cross-client isolation suite

Source: [AT-47](requirements/AT.md#at-47). Source phase: **P1**. Business requirements: [BR-063](requirements/BR.md#br-063).

Delivery tickets: [EVN-SEC-063](modules/15-security-privacy-compliance/tickets/EVN-SEC-063.md).

**Required pass criteria:** Zero leaks across API routes, jobs and retrieval

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-48 - Plan limit reached mid-month, and a toll-fraud attempt

Source: [AT-48](requirements/AT.md#at-48). Source phase: **P1**. Business requirements: [BR-010](requirements/BR.md#br-010), [BR-041](requirements/BR.md#br-041).

Delivery tickets: [EVN-BIL-010](modules/09-plans-billing-usage-margin/tickets/EVN-BIL-010.md), [EVN-BIL-041](modules/09-plans-billing-usage-margin/tickets/EVN-BIL-041.md).

**Required pass criteria:** Overage or cap rule applied without dropping emergencies; alerts at 80% and 100%; caps and the kill switch stop abusive traffic

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-49 - Language-model or carrier outage during live calls, and a backup restore

Source: [AT-49](requirements/AT.md#at-49). Source phase: **P1**. Business requirements: [BR-068](requirements/BR.md#br-068).

Delivery tickets: [EVN-OPS-068](modules/18-reliability-deployment-scale/tickets/EVN-OPS-068.md).

**Required pass criteria:** Fallback within 1.2 s or a safe flow; carrier reroute within 60 s; message captured; restore into an isolated environment within the target recovery time

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-50 - Deployment during live calls

Source: [AT-50](requirements/AT.md#at-50). Source phase: **P1**. Business requirements: [BR-069](requirements/BR.md#br-069).

Delivery tickets: [EVN-OPS-069](modules/18-reliability-deployment-scale/tickets/EVN-OPS-069.md).

**Required pass criteria:** Zero dropped calls; workers drain before restart

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-51 - Load at twice the P1 design capacity

Source: [AT-51](requirements/AT.md#at-51). Source phase: **P1**. Business requirements: [BR-072](requirements/BR.md#br-072).

Delivery tickets: [EVN-OPS-072](modules/18-reliability-deployment-scale/tickets/EVN-OPS-072.md).

**Required pass criteria:** Service levels met; per-stage latency reported; desk offers keep their p95 targets

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-52 - Accessibility audit

Source: [AT-52](requirements/AT.md#at-52). Source phase: **P1**. Business requirements: [BR-074](requirements/BR.md#br-074).

Delivery tickets: [EVN-QA-074](modules/19-testing-client-acceptance/tickets/EVN-QA-074.md).

**Required pass criteria:** WCAG 2.1 AA on dashboard, desk, widget and generated site templates

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-53 - Independent penetration test

Source: [AT-53](requirements/AT.md#at-53). Source phase: **P1**. Business requirements: [BR-073](requirements/BR.md#br-073).

Delivery tickets: [EVN-SEC-073](modules/15-security-privacy-compliance/tickets/EVN-SEC-073.md).

**Required pass criteria:** No open critical or high findings; client isolation and operator access are in scope

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-54 - AI change blocked on regression

Source: [AT-54](requirements/AT.md#at-54). Source phase: **P1**. Business requirements: [BR-021](requirements/BR.md#br-021), [BR-076](requirements/BR.md#br-076).

Delivery tickets: [EVN-AIQ-076](modules/03-ai-governance-evaluation/tickets/EVN-AIQ-076.md), [EVN-KNW-021](modules/02-knowledge-agent-configuration/tickets/EVN-KNW-021.md).

**Required pass criteria:** A prompt change that regresses safety or core metrics is blocked; a passing change can be canaried and rolled back instantly

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-55 - Published plans match enforced entitlements

Source: [AT-55](requirements/AT.md#at-55). Source phase: **P1**. Business requirements: [BR-043](requirements/BR.md#br-043).

Delivery tickets: [EVN-BIL-043](modules/09-plans-billing-usage-margin/tickets/EVN-BIL-043.md).

**Required pass criteria:** The public plan data and the marketing pricing page are generated from the same entitlement data; a contradiction between a plan card, a comparison table and the entitlements fails the release checks

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-56 - Subscription, entitlements and margin

Source: [AT-56](requirements/AT.md#at-56). Source phase: **P1**. Business requirements: [BR-040](requirements/BR.md#br-040), [BR-042](requirements/BR.md#br-042).

Delivery tickets: [EVN-BIL-040](modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md), [EVN-BIL-042](modules/09-plans-billing-usage-margin/tickets/EVN-BIL-042.md).

**Required pass criteria:** A plan change reaches entitlements without a deployment; Stripe reconciliation is clean; margin per client including operator minutes is visible

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-57 - Inbox, dashboard and follow-up

Source: [AT-57](requirements/AT.md#at-57). Source phase: **P1**. Business requirements: [BR-037](requirements/BR.md#br-037), [BR-038](requirements/BR.md#br-038), [BR-039](requirements/BR.md#br-039).

Delivery tickets: [EVN-ANL-039](modules/16-business-value-analytics/tickets/EVN-ANL-039.md), [EVN-INB-037](modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-037.md), [EVN-INB-038](modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-038.md).

**Required pass criteria:** Calls, chats, texts and forms appear as requests with assignment and notes; the dashboard shows calls answered, jobs and recovered revenue; sequences respect consent and quiet hours

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-58 - Administration and incident controls

Source: [AT-58](requirements/AT.md#at-58). Source phase: **P1**. Business requirements: [BR-070](requirements/BR.md#br-070).

Delivery tickets: [EVN-ADM-070](modules/17-admin-backoffice/tickets/EVN-ADM-070.md).

**Required pass criteria:** Support finds a client, replays a call and impersonates with a visible banner; kill switch and vendor failover work

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-59 - API and webhooks

Source: [AT-59](requirements/AT.md#at-59). Source phase: **P1**. Business requirements: [BR-071](requirements/BR.md#br-071).

Delivery tickets: [EVN-INT-071](modules/11-api-connectors-integrations/tickets/EVN-INT-071.md).

**Required pass criteria:** OpenAPI contract tests pass; webhook signatures, retries and replay verified; a Zapier-style trigger works

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


### AT-60 - Ownership and handover

Source: [AT-60](requirements/AT.md#at-60). Source phase: **P1**. Business requirements: [BR-075](requirements/BR.md#br-075).

Delivery tickets: [EVN-OWN-075](modules/20-ownership-handover/tickets/EVN-OWN-075.md).

**Required pass criteria:** Repositories, accounts, keys and documentation are in EverOnn's control; EverOnn staff can build and deploy from the repository; software bill of materials and license report delivered

- [ ] Execute the complete source scenario in the agreed environment.
- [ ] Attach actual results, receipts/traces/screenshots as applicable and independent reviewer.
- [ ] Resolve defects and record client acceptance for the released version.

Current disposition: full source acceptance not evidenced; pending. The linked source register retains any wording differences between the original documents.


## Additional session-extension acceptance

### Customer project repository reader - EVN-PJM-101

- [x] Existing implementation provides role-scoped connection/read/sync, encrypted context-bound private tokens, bounded fixed-host catalog, Markdown/Mermaid/image views and filename/path search.
- [x] Deterministic/public-private fixtures, public GitHub read and scoped database verification are recorded.
- [ ] Deploy the reviewed application snapshot and verify hosted tenant/role behaviour.
- [ ] Verify an authorised real private repository without exposing its token/content.
- [ ] Client reviews the workflow; repository documents remain read-only and do not execute skills.

### Markdown client delivery pack - EVN-PJM-102

- [ ] Verify all tracked source records, ticket sections, relative links and dependency graph.
- [ ] Publish Markdown-only files to the requested GitHub repository and record the commit.
- [ ] Client connects branch `main` in Project Management and confirms usable navigation.
- [ ] Client agrees scope/owners/acceptance; documentation publication does not close product tickets.

## UAT sign-off record

| Field | Value to record |
| --- | --- |
| Release/environment | Pending |
| Agreed scope and ticket IDs | Pending |
| Tests and evidence report | Pending |
| Open defects and approved dispositions | Pending |
| Accepted/deferred business deliverables | Pending |
| Operational, support and recovery readiness | Pending |
| Client name, role, date and approval reference | Pending |

There is no signed UAT record in this review. Once approved, store a dated Markdown acceptance record referencing the actual release and update the relevant tickets; do not erase previous evidence.

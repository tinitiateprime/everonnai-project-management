# AT - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## AT-01

Assigned delivery tickets: [EVN-KNW-020](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-020.md), [EVN-ONB-015](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-015.md), [EVN-WEB-014](../modules/06-website-generation-hosting/tickets/EVN-WEB-014.md), [EVN-WEB-019](../modules/06-website-generation-hosting/tickets/EVN-WEB-019.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1833.

**Source record:** AT-01 | Owner claims a business from a Google listing | Private preview and draft profile in under 2 minutes; page is not indexable; no real phone number shown; unverified claims are highlighted for the owner | BR-014, BR-015, BR-019, BR-020 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 599.

## AT-02

Assigned delivery tickets: [EVN-KNW-020](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-020.md), [EVN-KNW-021](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-021.md), [EVN-ONB-022](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-022.md), [EVN-VOX-009](../modules/04-telephone-voice-language/tickets/EVN-VOX-009.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1834.

**Source record:** AT-02 | Owner verifies, approves knowledge, connects forwarding, tests and goes live | Forwarding verified by an automated test call before the channel is live; approval recorded with the version id; test call and chat run against the draft without billing | BR-009, BR-020, BR-022, BR-021 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 600.

## AT-03

Assigned delivery tickets: [EVN-WEB-016](../modules/06-website-generation-hosting/tickets/EVN-WEB-016.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1835.

**Source record:** AT-03 | Custom domain connection | DNS verified, certificate issued automatically, site live; renewal simulated | BR-016 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 601.

## AT-04

Assigned delivery tickets: [EVN-WEB-013](../modules/06-website-generation-hosting/tickets/EVN-WEB-013.md), [EVN-WEB-017](../modules/06-website-generation-hosting/tickets/EVN-WEB-017.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1836.

**Source record:** AT-04 | Search and AI-search readiness on sample generated sites | Structured data validates; Lighthouse mobile 90 or more on all four categories; LCP under 2.5 s; chat, click-to-call and forms present | BR-017, BR-013 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 602.

## AT-05

Assigned delivery tickets: [EVN-WEB-018](../modules/06-website-generation-hosting/tickets/EVN-WEB-018.md), [EVN-WEB-019](../modules/06-website-generation-hosting/tickets/EVN-WEB-019.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1837.

**Source record:** AT-05 | Bulk generation at 1,000 sites per day with bursts of 300 per hour | Throughput met; per-site cost tracked; prohibited categories blocked | BR-018, BR-019 | P2

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 603.

## AT-06

Assigned delivery tickets: [EVN-VRT-044](../modules/10-brands-vertical-packs/tickets/EVN-VRT-044.md), [EVN-VRT-045](../modules/10-brands-vertical-packs/tickets/EVN-VRT-045.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1840.

**Source record:** AT-06 | Two brands and two vertical packs live on one platform | Each brand shows its own name, domain, theme, emails, texts and legal pages; a client cannot see another brand; one operator can serve clients of both brands; every brand's terms name the contracting entity | BR-044, BR-045 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 606.

## AT-07

Assigned delivery tickets: [EVN-VRT-046](../modules/10-brands-vertical-packs/tickets/EVN-VRT-046.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1841.

**Source record:** AT-07 | Configure a new vertical pack from the template | A test vertical is created from the pack template (site, playbooks, knowledge, plans, terms) and reaches the readiness gate without platform code changes; elapsed time is recorded | BR-046 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 607.

## AT-08

Assigned delivery tickets: [EVN-VRT-047](../modules/10-brands-vertical-packs/tickets/EVN-VRT-047.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1842.

**Source record:** AT-08 | Readiness gate blocks an unready vertical | Enabling a pack with an incomplete checklist is refused; approvals record who signed and the evidence; the evaluation threshold blocks a pack that fails safety cases | BR-047 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 608.

## AT-09

Assigned delivery tickets: [EVN-VRT-048](../modules/10-brands-vertical-packs/tickets/EVN-VRT-048.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1843.

**Source record:** AT-09 | Parity capabilities for the first packs | Each capability on the pack's parity list is present, embedded or connected and demonstrated with test data | BR-048 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 609.

## AT-10

Assigned delivery tickets: [EVN-INT-049](../modules/11-api-connectors-integrations/tickets/EVN-INT-049.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1844.

**Source record:** AT-10 | Connector framework and fallback | A test connector authenticates, syncs and reports health; with the connector disabled, the vertical still captures requests, notifies the team and books through the calendar | BR-049 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 610.

## AT-11

Assigned delivery tickets: [EVN-SEC-065](../modules/15-security-privacy-compliance/tickets/EVN-SEC-065.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1845.

**Source record:** AT-11 | Compliance profile enforcement | A pack under the health-care profile cannot go live unless every provider in the call path is on the agreement-covered list; legal and insurance profiles block advice and quoting; the tax profile prevents collection of return details; profile changes are audited | BR-065 | P2

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 611.

## AT-12

Assigned delivery tickets: [EVN-INB-007](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-007.md), [EVN-VOX-001](../modules/04-telephone-voice-language/tickets/EVN-VOX-001.md), [EVN-VOX-002](../modules/04-telephone-voice-language/tickets/EVN-VOX-002.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1848.

**Source record:** AT-12 | After-hours locksmith lockout call | Details captured with read-back; urgency classified; owner text within 30 seconds; request, transcript and audio present | BR-001, BR-002, BR-007 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 614.

## AT-13

Assigned delivery tickets: [EVN-VOX-003](../modules/04-telephone-voice-language/tickets/EVN-VOX-003.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1849.

**Source record:** AT-13 | Caller-perceived response time on real phone calls | Across 200 real phone calls: p50 under 1.0 s and p95 under 1.8 s; barge-in stops speech within 200 ms | BR-003 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 615.

## AT-14

Assigned delivery tickets: [EVN-AIQ-004](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-004.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1850.

**Source record:** AT-14 | Caller demands a price under a never-quote policy | No figure is invented; a callback or estimate is offered; a guardrail event is logged | BR-004 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 616.

## AT-15

Assigned delivery tickets: [EVN-AIQ-004](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-004.md), [EVN-AIQ-076](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-076.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1851.

**Source record:** AT-15 | Prompt injection and social engineering on voice, chat and imported web content | Zero policy breaches across the red-team suite | BR-004, BR-076 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 617.

## AT-16

Assigned delivery tickets: [EVN-HIL-025](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-025.md), [EVN-VOX-005](../modules/04-telephone-voice-language/tickets/EVN-VOX-005.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1852.

**Source record:** AT-16 | Caller reports a gas smell or medical emergency | Advised to call emergency services; top-priority escalation; immediate live transfer to a person; alerts repeat until acknowledged | BR-005, BR-025 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 618.

## AT-17

Assigned delivery tickets: [EVN-VOX-006](../modules/04-telephone-voice-language/tickets/EVN-VOX-006.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1853.

**Source record:** AT-17 | Caller speaks Spanish or switches mid-call | Agent switches language; the caller's language is recorded; a Spanish-skilled operator is routed when escalated | BR-006 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 619.

## AT-18

Assigned delivery tickets: [EVN-INB-008](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-008.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1854.

**Source record:** AT-18 | Booking through the AI, including a conflicting slot | Appointment created and confirmed by text; a concurrent booking of the same slot is rejected and alternatives are offered | BR-008 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 620.

## AT-19

Assigned delivery tickets: [EVN-CHT-011](../modules/05-chat-widget-sms/tickets/EVN-CHT-011.md), [EVN-WEB-013](../modules/06-website-generation-hosting/tickets/EVN-WEB-013.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1855.

**Source record:** AT-19 | Website chat with photo upload and lead capture | Structured request created; consent recorded; owner notified; widget under 40 KB | BR-011, BR-013 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 621.

## AT-20

Assigned delivery tickets: [EVN-CHT-012](../modules/05-chat-widget-sms/tickets/EVN-CHT-012.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1856.

**Source record:** AT-20 | Missed-call text-back and STOP | Text-back sent only with consent; STOP ends all non-essential messages from the number; consent ledger updated; fail-closed guard verified | BR-012 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 622.

## AT-21

Assigned delivery tickets: [EVN-ACQ-050](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-050.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1859.

**Source record:** AT-21 | Add a competitor target without code | A new target with signatures, sources, a dated pricing snapshot, feature checklist, contract notes and playbook is created and used to import prospects; stale facts are flagged | BR-050 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 625.

## AT-22

Assigned delivery tickets: [EVN-ACQ-051](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-051.md), [EVN-ACQ-052](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-052.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1860.

**Source record:** AT-22 | Prospect import with provenance and source-term controls | Records keep source, date and evidence; duplicates are merged; fields barred by source terms cannot be used for outreach; unverified facts show as unknown; the pipeline records stage, owner and next action | BR-051, BR-052 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 626.

## AT-23

Assigned delivery tickets: [EVN-ACQ-053](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-053.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1861.

**Source record:** AT-23 | Outreach guardrails | Emails carry the brand's sender identity, address and opt-out; an opt-out on one brand suppresses all brands; automated or AI-voice contact without a consent record is blocked; manual calls respect number type, local time and state rules | BR-053 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 627.

## AT-24

Assigned delivery tickets: [EVN-ACQ-054](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-054.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1862.

**Source record:** AT-24 | Prospect preview and demonstration | A private, non-indexed preview and a demonstration agent built from the prospect's public business details are ready; nothing is published without owner approval and no call or text is placed without consent | BR-054 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 628.

## AT-25

Assigned delivery tickets: [EVN-ACQ-055](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-055.md), [EVN-BIL-043](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-043.md), [EVN-MIG-057](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-057.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1863.

**Source record:** AT-25 | Savings comparison and claims file | The calculator shows current cost, contract and termination fees, retained services and break-even; unconfirmed inputs are labeled; a claim cannot be used until approved and unexpired | BR-055, BR-057, BR-043 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 629.

## AT-26

Assigned delivery tickets: [EVN-MIG-056](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md), [EVN-MIG-057](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-057.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1864.

**Source record:** AT-26 | End-to-end migration without service loss | Content is imported and reviewed; domain ownership is verified and the domain transferred or repointed; email continues; forwarded numbers are verified; a parallel run and cut-over happen; rollback is exercised; no calls or form leads are lost during cut-over | BR-056, BR-057 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 630.

## AT-27

Assigned delivery tickets: [EVN-ANL-058](../modules/16-business-value-analytics/tickets/EVN-ANL-058.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1865.

**Source record:** AT-27 | Acquisition analytics | Funnel, cost per acquired client, time to switch, savings delivered and retention are reported by target, vertical, brand and channel | BR-058 | P2

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 631.

## AT-28

Assigned delivery tickets: [EVN-HIL-024](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1868.

**Source record:** AT-28 | Caller says "let me talk to a person" | Live transfer to an available human, or a promise and a scheduled callback within one turn; the caller is never trapped | BR-024 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 634.

## AT-29

Assigned delivery tickets: [EVN-HIL-026](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-026.md), [EVN-HIL-027](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1869.

**Source record:** AT-29 | Multi-client screen-pop: three different clients' escalations in sequence | For each: client name, line label, greeting, caller, reason and captured details appear within 500 ms (p95); the operator greets in the right client's name; the operator hears the private announcement and the caller does not | BR-026, BR-027 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 635.

## AT-30

Assigned delivery tickets: [EVN-HIL-027](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md), [EVN-HIL-028](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1870.

**Source record:** AT-30 | Call arrives on a line that cannot be resolved | Desk shows UNKNOWN LINE, no client data and only the neutral greeting; a support incident is opened; the router did not guess | BR-027, BR-028 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 636.

## AT-31

Assigned delivery tickets: [EVN-HIL-029](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-029.md), [EVN-HIL-034](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-034.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1871.

**Source record:** AT-31 | Operator attempts an action outside the client's authority | Control disabled or approval requested; the server rejects a direct command; the owner's decision flows back to the desk | BR-029, BR-034 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 637.

## AT-32

Assigned delivery tickets: [EVN-HIL-028](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md), [EVN-SEC-063](../modules/15-security-privacy-compliance/tickets/EVN-SEC-063.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1872.

**Source record:** AT-32 | Client isolation on the desk | An operator without a grant sees nothing for that client; simultaneous chats are separately labeled; attaching data across clients is rejected; a revoked grant removes access within 5 seconds; the wrong-client control logs and re-routes | BR-028, BR-063 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 638.

## AT-33

Assigned delivery tickets: [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1873.

**Source record:** AT-33 | Operator call and chat controls | Hold with the client's audio; warm transfer with a briefing to the owner; conference a technician; callback showing the client's number; hand back to the AI; chats parked while on a call | BR-030 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 639.

## AT-34

Assigned delivery tickets: [EVN-HIL-024](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md), [EVN-HIL-025](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-025.md), [EVN-HIL-026](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-026.md), [EVN-HIL-036](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-036.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1874.

**Source record:** AT-34 | No operator accepts in time, and simultaneous acceptance | Cascade proceeds (next operator, then owner, then message capture with a promised callback); two simultaneous acceptances result in exactly one assignment | BR-025, BR-024, BR-036, BR-026 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 640.

## AT-35

Assigned delivery tickets: [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md), [EVN-HIL-033](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-033.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1875.

**Source record:** AT-35 | Wrap-up, handling record and quality sampling | Disposition and notes recorded; handling timestamps stored; operator minutes metered; the interaction enters the sampling queue by risk | BR-033, BR-030 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 641.

## AT-36

Assigned delivery tickets: [EVN-INB-035](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-035.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1876.

**Source record:** AT-36 | Owner reviews a human-handled interaction | Inbox flags the interaction as handled by the EverOnn team with the operator's first name, duration, disposition and notes; recording per policy; the owner can rate it | BR-035 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 642.

## AT-37

Assigned delivery tickets: [EVN-HIL-036](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-036.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1877.

**Source record:** AT-37 | Desk reload, network loss and a second browser tab | State restored within 3 seconds with no dropped call; disconnect detected within 5 seconds and handled per policy; a second session supersedes the first; telephone fallback works | BR-036 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 643.

## AT-38

Assigned delivery tickets: [EVN-HIL-031](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-031.md), [EVN-HIL-032](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-032.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1878.

**Source record:** AT-38 | Supervisor wall board, coaching and roster changes | Wall board shows queues by client; silent monitor, whisper and reassign work and are logged; roster and grant changes take effect immediately | BR-031, BR-032 | P2

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 644.

## AT-39

Assigned delivery tickets: [EVN-KNW-023](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-023.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1879.

**Source record:** AT-39 | Explainability and correction | The owner opens a call, sees the knowledge sources, tools and rules used, flags a wrong answer, and a knowledge proposal and an evaluation case are created | BR-023 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 645.

## AT-40

Assigned delivery tickets: [EVN-ORD-059](../modules/14-restaurant-ordering/tickets/EVN-ORD-059.md), [EVN-ORD-061](../modules/14-restaurant-ordering/tickets/EVN-ORD-061.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1882.

**Source record:** AT-40 | Menu, web order and pay-at-pickup | A menu with combinations, sizes and modifiers is imported and published; a web order is placed with pickup time and correct tax; confirmation is received; the ticket appears on the staff screen and prints | BR-059, BR-061 | P2

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 648.

## AT-41

Assigned delivery tickets: [EVN-ORD-060](../modules/14-restaurant-ordering/tickets/EVN-ORD-060.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1883.

**Source record:** AT-41 | AI phone order with readback | Across scripted and real test calls including accents and noise, orders are read back and confirmed; item-level and modifier-level accuracy meet the pilot thresholds; allergy questions transfer to staff; no card number is spoken or stored | BR-060 | P2

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 649.

## AT-42

Assigned delivery tickets: [EVN-ORD-061](../modules/14-restaurant-ordering/tickets/EVN-ORD-061.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1884.

**Source record:** AT-42 | Order routing reliability | Orders are never lost or duplicated across network loss and reconnection; an order nobody accepts escalates to a call to the restaurant within the service level | BR-061 | P2

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 650.

## AT-43

Assigned delivery tickets: [EVN-ORD-062](../modules/14-restaurant-ordering/tickets/EVN-ORD-062.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1885.

**Source record:** AT-43 | Mandarin and Cantonese ordering with bilingual tickets | Test calls in each language on real menus meet the accuracy thresholds; kitchen tickets print bilingual names | BR-062 | P3

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 651.

## AT-44

Assigned delivery tickets: [EVN-SEC-064](../modules/15-security-privacy-compliance/tickets/EVN-SEC-064.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1888.

**Source record:** AT-44 | Recording regime by jurisdiction | Announcement and recording behavior match the rules table for one-party and all-party cases; refusal stops recording | BR-064 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 654.

## AT-45

Assigned delivery tickets: [EVN-SEC-066](../modules/15-security-privacy-compliance/tickets/EVN-SEC-066.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1889.

**Source record:** AT-45 | Client terms and disclosures at onboarding | A new client cannot go live without accepting the terms; recording and AI-disclosure settings are explained and recorded; the data-processing terms are available to the client | BR-066 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 655.

## AT-46

Assigned delivery tickets: [EVN-SEC-067](../modules/15-security-privacy-compliance/tickets/EVN-SEC-067.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1890.

**Source record:** AT-46 | Data export and deletion | Complete export delivered; deletion and cryptographic erasure verified | BR-067 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 656.

## AT-47

Assigned delivery tickets: [EVN-SEC-063](../modules/15-security-privacy-compliance/tickets/EVN-SEC-063.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1893.

**Source record:** AT-47 | Cross-client isolation suite | Zero leaks across API routes, jobs and retrieval | BR-063 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 659.

## AT-48

Assigned delivery tickets: [EVN-BIL-010](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-010.md), [EVN-BIL-041](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-041.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1894.

**Source record:** AT-48 | Plan limit reached mid-month, and a toll-fraud attempt | Overage or cap rule applied without dropping emergencies; alerts at 80% and 100%; caps and the kill switch stop abusive traffic | BR-041, BR-010 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 660.

## AT-49

Assigned delivery tickets: [EVN-OPS-068](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-068.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1895.

**Source record:** AT-49 | Language-model or carrier outage during live calls, and a backup restore | Fallback within 1.2 s or a safe flow; carrier reroute within 60 s; message captured; restore into an isolated environment within the target recovery time | BR-068 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 661.

## AT-50

Assigned delivery tickets: [EVN-OPS-069](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-069.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1896.

**Source record:** AT-50 | Deployment during live calls | Zero dropped calls; workers drain before restart | BR-069 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 662.

## AT-51

Assigned delivery tickets: [EVN-OPS-072](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-072.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1897.

**Source record:** AT-51 | Load at twice the P1 design capacity | Service levels met; per-stage latency reported; desk offers keep their p95 targets | BR-072 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 663.

## AT-52

Assigned delivery tickets: [EVN-QA-074](../modules/19-testing-client-acceptance/tickets/EVN-QA-074.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1898.

**Source record:** AT-52 | Accessibility audit | WCAG 2.1 AA on dashboard, desk, widget and generated site templates | BR-074 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 664.

## AT-53

Assigned delivery tickets: [EVN-SEC-073](../modules/15-security-privacy-compliance/tickets/EVN-SEC-073.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1899.

**Source record:** AT-53 | Independent penetration test | No open critical or high findings; client isolation and operator access are in scope | BR-073 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 665.

## AT-54

Assigned delivery tickets: [EVN-AIQ-076](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-076.md), [EVN-KNW-021](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-021.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1900.

**Source record:** AT-54 | AI change blocked on regression | A prompt change that regresses safety or core metrics is blocked; a passing change can be canaried and rolled back instantly | BR-076, BR-021 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 666.

## AT-55

Assigned delivery tickets: [EVN-BIL-043](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-043.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1901.

**Source record:** AT-55 | Published plans match enforced entitlements | The public plan data and the marketing pricing page are generated from the same entitlement data; a contradiction between a plan card, a comparison table and the entitlements fails the release checks | BR-043 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 667.

## AT-56

Assigned delivery tickets: [EVN-BIL-040](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md), [EVN-BIL-042](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-042.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1902.

**Source record:** AT-56 | Subscription, entitlements and margin | A plan change reaches entitlements without a deployment; Stripe reconciliation is clean; margin per client including operator minutes is visible | BR-040, BR-042 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 668.

## AT-57

Assigned delivery tickets: [EVN-ANL-039](../modules/16-business-value-analytics/tickets/EVN-ANL-039.md), [EVN-INB-037](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-037.md), [EVN-INB-038](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-038.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1903.

**Source record:** AT-57 | Inbox, dashboard and follow-up | Calls, chats, texts and forms appear as requests with assignment and notes; the dashboard shows calls answered, jobs and recovered revenue; sequences respect consent and quiet hours | BR-037, BR-039, BR-038 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 669.

## AT-58

Assigned delivery tickets: [EVN-ADM-070](../modules/17-admin-backoffice/tickets/EVN-ADM-070.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1904.

**Source record:** AT-58 | Administration and incident controls | Support finds a client, replays a call and impersonates with a visible banner; kill switch and vendor failover work | BR-070 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 670.

## AT-59

Assigned delivery tickets: [EVN-INT-071](../modules/11-api-connectors-integrations/tickets/EVN-INT-071.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1905.

**Source record:** AT-59 | API and webhooks | OpenAPI contract tests pass; webhook signatures, retries and replay verified; a Zapier-style trigger works | BR-071 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 671.

## AT-60

Assigned delivery tickets: [EVN-OWN-075](../modules/20-ownership-handover/tickets/EVN-OWN-075.md).

**Primary source:** TECH section 25.2 Acceptance tests; extraction row 1906.

**Source record:** AT-60 | Ownership and handover | Repositories, accounts, keys and documentation are in EverOnn's control; EverOnn staff can build and deploy from the repository; software bill of materials and license report delivered | BR-075 | P1

**Also documented:** BRD section 15.2 Acceptance tests; extraction row 672.

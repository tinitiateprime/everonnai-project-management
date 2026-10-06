# Business delivery checklist

This checklist shows what the client will receive and the next step for each deliverable. Start with the short [project overview](README.md) for the overall picture.

**Partly built:** some features exist; more work is required. **Planned:** the full deliverable is still to be built. Progress describes development, not client acceptance. No complete business deliverable has been signed off yet.

Select a deliverable to open its detailed ticket. Database, backend, AI, testing and deployment details remain there for the delivery team. The original requirements and priorities are preserved in [source traceability](TRACEABILITY.md).

## Accounts and business setup

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Verify ownership before anything is public](modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-015.md) | Partly built | Independently verify business ownership before public publishing. |
| [Test before going live](modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-022.md) | Partly built | Provide real phone/chat test journeys before activation. |

## Business knowledge and assistant settings

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Approve what the AI knows](modules/02-knowledge-agent-configuration/tickets/EVN-KNW-020.md) | Partly built | Keep approved information stable while draft edits are reviewed. |
| [Self-service configuration](modules/02-knowledge-agent-configuration/tickets/EVN-KNW-021.md) | Partly built | Complete draft, test, approval and rollback for permitted business settings. |
| [Explain and correct](modules/02-knowledge-agent-configuration/tickets/EVN-KNW-023.md) | Partly built | Show answer sources and make corrections traceable. |

## AI safety and quality

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Truthful and safe AI](modules/03-ai-governance-evaluation/tickets/EVN-AIQ-004.md) | Partly built | Complete truthful-answer, disclosure and safety checks across the assistant. |
| [Safe AI change control](modules/03-ai-governance-evaluation/tickets/EVN-AIQ-076.md) | Partly built | Check quality and safety before changing the assistant. |

## Phone calls and languages

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Answer every call](modules/04-telephone-voice-language/tickets/EVN-VOX-001.md) | Planned | Connect real business phone lines and prove answering and safe message capture. |
| [Capture the job accurately](modules/04-telephone-voice-language/tickets/EVN-VOX-002.md) | Partly built | Confirm important customer details accurately during real calls. |
| [Natural, responsive conversation](modules/04-telephone-voice-language/tickets/EVN-VOX-003.md) | Partly built | Test natural conversation, interruptions and response speed on phone calls. |
| [Emergency handling](modules/04-telephone-voice-language/tickets/EVN-VOX-005.md) | Partly built | Test emergency handling and urgent human escalation on real calls. |
| [English and Spanish](modules/04-telephone-voice-language/tickets/EVN-VOX-006.md) | Planned | Add and test English/Spanish calls and mid-call language changes. |
| [Keep existing numbers](modules/04-telephone-voice-language/tickets/EVN-VOX-009.md) | Planned | Verify forwarding and plan number transfers without disrupting service. |

## Website chat and text messages

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Website chat](modules/05-chat-widget-sms/tickets/EVN-CHT-011.md) | Partly built | Complete the external website widget and customer photo handling. |
| [Texting and text-back](modules/05-chat-widget-sms/tickets/EVN-CHT-012.md) | Planned | Add two-way texting, missed-call replies and immediate opt-out handling. |

## Website creation and publishing

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Chat, call and forms on every site](modules/06-website-generation-hosting/tickets/EVN-WEB-013.md) | Partly built | Verify forms, chat and call actions on each published site. |
| [Private preview in minutes](modules/06-website-generation-hosting/tickets/EVN-WEB-014.md) | Partly built | Make preview creation reliable and measure the agreed creation time. |
| [Custom domains](modules/06-website-generation-hosting/tickets/EVN-WEB-016.md) | Planned | Add custom-domain setup and automatic security certificates. |
| [Search and AI-search ready](modules/06-website-generation-hosting/tickets/EVN-WEB-017.md) | Partly built | Review local-search content, performance and indexing on published pages. |
| [1,000 sites per day](modules/06-website-generation-hosting/tickets/EVN-WEB-018.md) | Planned | Measure generation and hosting capacity under realistic demand. |
| [Prevent fake or abusive sites](modules/06-website-generation-hosting/tickets/EVN-WEB-019.md) | Partly built | Complete preview protections, abuse checks and site-removal procedures. |

## Human support and operator desk

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Always able to reach a human](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md) | Partly built | Complete human routing, response coverage and safe fallback. |
| [Configurable escalation rules](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-025.md) | Partly built | Allow reviewed business rules to trigger the correct escalation. |
| [Shared multi-client operator desk](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-026.md) | Planned | Build the shared operator desk and prove its staffing model. |
| [Client screen-pop and correct greeting](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md) | Planned | Show the correct business identity and greeting for each operator task. |
| [No client mix-ups](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md) | Planned | Prevent customer records and conversations from mixing between businesses. |
| [Operator authority per client](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-029.md) | Planned | Enforce what operators may do for each business. |
| [Operator call and chat controls](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md) | Planned | Add tested call-transfer, conversation and messaging controls. |
| [Supervision](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-031.md) | Planned | Provide authorised supervision and quality-review tools. |
| [Staffing and rosters](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-032.md) | Planned | Set up shifts, skills and confirmed service coverage. |
| [Human quality and audit](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-033.md) | Planned | Record human handling quality and auditable actions. |
| [Approvals for sensitive actions](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-034.md) | Partly built | Require approval before sensitive operator actions. |
| [Desk reliability](modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-036.md) | Planned | Prove safe reconnect, task assignment and recovery when the desk fails. |

## Enquiries, appointments and follow-up

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Owner summary within 30 seconds](modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-007.md) | Partly built | Prove owner summaries arrive within the agreed time after each call. |
| [Calendar booking](modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-008.md) | Partly built | Complete availability rules, confirmations and booking-change workflows. |
| [Owner sees human handling](modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-035.md) | Planned | Show owners what the operator handled and the result. |
| [Unified inbox](modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-037.md) | Partly built | Complete shared inbox assignment, notes and customer-record management. |
| [Automated follow-up](modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-038.md) | Planned | Add consent-aware follow-up, reminders and delivery tracking. |

## Subscriptions, usage and pricing

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Fraud and cost protection](modules/09-plans-billing-usage-margin/tickets/EVN-BIL-010.md) | Partly built | Enforce abuse controls, usage budgets and customer alerts. |
| [Plans and billing](modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md) | Planned | Connect paid subscriptions, invoices and account billing. |
| [Metering and limits](modules/09-plans-billing-usage-margin/tickets/EVN-BIL-041.md) | Partly built | Extend usage tracking to all required services and enforce plan limits. |
| [Cost and margin visibility](modules/09-plans-billing-usage-margin/tickets/EVN-BIL-042.md) | Partly built | Reconcile provider and operator costs with actual charges. |
| [Published claims match the product](modules/09-plans-billing-usage-margin/tickets/EVN-BIL-043.md) | Partly built | Agree plan features and ensure public claims match the delivered product. |

## Business services and brands

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [One suite, many vertical brands](modules/10-brands-vertical-packs/tickets/EVN-VRT-044.md) | Planned | Add separate service brands with reviewed default settings. |
| [Brands are kept apart](modules/10-brands-vertical-packs/tickets/EVN-VRT-045.md) | Planned | Keep each brand and its businesses correctly separated. |
| [Launch a vertical by configuration](modules/10-brands-vertical-packs/tickets/EVN-VRT-046.md) | Partly built | Make new service packs configurable and reviewed. |
| [Vertical readiness gate](modules/10-brands-vertical-packs/tickets/EVN-VRT-047.md) | Planned | Approve each service pack before launch. |
| [Match what customers already rely on](modules/10-brands-vertical-packs/tickets/EVN-VRT-048.md) | Planned | Check the tools and workflows customers need before switching. |

## Business-tool connections

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Connect the systems each vertical uses](modules/11-api-connectors-integrations/tickets/EVN-INT-049.md) | Partly built | Complete approved business-tool connections and test actual results. |
| [API and integrations](modules/11-api-connectors-integrations/tickets/EVN-INT-071.md) | Partly built | Deliver documented, secure partner APIs and integrations. |

## New-customer growth

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Target any provider's customers](modules/12-customer-acquisition-claims/tickets/EVN-ACQ-050.md) | Planned | Build the approved provider-target research process. |
| [Prospects with proof of origin](modules/12-customer-acquisition-claims/tickets/EVN-ACQ-051.md) | Planned | Record prospect sources and permission to use that information. |
| [Qualify and track every prospect](modules/12-customer-acquisition-claims/tickets/EVN-ACQ-052.md) | Planned | Track qualification, contact history and conversion stages. |
| [Compliant outreach](modules/12-customer-acquisition-claims/tickets/EVN-ACQ-053.md) | Planned | Approve outreach channels, permissions and operating rules. |
| [Build before asking](modules/12-customer-acquisition-claims/tickets/EVN-ACQ-054.md) | Partly built | Create safe prospect previews before requesting commitment. |
| [Honest savings comparison](modules/12-customer-acquisition-claims/tickets/EVN-ACQ-055.md) | Planned | Make savings comparisons accurate, dated and reviewable. |

## Customer migration

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Managed migration without service loss](modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md) | Planned | Plan and test migration without losing customer service. |
| [Respect the customer's contract and ownership](modules/13-customer-migration-offboarding/tickets/EVN-MIG-057.md) | Planned | Document permission, contract obligations and customer ownership. |

## Restaurant ordering

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Direct online ordering](modules/14-restaurant-ordering/tickets/EVN-ORD-059.md) | Planned | Build menu selection, customer checkout and order confirmation. |
| [AI phone ordering with readback](modules/14-restaurant-ordering/tickets/EVN-ORD-060.md) | Planned | Capture phone orders accurately and read them back before confirmation. |
| [Orders reach the kitchen](modules/14-restaurant-ordering/tickets/EVN-ORD-061.md) | Planned | Prove orders reach staff or the kitchen and are acknowledged. |
| [Bilingual ordering and tickets](modules/14-restaurant-ordering/tickets/EVN-ORD-062.md) | Planned | Test the required ordering languages and kitchen-ticket formatting. |

## Data protection and privacy

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Client data isolation](modules/15-security-privacy-compliance/tickets/EVN-SEC-063.md) | Partly built | Complete independent checks of business, brand and operator data separation. |
| [Consent and disclosure rules](modules/15-security-privacy-compliance/tickets/EVN-SEC-064.md) | Planned | Implement approved consent, recording, disclosure and opt-out workflows. |
| [Compliance profile for each vertical](modules/15-security-privacy-compliance/tickets/EVN-SEC-065.md) | Planned | Apply the approved privacy and operating rules for each service. |
| [Clear client terms](modules/15-security-privacy-compliance/tickets/EVN-SEC-066.md) | Planned | Complete reviewed client terms and processing agreements. |
| [Export and deletion](modules/15-security-privacy-compliance/tickets/EVN-SEC-067.md) | Planned | Provide authorised data export, retention and deletion workflows. |
| [Security assurance](modules/15-security-privacy-compliance/tickets/EVN-SEC-073.md) | Partly built | Complete security review, key management and incident evidence. |

## Business results and reports

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Proof of value](modules/16-business-value-analytics/tickets/EVN-ANL-039.md) | Partly built | Show evidence-based enquiry, booking and business-value reports. |
| [Acquisition analytics](modules/16-business-value-analytics/tickets/EVN-ANL-058.md) | Planned | Report prospect conversion and migration results. |

## Platform administration

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Back-office administration](modules/17-admin-backoffice/tickets/EVN-ADM-070.md) | Planned | Build controlled support and administration tools. |

## Service reliability and growth

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Reliability during outages](modules/18-reliability-deployment-scale/tickets/EVN-OPS-068.md) | Partly built | Prove fallback and recovery during provider and system outages. |
| [Zero-downtime releases](modules/18-reliability-deployment-scale/tickets/EVN-OPS-069.md) | Partly built | Deploy updates without disrupting active customer interactions. |
| [Scale by adding capacity](modules/18-reliability-deployment-scale/tickets/EVN-OPS-072.md) | Planned | Measure capacity and make additional infrastructure repeatable. |

## Accessibility

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [Accessibility](modules/19-testing-client-acceptance/tickets/EVN-QA-074.md) | Partly built | Review and fix keyboard, screen-reader and mobile accessibility. |

## Ownership and handover

| Business deliverable | Progress | Next step |
| --- | --- | --- |
| [EverOnn owns everything](modules/20-ownership-handover/tickets/EVN-OWN-075.md) | Partly built | Confirm account/code ownership and deliver operational handover. |

## Client review checklist

- [ ] Confirm the first service and which deliverables are included in its launch.
- [ ] Agree priorities, owners and delivery dates.
- [ ] Review demonstrations and evidence for the agreed outcomes.
- [ ] Approve the released version and record any agreed remaining work.

See [delivery stages](DELIVERY_PLAN.md) for sequence and [acceptance criteria](ACCEPTANCE.md) for the detailed checks. Customer project-document access and this checklist are additional session deliverables; their details are in [the project documentation module](modules/21-project-documentation-workbench/README.md).

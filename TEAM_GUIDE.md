# Delivery team reference

Start with [the client project overview](README.md) or [business checklist](BUSINESS_DELIVERABLES.md). This page contains the engineering navigation and the complete module directory.

The hierarchy remains project > modules > tickets: 22 modules, 102 tickets, 76 source business deliverables and 26 enabling/extension tickets. Each ticket includes technical component, DB, UI, business-to-technical mapping, backend, AI, QA and deployment details.

## Working guides

| Guide | Purpose |
| --- | --- |
| [Current state](CURRENT_STATE.md) | Existing capabilities, limits and evidence from the inspected application |
| [Delivery plan](DELIVERY_PLAN.md) | Dependencies, phases and release gates |
| [Ticket index](TICKET_INDEX.md) | All business and technical enabling tickets |
| [Technical deliverables](TECHNICAL_DELIVERABLES.md) | Implementation boundaries and current/proposed components |
| [Decisions](DECISIONS.md) | Architecture and product choices requiring approval |
| [Risks](RISKS.md) | Current gaps, mitigations and launch blockers |
| [Acceptance](ACCEPTANCE.md) | Full source test scenarios and sign-off protocol |
| [Traceability](TRACEABILITY.md) | Source requirements and assigned tickets |
| [Source registers](requirements/README.md) | Full requirement definitions and source variants |
| [Sources](SOURCES.md) | Original document provenance and review boundaries |
| [Code evidence](EVIDENCE.md) | Inspected application file fingerprints |
| [Source alignment](SOURCE_ISSUES.md) | Conflicts and interpretation decisions |
| [Session extensions](SCOPE_EXTENSIONS.md) | User-requested scope beyond the original documents |
| [Validation](VALIDATION.md) | Documentation coverage, links and dependencies |
| [Ticket template](TICKET_TEMPLATE.md) | Required ticket sections and maintenance rules |

## Engineering status rules

| Ticket label | Meaning in the client checklist |
| --- | --- |
| Partial | Partly built; remaining criteria are listed in the ticket |
| Planned | Full workflow has not been demonstrated |
| Implemented | The specific bounded slice has code/check evidence |
| Decision required | Record the applicable scope/architecture decision before committing implementation |

Keep engineering progress, QA, deployment and client acceptance separate. Checked boxes describe an evidenced slice; a full source requirement needs all its criteria and dated acceptance. Source priorities/phases remain in the detailed tickets. No new delivery dates or scope approvals are implied by the simpler client wording.

## Module directory

| Module | Code | Tickets | Current engineering labels |
| --- | --- | --- | --- |
| [00 - Foundations, scope and architecture decisions](modules/00-foundations-governance/README.md) | FND | 1 | 1 Decision required |
| [01 - Onboarding, identity and tenant lifecycle](modules/01-onboarding-tenancy-identity/README.md) | ONB | 4 | 4 Partial |
| [02 - Knowledge, agent configuration and approved business memory](modules/02-knowledge-agent-configuration/README.md) | KNW | 5 | 5 Partial |
| [03 - AI runtime, skills, provider portability and evaluation](modules/03-ai-governance-evaluation/README.md) | AIQ | 6 | 6 Partial |
| [04 - Telephone numbers, voice service and bilingual calls](modules/04-telephone-voice-language/README.md) | VOX | 7 | 4 Planned; 3 Partial |
| [05 - Customer chat, external widget and SMS](modules/05-chat-widget-sms/README.md) | CHT | 3 | 2 Partial; 1 Planned |
| [06 - AI website generation, editing, publishing and domains](modules/06-website-generation-hosting/README.md) | WEB | 9 | 6 Partial; 3 Planned |
| [07 - Human escalation and the multi-client Live Agent Desk](modules/07-human-operations-live-agent-desk/README.md) | HIL | 12 | 3 Partial; 9 Planned |
| [08 - Unified inbox, contacts, booking and follow-up](modules/08-inbox-contacts-booking-followup/README.md) | INB | 6 | 4 Partial; 2 Planned |
| [09 - Plans, subscriptions, metering, budgets and margin](modules/09-plans-billing-usage-margin/README.md) | BIL | 6 | 4 Partial; 1 Planned; 1 Implemented |
| [10 - Vertical brands, packs, readiness and capability parity](modules/10-brands-vertical-packs/README.md) | VRT | 5 | 4 Planned; 1 Partial |
| [11 - Public API, webhooks and vertical connectors](modules/11-api-connectors-integrations/README.md) | INT | 2 | 2 Partial |
| [12 - Incumbent targets, prospects, outreach and savings evidence](modules/12-customer-acquisition-claims/README.md) | ACQ | 6 | 5 Planned; 1 Partial |
| [13 - Authorised migration, service continuity and offboarding](modules/13-customer-migration-offboarding/README.md) | MIG | 2 | 2 Planned |
| [14 - Restaurant menus, web/phone orders and kitchen delivery](modules/14-restaurant-ordering/README.md) | ORD | 4 | 4 Planned |
| [15 - Security, consent, privacy, legal terms and assurance](modules/15-security-privacy-compliance/README.md) | SEC | 8 | 3 Partial; 5 Planned |
| [16 - Customer value, funnel and acquisition analytics](modules/16-business-value-analytics/README.md) | ANL | 2 | 1 Partial; 1 Planned |
| [17 - Internal administration, support and incident operations](modules/17-admin-backoffice/README.md) | ADM | 1 | 1 Planned |
| [18 - Infrastructure, durable workflows, reliability and scale](modules/18-reliability-deployment-scale/README.md) | OPS | 7 | 5 Partial; 2 Planned |
| [19 - Testing, accessibility, UAT and release acceptance](modules/19-testing-client-acceptance/README.md) | QA | 2 | 2 Partial |
| [20 - Ownership, licensing, documentation and operational handover](modules/20-ownership-handover/README.md) | OWN | 2 | 2 Partial |
| [21 - Customer repositories and client project delivery documentation](modules/21-project-documentation-workbench/README.md) | PJM | 2 | 2 Implemented |

## Important delivery boundaries

The current PostgreSQL/Supabase/Amplify implementation differs from the specification's RHEL/Podman/MariaDB baseline. The source SiteSpec/component renderer also differs from the current original AI HTML/CSS direction. Resolve the applicable decisions with evidence before claiming full compliance.

Browser voice, approved FAQs, usage tracking and a passing local build establish useful slices. Real telephone answering, staffed human coverage, subscriptions, independent ownership verification, custom domains, full recovery and client acceptance have their own remaining criteria.

When implementation changes behaviour or architecture, update the application's CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md with the code change. Maintain this repository's current status and affected tickets alongside release evidence.

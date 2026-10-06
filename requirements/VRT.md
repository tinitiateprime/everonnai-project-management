# VRT - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## VRT-001

Assigned delivery tickets: [EVN-VRT-044](../modules/10-brands-vertical-packs/tickets/EVN-VRT-044.md).

**Primary source:** TECH section 19.6 Brands and vertical packs (VRT); extraction row 1198.

**Source record:** VRT-001 [P1] MUST model a Brand as a first-class entity with: name, contracting legal entity, primary and secondary domains, theme (design tokens, logo, typography), legal documents (terms, privacy, messaging consent, client agreement), sender identities (email domain, text-message sender name, voice caller name), support contacts and physical address, the vertical or verticals it serves, its plan catalog and price book, its default vertical pack, and a status. Every tenant belongs to exactly one brand.

## VRT-002

Assigned delivery tickets: [EVN-VRT-044](../modules/10-brands-vertical-packs/tickets/EVN-VRT-044.md), [EVN-VRT-045](../modules/10-brands-vertical-packs/tickets/EVN-VRT-045.md).

**Primary source:** TECH section 19.6 Brands and vertical packs (VRT); extraction row 1199.

**Source record:** VRT-002 [P1] MUST apply the brand to everything a client or a client's customer sees: the client application and its login address, emails, texts, invoices, help content, generated websites' preview host, demonstration pages and notices. A user of one brand MUST NOT be able to discover or see another brand's clients, pricing or content.

## VRT-003

Assigned delivery tickets: [EVN-AIQ-104](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-104.md), [EVN-VRT-046](../modules/10-brands-vertical-packs/tickets/EVN-VRT-046.md), [EVN-VRT-048](../modules/10-brands-vertical-packs/tickets/EVN-VRT-048.md).

**Primary source:** TECH section 19.6 Brands and vertical packs (VRT); extraction row 1200.

**Source record:** VRT-003 [P1] MUST define a Vertical pack as a versioned data bundle containing: website templates and section variants; content library (service pages, FAQs, industry explanations); vocabulary and labels; intake playbooks and slot definitions; urgency, escalation and authority defaults; starter knowledge; greeting templates; the vertical's structured request schema (VRT-006); the compliance profile it requires (COM-014); the connector set it uses (INT-002); plans, entitlements and default terms; dashboard and report definitions; the onboarding checklist; and the migration playbooks for its conquest targets (MIG-010). Pack changes are versioned, staged, evaluated (EVL-005) and reversible.

## VRT-004

Assigned delivery tickets: [EVN-VRT-046](../modules/10-brands-vertical-packs/tickets/EVN-VRT-046.md).

**Primary source:** TECH section 19.6 Brands and vertical packs (VRT); extraction row 1201.

**Source record:** VRT-004 [P1] MUST support at least two brands and two packs live on one platform at the pilot, and MUST allow a new brand or pack to be added by configuration and content alone for standard cases, without changes to platform code. The elapsed time to create a new standard pack is measured and reported.

## VRT-005

Assigned delivery tickets: [EVN-VRT-047](../modules/10-brands-vertical-packs/tickets/EVN-VRT-047.md).

**Primary source:** TECH section 19.6 Brands and vertical packs (VRT); extraction row 1202.

**Source record:** VRT-005 [P1] MUST enforce a vertical readiness gate: a checklist per pack whose items (counsel review of terms and disclosures; compliance profile enabled and tested; evaluation set pass thresholds; playbook review by an industry expert; connector and fallback checks; pricing and published-claims check; operator training where the desk will serve the vertical) must each be approved by a named person before the pack can be enabled for production tenants. Approvals are recorded and versioned.

## VRT-006

Assigned delivery tickets: [EVN-VRT-046](../modules/10-brands-vertical-packs/tickets/EVN-VRT-046.md).

**Primary source:** TECH section 19.6 Brands and vertical packs (VRT); extraction row 1203.

**Source record:** VRT-006 [P1] MUST support vertical-specific structured data without schema changes: each pack declares the fields of its request object (for example vehicle details for auto repair, entity type and tax years for accounting, an order for a restaurant) in a JSON Schema; the platform validates, stores, displays, searches and reports on them.

## VRT-007

Assigned delivery tickets: [EVN-ANL-058](../modules/16-business-value-analytics/tickets/EVN-ANL-058.md), [EVN-HIL-027](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md), [EVN-VRT-044](../modules/10-brands-vertical-packs/tickets/EVN-VRT-044.md).

**Primary source:** TECH section 19.6 Brands and vertical packs (VRT); extraction row 1204.

**Source record:** VRT-007 [P2] SHOULD provide brand-level defaults for operators (greeting and desk-profile templates, notices) and cross-brand analytics for EverOnn with a brand and vertical filter.

## VRT-008

Assigned delivery tickets: [EVN-VRT-044](../modules/10-brands-vertical-packs/tickets/EVN-VRT-044.md).

**Primary source:** TECH section 19.6 Brands and vertical packs (VRT); extraction row 1205.

**Source record:** VRT-008 [P1] MUST share one inbox, one operator desk, one billing engine and one AI runtime across brands. Operators may be granted clients of several brands (DSK-002); the desk shows the client's business name as the primary identity and the brand as a secondary tag.

## VRT-009

Assigned delivery tickets: [EVN-VRT-044](../modules/10-brands-vertical-packs/tickets/EVN-VRT-044.md), [EVN-VRT-045](../modules/10-brands-vertical-packs/tickets/EVN-VRT-045.md).

**Primary source:** TECH section 19.6 Brands and vertical packs (VRT); extraction row 1206.

**Source record:** VRT-009 [P1] MUST name the contracting entity in every brand's legal documents, footers and client agreement, apply one consistent set of terms, privacy and refund policies across brands, and share a single suppression list across all brands (ACQ-008).

## VRT-010

Assigned delivery tickets: [EVN-VRT-046](../modules/10-brands-vertical-packs/tickets/EVN-VRT-046.md), [EVN-VRT-047](../modules/10-brands-vertical-packs/tickets/EVN-VRT-047.md).

**Primary source:** TECH section 19.6 Brands and vertical packs (VRT); extraction row 1207.

**Source record:** VRT-010 [P1] MUST support pack governance: an owner (vertical manager) per pack, a change log, a review calendar for time-sensitive content (market prices, regulatory notes), and metrics per pack (time to launch, activation, retention, cost to serve, escalation rate).

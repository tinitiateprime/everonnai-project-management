# INT - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## INT-001

Assigned delivery tickets: [EVN-INT-049](../modules/11-api-connectors-integrations/tickets/EVN-INT-049.md).

**Primary source:** TECH section 19.10 Integration framework and vertical connectors (INT); extraction row 1248.

**Source record:** INT-001 [P1] MUST provide a connector framework: a standard interface for authentication (OAuth or API key), initial and incremental sync, webhooks, field mapping, retries, rate-limit handling and health reporting; per-tenant credentials held in the secrets vault; a connector development kit; contract tests; versioning; a sandbox mode; failure isolation so that one connector cannot affect others; and audit of every action. Calendar, point-of-sale, field-service, shop-management, practice-management, accounting and agency systems all use it.

## INT-002

Assigned delivery tickets: [EVN-INT-049](../modules/11-api-connectors-integrations/tickets/EVN-INT-049.md), [EVN-VRT-048](../modules/10-brands-vertical-packs/tickets/EVN-VRT-048.md).

**Primary source:** TECH section 19.10 Integration framework and vertical connectors (INT); extraction row 1249.

**Source record:** INT-002 [P1] SHOULD maintain a connector catalog by vertical, in priority tiers with status (planned, beta, generally available). Candidates, each subject to confirmed access and terms before anything is promised to a client: auto repair (Tekmetric, Shop-Ware, Mitchell1, Shopmonkey and similar); home and urgent services (ServiceTitan, Housecall Pro, Jobber, FieldEdge); accounting (TaxDome, Canopy, Karbon, QuickBooks, Xero, SmartVault); law (Clio, MyCase, Lawmatics, Filevine); insurance (Applied Epic, EZLynx, HawkSoft, AMS360, AgencyZoom); dental (Dentrix, Eaglesoft, Open Dental); chiropractic (ChiroTouch); veterinary (Cornerstone, ezyVet, Shepherd, Neo); medical and med spa (Nextech, Zenoti, Boulevard); restaurants (Square, Toast, Clover). A connector appears in client-facing material only when it is generally available.

## INT-003

Assigned delivery tickets: [EVN-INT-049](../modules/11-api-connectors-integrations/tickets/EVN-INT-049.md).

**Primary source:** TECH section 19.10 Integration framework and vertical connectors (INT); extraction row 1250.

**Source record:** INT-003 [P1] MUST ensure every vertical pack works without any connector: requests are captured and structured, the team is notified, calendars and email or text are used, and nothing depends on a third-party system being connected. Connectors add automation; they are never required for the core service.

## INT-004

Assigned delivery tickets: [EVN-INT-049](../modules/11-api-connectors-integrations/tickets/EVN-INT-049.md), [EVN-VRT-047](../modules/10-brands-vertical-packs/tickets/EVN-VRT-047.md).

**Primary source:** TECH section 19.10 Integration framework and vertical connectors (INT); extraction row 1251.

**Source record:** INT-004 [P2] SHOULD track integration access as managed work: partner-program applications, terms, certification stages, commercial conditions and owners, visible to the vertical manager.

## INT-005

Assigned delivery tickets: [EVN-INT-049](../modules/11-api-connectors-integrations/tickets/EVN-INT-049.md), [EVN-SEC-065](../modules/15-security-privacy-compliance/tickets/EVN-SEC-065.md).

**Primary source:** TECH section 19.10 Integration framework and vertical connectors (INT); extraction row 1252.

**Source record:** INT-005 [P2] MUST apply data minimization and the vertical's compliance profile to connectors, and for health-care connectors permit only subprocessors covered by business associate agreements (COM-015).

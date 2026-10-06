# WEB - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## WEB-001

Assigned delivery tickets: [EVN-WEB-014](../modules/06-website-generation-hosting/tickets/EVN-WEB-014.md), [EVN-WEB-018](../modules/06-website-generation-hosting/tickets/EVN-WEB-018.md), [EVN-WEB-101](../modules/06-website-generation-hosting/tickets/EVN-WEB-101.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1122.

**Source record:** WEB-001 [P1] MUST implement the generation pipeline as durable jobs: (1) data collection (profile, imported content), (2) content generation with schema-constrained LLM output and brand/tone controls, (3) image selection or generation from licensed sources and the owner's photos (P1: owner photos, licensed stock; generated imagery only where licensing and disclosure rules are met), (4) Site Spec validation and safety checks (no invented licenses, awards, or claims), (5) render, (6) preview deployment. Target: under 2 minutes p50 to preview; throughput target 1,000 sites/day sustained with burst to 300 per hour (P2), with per-site LLM cost tracked and capped.

## WEB-002

Assigned delivery tickets: [EVN-WEB-014](../modules/06-website-generation-hosting/tickets/EVN-WEB-014.md), [EVN-WEB-019](../modules/06-website-generation-hosting/tickets/EVN-WEB-019.md), [EVN-WEB-102](../modules/06-website-generation-hosting/tickets/EVN-WEB-102.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1123.

**Source record:** WEB-002 [P1] MUST ensure content claim safety: the generator MUST NOT fabricate reviews, certifications, years in business, service guarantees, or prices. Any claim must trace to a source field or be flagged for owner confirmation. Preview shows "unverified claims" highlights the owner must resolve.

## WEB-003

Assigned delivery tickets: [EVN-ACQ-054](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-054.md), [EVN-ONB-015](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-015.md), [EVN-WEB-014](../modules/06-website-generation-hosting/tickets/EVN-WEB-014.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1124.

**Source record:** WEB-003 [P1] MUST keep previews private and non-indexable (noindex, unguessable URLs, no real phone or address exposure per ONB-002) until verification and owner approval; preview TTL and cleanup jobs apply to unclaimed prospects.

## WEB-004

Assigned delivery tickets: [EVN-WEB-016](../modules/06-website-generation-hosting/tickets/EVN-WEB-016.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1125.

**Source record:** WEB-004 [P1] MUST support custom domains: guided DNS setup (CNAME/ALIAS or nameservers), automatic TLS certificate issuance and renewal per hostname (ACME; on-demand TLS at the edge), domain verification, apex and www handling, redirects, and health monitoring with alerts. At P2, EverOnn can register domains on the owner's behalf through a registrar API.

## WEB-005

Assigned delivery tickets: [EVN-WEB-019](../modules/06-website-generation-hosting/tickets/EVN-WEB-019.md), [EVN-WEB-103](../modules/06-website-generation-hosting/tickets/EVN-WEB-103.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1126.

**Source record:** WEB-005 [P1] MUST serve tenant sites on a separate registrable domain from EverOnn's own application and marketing domains (for example everonn.site), so cookies, XSS blast radius, email reputation and SEO reputation are isolated.

## WEB-006

Assigned delivery tickets: [EVN-WEB-017](../modules/06-website-generation-hosting/tickets/EVN-WEB-017.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1127.

**Source record:** WEB-006 [P1] MUST generate SEO and AEO/GEO-ready markup: semantic HTML, LocalBusiness (and subtype) JSON-LD, FAQPage, Service, OpeningHoursSpecification, AggregateRating only when real and sourced, sitemap.xml, robots.txt, canonical tags, Open Graph, llms.txt and clean Q&A content blocks. Lighthouse mobile scores of 90 or more on all four categories, LCP under 2.5 s, CLS under 0.1 (measured in CI on a sample of generated sites).

## WEB-007

Assigned delivery tickets: [EVN-WEB-013](../modules/06-website-generation-hosting/tickets/EVN-WEB-013.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1128.

**Source record:** WEB-007 [P1] MUST embed the AI chat widget, click-to-call (tel: with tracking number), and lead forms by default, with spam protection (Turnstile/hCaptcha), rate limits, consent capture and delivery into the inbox.

## WEB-008

Assigned delivery tickets: [EVN-WEB-102](../modules/06-website-generation-hosting/tickets/EVN-WEB-102.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1129.

**Source record:** WEB-008 [P1] MUST provide a simple owner editor: edit text, hours, services, photos, colors, and reorder sections in the dashboard; changes create a new version; publish and rollback. No raw HTML editing by tenants at P1 (security).

## WEB-009

Assigned delivery tickets: [EVN-WEB-103](../modules/06-website-generation-hosting/tickets/EVN-WEB-103.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1130.

**Source record:** WEB-009 [P1] MUST sanitize all tenant-supplied content and enforce a strict Content Security Policy on tenant sites; tenant scripts and arbitrary embeds are prohibited at P1 (allow-listed embeds such as Google Maps only).

## WEB-010

Assigned delivery tickets: [EVN-ANL-039](../modules/16-business-value-analytics/tickets/EVN-ANL-039.md), [EVN-WEB-017](../modules/06-website-generation-hosting/tickets/EVN-WEB-017.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1131.

**Source record:** WEB-010 [P1] MUST support analytics for tenants: privacy-friendly first-party page views, click-to-call taps, form submissions, chat starts, source attribution (call tracking numbers per source at P2).

## WEB-011

Assigned delivery tickets: [EVN-WEB-018](../modules/06-website-generation-hosting/tickets/EVN-WEB-018.md), [EVN-WEB-101](../modules/06-website-generation-hosting/tickets/EVN-WEB-101.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1132.

**Source record:** WEB-011 [P2] MUST support bulk operations: template updates rolled out across all sites (with canary and rollback), bulk regeneration, and bulk domain checks; all through queued jobs with progress reporting.

## WEB-012

Assigned delivery tickets: [EVN-WEB-102](../modules/06-website-generation-hosting/tickets/EVN-WEB-102.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1133.

**Source record:** WEB-012 [P2] SHOULD provide multi-page vertical templates (service pages, city/area pages generated from service-area data with quality thresholds to avoid thin or duplicate content; the studio MUST document a policy to avoid search-spam patterns).

## WEB-013

Assigned delivery tickets: [EVN-WEB-019](../modules/06-website-generation-hosting/tickets/EVN-WEB-019.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1134.

**Source record:** WEB-013 [P1] MUST implement abuse controls: block generation for prohibited business categories, prevent phishing/impersonation sites (brand and domain similarity checks), takedown workflow (admin action within minutes), and a report-abuse link on every site.

## WEB-014

Assigned delivery tickets: [EVN-WEB-103](../modules/06-website-generation-hosting/tickets/EVN-WEB-103.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1135.

**Source record:** WEB-014 [P1] MUST implement CDN and cache strategy: immutable hashed assets, short HTML TTL with instant purge on publish, stale-while-revalidate, and origin shielding; the origin holds no per-request state.

## WEB-015

Assigned delivery tickets: [EVN-VOX-006](../modules/04-telephone-voice-language/tickets/EVN-VOX-006.md), [EVN-WEB-102](../modules/06-website-generation-hosting/tickets/EVN-WEB-102.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1136.

**Source record:** WEB-015 [P2] SHOULD support i18n (English and Spanish first) at the Site Spec level.

## WEB-016

Assigned delivery tickets: [EVN-VRT-046](../modules/10-brands-vertical-packs/tickets/EVN-VRT-046.md), [EVN-WEB-102](../modules/06-website-generation-hosting/tickets/EVN-WEB-102.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1137.

**Source record:** WEB-016 [P1] MUST provide vertical site templates and content libraries per pack (section variants, vocabulary, trust elements, service pages); the generation pipeline uses the pack's knowledge, and every generated claim remains subject to WEB-002.

## WEB-017

Assigned delivery tickets: [EVN-WEB-103](../modules/06-website-generation-hosting/tickets/EVN-WEB-103.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1138.

**Source record:** WEB-017 [P1] MUST publish sites under the client's own domain, with brand-specific preview and staging hosts and brand-specific legal pages, and a per-brand, per-plan option for a "powered by" credit; no page may give a misleading impression about the provider or its independence (BRL-032).

## WEB-018

Assigned delivery tickets: [EVN-VRT-048](../modules/10-brands-vertical-packs/tickets/EVN-VRT-048.md).

**Primary source:** TECH section 18.3 Requirements; extraction row 1139.

**Source record:** WEB-018 [P2] SHOULD provide vertical parity components per pack, delivered by building, embedding or connecting: accounting (secure client portal through a connector first; newsletters and tax-content library), auto repair (service pages, offers, review display), dental and medical (patient forms, scheduling embed), law (practice-area pages, intake forms), insurance (coverage pages, quote request), restaurants (ordering pages).

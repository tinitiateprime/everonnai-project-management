# ONB - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## ONB-001

Assigned delivery tickets: [EVN-WEB-014](../modules/06-website-generation-hosting/tickets/EVN-WEB-014.md).

**Primary source:** TECH section 12.2 Requirements; extraction row 753.

**Source record:** ONB-001 [P1] MUST implement the claim flow: input business name plus phone or website or Google listing link; system resolves the business, generates a private preview site (WEB-001) and a draft business profile within 2 minutes (target), then captures email or SMS to claim. Mobile thumb-friendly; at most 3 fields on the first screen.

## ONB-002

Assigned delivery tickets: [EVN-ONB-015](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-015.md), [EVN-WEB-019](../modules/06-website-generation-hosting/tickets/EVN-WEB-019.md).

**Primary source:** TECH section 12.2 Requirements; extraction row 754.

**Source record:** ONB-002 [P1] MUST prevent impersonation: a preview MUST NOT go public, receive real calls, or display the business's real phone number until ownership is verified (phone OTP to the number on the listing, or Google Business Profile ownership, or a document/manual review path handled by support). Verification method and result are stored.

## ONB-003

Assigned delivery tickets: [EVN-VOX-001](../modules/04-telephone-voice-language/tickets/EVN-VOX-001.md), [EVN-VOX-009](../modules/04-telephone-voice-language/tickets/EVN-VOX-009.md).

**Primary source:** TECH section 12.2 Requirements; extraction row 755.

**Source record:** ONB-003 [P1] MUST guide a 5-step setup wizard: (1) confirm business facts, (2) approve or edit services and hours, (3) set escalation and handoff rules, (4) choose how calls reach EverOnn (forward, port, or new number, VOX-030 to VOX-034), (5) test call and test chat, then go live. Progress is saved; the owner can resume from any device.

## ONB-004

Assigned delivery tickets: [EVN-ONB-022](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-022.md).

**Primary source:** TECH section 12.2 Requirements; extraction row 756.

**Source record:** ONB-004 [P1] MUST provide a test mode: a sandbox number and chat widget that run the real agent against the draft configuration without billing or notifying customers, with full transcript and "why did it say that" explanations (KNW-009).

## ONB-005

Assigned delivery tickets: [EVN-KNW-020](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-020.md).

**Primary source:** TECH section 12.2 Requirements; extraction row 757.

**Source record:** ONB-005 [P1] MUST require the owner to explicitly approve the AI's knowledge and greeting before go-live (a recorded approval event with the approved version id).

## ONB-006

Assigned delivery tickets: [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md).

**Primary source:** TECH section 12.2 Requirements; extraction row 758.

**Source record:** ONB-006 [P1] MUST capture business-hours, time zone, service area, languages, emergency policy, and preferred notification channels at onboarding.

## ONB-007

Assigned delivery tickets: [EVN-KNW-101](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-101.md), [EVN-ONB-015](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-015.md).

**Primary source:** TECH section 12.2 Requirements; extraction row 759.

**Source record:** ONB-007 [P1] SHOULD auto-import from Google Business Profile (name, hours, categories, reviews summary, photos) and from the existing website (services, FAQs) via the public web with respect for robots.txt and terms; failures MUST degrade to manual entry.

## ONB-008

Assigned delivery tickets: [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md).

**Primary source:** TECH section 12.2 Requirements; extraction row 760.

**Source record:** ONB-008 [P2] SHOULD support multi-location tenants (one tenant, many locations, each with its own number, hours and agent variant).

## ONB-009

Assigned delivery tickets: [EVN-ONB-101](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md).

**Primary source:** TECH section 12.2 Requirements; extraction row 761.

**Source record:** ONB-009 [P1] MUST support team invitations with roles from §10.2 and per-user notification preferences.

## ONB-010

Assigned delivery tickets: [EVN-ONB-015](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-015.md), [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md).

**Primary source:** TECH section 12.2 Requirements; extraction row 762.

**Source record:** ONB-010 [P1] MUST be resumable and idempotent: repeated claim submissions for the same business MUST NOT create duplicate tenants (dedupe on normalized phone, domain and Place ID).

## ONB-011

Assigned delivery tickets: [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-VRT-044](../modules/10-brands-vertical-packs/tickets/EVN-VRT-044.md).

**Primary source:** TECH section 12.2 Requirements; extraction row 763.

**Source record:** ONB-011 [P1] MUST make the claim flow brand-aware: each brand has its own landing and claim pages, forms, emails and consent texts, and creates the tenant under that brand and its vertical pack.

## ONB-012

Assigned delivery tickets: [EVN-ACQ-054](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-054.md).

**Primary source:** TECH section 12.2 Requirements; extraction row 764.

**Source record:** ONB-012 [P1] MUST support a switching claim: when a preview originates from an acquisition prospect, it is pre-populated from the prospect's public data with the source recorded, the prospect and tenant are linked, and a migration project (MIG-001) is opened as soon as the incumbent is known.

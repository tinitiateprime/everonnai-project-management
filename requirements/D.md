# D - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## D-1

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1935.

**Source record:** D-1 | Final plan packaging and pricing (Website $19, Front Desk $79, Growth $149 vs the tiers in the August 3 marketing brief), included minutes, overage, outcome pricing | EverOnn | Before P1 Increment 4 | Live-site tiers; 300 included minutes on Front Desk; overage per minute

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 723.

**Additional source wording:** D-1 | Final plan packaging: prices, included minutes, overage, operator add-on pricing, outcome-based pricing | EverOnn owner, product owner | Before billing is built | Website $19, Front Desk $79, Growth $149; 300 included minutes on Front Desk; overage per minute; operators as an add-on

## D-2

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1936.

**Source record:** D-2 | RHEL/MariaDB exceptions (Temporal, Langfuse, Sentry self-host, Unleash, Qdrant, OpenSearch, ClickHouse) | EverOnn + studio | P0 | No exceptions; use baseline-compatible alternatives or SaaS for non-core functions

## D-3

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1937.

**Source record:** D-3 | Telecom/privacy counsel engagement; consent, recording, AI-disclosure wording | EverOnn | Before P1 pilot | Most conservative rules (all-party consent announcement; explicit SMS opt-in)

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 724.

**Additional source wording:** D-3 | Telecom and privacy counsel engaged; consent, recording and AI-disclosure wording | EverOnn owner | Before the pilot | The most conservative rules (announce recording where any party may require it; explicit text opt-in)

## D-4

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1938.

**Source record:** D-4 | Vector store: MariaDB VECTOR vs Qdrant | Studio recommends | P0 | MariaDB VECTOR at P1

## D-5

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1939.

**Source record:** D-5 | Identity provider: Keycloak vs SaaS | Studio recommends, EverOnn approves | P0 | Keycloak

## D-6

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1940.

**Source record:** D-6 | Edge and custom-domain approach: Cloudflare for SaaS vs self-hosted ACME | Studio recommends | P0 | Cloudflare in front, on-demand TLS for custom hostnames

## D-7

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1941.

**Source record:** D-7 | Voice orchestration: build on LiveKit Agents/Pipecat vs managed platform for pilot | Studio recommends with evidence | P0 | Build on LiveKit Agents behind AgentRuntime

## D-8

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1942.

**Source record:** D-8 | Hosting model: EverOnn-owned RHEL servers/colo vs RHEL on cloud IaaS; failure-domain layout | EverOnn | P0 | RHEL on IaaS in two failure domains, media tier separate

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 725.

**Additional source wording:** D-8 | Hosting model: EverOnn-owned servers or cloud servers running the standard platform; failure-domain layout | EverOnn owner | Foundations | Cloud servers running the standard platform in two failure domains, with the voice media tier separate

## D-9

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1943.

**Source record:** D-9 | HITL workforce model: employees vs BPO partner, coverage hours, geographies, languages, pay model | EverOnn | Before P2 | Mode A plus a small pilot pool of EverOnn operators (Mode B) at P1; design for employees and partner pools

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 726.

**Additional source wording:** D-9 | Human operator workforce: employees or partner, coverage hours, locations, languages | EverOnn operations lead | Before Phase 2 | Owner mode plus a small pilot pool of EverOnn operators; design for employees and partners

## D-10

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1944.

**Source record:** D-10 | Default call recording policy and retention (on/off, 90 days) | EverOnn + counsel | Before pilot | Recording on with announcement where required; 90-day retention

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 727.

**Additional source wording:** D-10 | Default recording policy and retention | EverOnn owner, counsel | Before the pilot | Recording on with announcement where required; 90-day retention

## D-11

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1945.

**Source record:** D-11 | Launch geography (US only vs US and Canada) and language (EN/ES) | EverOnn | P0 | US, English and Spanish

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 728.

**Additional source wording:** D-11 | Launch geography and languages | EverOnn owner | Foundations | United States; English and Spanish

## D-12

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1946.

**Source record:** D-12 | Tenant-site domain (everonn.site or other), registration and DNS ownership | EverOnn | P0 | Register separate domain; wildcard DNS

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 729.

**Additional source wording:** D-12 | Domain for client websites | EverOnn owner | Foundations | A separate domain from EverOnn's own, with wildcard addressing

## D-13

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1947.

**Source record:** D-13 | Persona and voice branding for the default AI voice; owner voice cloning policy | EverOnn | P1 | Curated voices; no cloning

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 730.

**Additional source wording:** D-13 | Persona and voice for the default AI; policy on cloning an owner's voice | EverOnn product owner | Pilot | Curated voices; no cloning

## D-14

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1948.

**Source record:** D-14 | Source of truth for business data import (Google Business Profile API vs scraping) and terms compliance | Studio + counsel | P0 | Official APIs and owner-provided data only; no scraping of sites that prohibit it

## D-15

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1949.

**Source record:** D-15 | Operator audio topology: private briefing room then bridge (Design A) vs restricted subscription in the caller's room (Design B); softphone approach and telephone fallback (§16.7.2) | Studio recommends with spike evidence | P0 | Design A unless the spike shows a clear advantage for B

## D-16

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1950.

**Source record:** D-16 | Default authority matrix for operators and the default greeting and announcement behavior, by vertical | EverOnn operations lead | Before the pilot | Conservative: no quotes, no time commitments, booking allowed, dispatch by owner approval; announcement on

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 731.

**Additional source wording:** D-16 | Default authority for operators, and default greeting and announcement behavior, by industry | EverOnn operations lead | Before the pilot | Conservative: no quotes, no time commitments, booking allowed, dispatch with owner approval; announcement on

## D-17

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1951.

**Source record:** D-17 | Operator coverage model: hours, languages, location, employment model, and client coverage windows | EverOnn operations lead | Before the pilot | Pilot pool in one time zone with extended hours; Spanish-skilled operator on every shift; after-hours falls back to owner mode

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 732.

**Additional source wording:** D-17 | Operator coverage model: hours, languages, location, employment model, per-client coverage windows | EverOnn operations lead | Before the pilot | Pilot pool in one time zone with extended hours; a Spanish-skilled operator on every shift; after hours falls back to owner mode

## D-18

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1952.

**Source record:** D-18 | Positioning of EverOnn-operated human operators against the published statement that EverOnn provides technology, not services (public site, terms, liability, regulatory classification of a staffed answering service) | EverOnn owner + counsel | Before the pilot | Offer operators only as a separately contracted managed service with its own terms; keep the technology-only statement for the core product

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 733.

**Additional source wording:** D-18 | Positioning of EverOnn-operated human operators against the "technology, not services" statement | EverOnn owner, counsel | Before the pilot | A separately contracted managed service with its own terms; technology-only statement kept for the core product

## D-19

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1953.

**Source record:** D-19 | Launch verticals: the published site lists locksmith, roadside and towing, HVAC, plumbing, garage door and cleaning services; this document also names electricians and restoration | EverOnn owner | P0 | Build playbooks for the six published verticals first; add electricians and restoration later

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 734.

**Additional source wording:** D-19 | Launch industries | EverOnn owner | Foundations | The six industries published on the website first

## D-20

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1954.

**Source record:** D-20 | Plan entitlement mapping for capabilities not stated on the site: two-way texting and missed-call text-back, calendar booking, Spanish, follow-up sequences, review workflows, expanded reporting, local service pages | EverOnn owner + product owner | Before P1 billing | Mapping in the business requirements document (plan and phase matrix)

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 735.

**Additional source wording:** D-20 | Plan entitlement mapping for capabilities not stated on the website | EverOnn owner, product owner | Before billing is built | The mapping in section 5.3

## D-21

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1955.

**Source record:** D-21 | Private preview intake: instant self-service versus staff-prepared preview, and the fields collected on the form | EverOnn product owner | P0 | Keep the two-minute target with staff review as a fallback; three fields on the first screen, remaining details after claim

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 736.

**Additional source wording:** D-21 | Private preview intake: instant or staff-prepared; form fields | EverOnn product owner | Foundations | Two-minute target with staff review as fallback; three fields first

## D-22

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1956.

**Source record:** D-22 | Meaning of STOP: all non-essential messages from the number, or marketing messages only | EverOnn owner + counsel | Before the pilot | STOP ends all non-essential messages from that number; counsel to confirm and the published messaging-consent page to match

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 737.

**Additional source wording:** D-22 | Meaning of STOP | EverOnn owner, counsel | Before the pilot | Ends all non-essential messages from the number

## D-23

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1957.

**Source record:** D-23 | Public wording of the phone-number promise (keep your number): forwarding at P1, porting at P2 | EverOnn product owner | Before P1 launch | Say forwarding is supported now and porting is planned

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 738.

**Additional source wording:** D-23 | Public wording of the phone-number promise | EverOnn product owner | Before pilot launch | Forwarding now; porting planned

## D-24

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1958.

**Source record:** D-24 | EverOnn's own legal documents: extend the privacy policy, terms and messaging consent to platform data (recordings, transcripts, AI processing, processor role); add a client agreement and data-processing terms | EverOnn owner + counsel | Before the pilot | Counsel-drafted set covering the platform, published before the first pilot client

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 739.

**Additional source wording:** D-24 | EverOnn's own legal documents extended to the platform; client agreement and data-processing terms | EverOnn owner, counsel | Before the pilot | Counsel-drafted set published before the first pilot client

## D-25

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1959.

**Source record:** D-25 | Demonstration assets: live demo number and audio samples, including a locksmith sample | EverOnn product owner | P1 | Add a locksmith sample; live demo number when the demo tenant is ready

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 740.

**Additional source wording:** D-25 | Demonstration assets: live demo number and audio samples including locksmith | EverOnn product owner | Pilot | Add a locksmith sample; live number when ready

## D-26

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1960.

**Source record:** D-26 | First verticals and their order (waves): auto repair and home and urgent services in P1, accounting in P2, restaurants pilot in P2, regulated verticals in P3 | EverOnn owner | P0 | Waves as in §5.6

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 741.

**Additional source wording:** D-26 | First verticals and their order (waves) | EverOnn owner | Foundations | Auto repair and home and urgent services in the pilot; accounting and the restaurant pilot in scale; regulated verticals in expansion

## D-27

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1961.

**Source record:** D-27 | Vertical brand names, domains, how the brand and EverOnn are presented, and trademark clearance | EverOnn owner + counsel | Before each brand launches | EverOnn named as contracting entity on every brand; clearance before launch

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 742.

**Additional source wording:** D-27 | Vertical brand names, domains, how the brand and EverOnn are presented, and trademark clearance | EverOnn owner, counsel | Before each brand launches | EverOnn named as contracting entity on every brand; clearance before launch

## D-28

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1962.

**Source record:** D-28 | First conquest targets per vertical, and written confirmation of each data source's license terms | EverOnn owner | P0 | Repair Shop Websites and Autoshop Solutions (auto repair); Chinese Menu Online (restaurants); CPA Site Solutions (accounting); no use of technology-list phone numbers

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 743.

**Additional source wording:** D-28 | First conquest targets per vertical, and written confirmation of each data source's license terms | EverOnn owner | Foundations | Repair Shop Websites and Autoshop Solutions (auto repair); Chinese Menu Online (restaurants); CPA Site Solutions (accounting); no use of technology-list phone numbers

## D-29

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1963.

**Source record:** D-29 | Outreach channels and staffing | EverOnn owner + counsel | Before outreach begins | Email and manually dialed calls only; no AI-voice or automated-text outreach; registrations where required

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 744.

**Additional source wording:** D-29 | Outreach channels and staffing | EverOnn owner, counsel | Before outreach begins | Email and manually dialed calls only; no AI-voice or automated-text outreach; registrations where required

## D-30

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1964.

**Source record:** D-30 | Restaurant pilot design: order-receipt path, payment approach, accuracy thresholds, choice of three pilot restaurants | EverOnn product owner | Before the pilot | Staff-accept screen plus printer; pay at pickup or by payment link; thresholds set before the pilot

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 745.

**Additional source wording:** D-30 | Restaurant pilot design: how orders reach the kitchen, payment approach, accuracy thresholds, choice of three restaurants | EverOnn product owner | Before the pilot | Staff-accept screen plus printer; pay at pickup or by payment link; thresholds set before the pilot

## D-31

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1965.

**Source record:** D-31 | Health-care readiness: which providers sign business associate agreements, timing, and whether veterinary launches before HIPAA-covered practices | EverOnn owner + counsel | Before wave C | Veterinary first; health-care packs only after the agreement chain is proven

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 746.

**Additional source wording:** D-31 | Health-care readiness: which providers sign business associate agreements, timing, and whether veterinary launches before HIPAA-covered practices | EverOnn owner, counsel | Before wave C | Veterinary first; health-care packs only after the agreement chain is proven

## D-32

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1966.

**Source record:** D-32 | Migration policy: who performs and pays for migration, parallel-run period, treatment of early-termination fees | EverOnn owner | Before the first conversion | EverOnn performs migration at no charge; never pays or advises breach of a contract; fees are counted in the comparison

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 747.

## D-33

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1967.

**Source record:** D-33 | Per-vertical pricing and switching offers | EverOnn owner | Before each brand launches | Per-brand price books benchmarked to incumbents; offers only with substantiated comparisons

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 748.

## D-34

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 26.3 Open decisions register; extraction row 1968.

**Source record:** D-34 | Accountants' client portal: connector first or a native portal | EverOnn product owner | Before the accounting pack | Connector first

**Also documented:** BRD section Appendix B. Open decisions register; extraction row 749.

**Additional source wording:** D-34 | Accountants' client portal: connect to the firm's own portal first, or build a native one | EverOnn product owner | Before the accounting pack | Connect first

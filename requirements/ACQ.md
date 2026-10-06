# ACQ - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## ACQ-001

Assigned delivery tickets: [EVN-ACQ-050](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-050.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1210.

**Source record:** ACQ-001 [P1] MUST provide a conquest target registry. A target records: the incumbent provider and the verticals it serves; its detection signatures (technology-list references, "powered by" credit patterns, hosting or domain fingerprints); the source lists and their terms and refresh dates; published pricing snapshots with as-of dates and source links; the feature checklist; contract and lock-in notes (term, renewal, termination fees, ownership of domain and content); known AI features; the migration playbook (MIG-010); offer templates; and status. New targets are created by configuration. Time-sensitive facts carry an as-of date and a review-by date and are flagged when stale (BRL-038).

## ACQ-002

Assigned delivery tickets: [EVN-ACQ-051](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-051.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1211.

**Source record:** ACQ-002 [P1] MUST support prospect ingestion from permitted sources (licensed technology lists, public portfolios and directories, EverOnn's own research, inbound forms). Every record keeps provenance: source, list, date, the terms basis for use, and the evidence of the incumbent relationship. Ingestion deduplicates across sources (domain, phone, place identifier), removes redirects, inactive sites, out-of-scope locations and non-target businesses, and tags each field with the uses its source permits (for example, contact numbers from a technology list are flagged "not for marketing"). Records past their retention period are purged.

## ACQ-003

Assigned delivery tickets: [EVN-ACQ-051](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-051.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1212.

**Source record:** ACQ-003 [P1] MUST hold a prospect record with: business name; website; location; incumbent provider; evidence and its date; public business contact; decision-maker role; visible website, chat and ordering features; actual current bill (once obtained); identified gap; current portal, POS or practice-software dependencies; proposed EverOnn package; savings calculation; migration needs; next action; and status. Each field records whether it is verified, estimated or unknown; unknown is never displayed or reported as "no" (BRL-027).

## ACQ-004

Assigned delivery tickets: [EVN-ACQ-052](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-052.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1213.

**Source record:** ACQ-004 [P1] SHOULD provide qualification and scoring using transparent, adjustable rules (signals of an enquiry-handling gap such as no chat or online booking, size of current spend, migration complexity, regulatory load, location and size). Scores explain their factors, never assert facts, and can be overridden by a person.

## ACQ-005

Assigned delivery tickets: [EVN-ACQ-052](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-052.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1214.

**Source record:** ACQ-005 [P1] MUST run a pipeline with defined stages (identified, verified, previewed, contacted, engaged, demonstrated, proposed, agreed, migrating, live, retained or lost), an owner and a next action for each prospect, an audit trail, and views by target, vertical, brand and channel.

## ACQ-006

Assigned delivery tickets: [EVN-ACQ-054](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-054.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1215.

**Source record:** ACQ-006 [P1] MUST generate a personalized preview and demonstration from a prospect's own public business details: a private, non-indexed website preview using the preview engine (WEB-003), and a demonstration agent, on the prospect's business name, services, hours and handoff rules, that can be tried by chat or a call the prospect requests. Nothing is published without verified owner approval (BRL-006), and no call or text is placed to a prospect without a consent record (BRL-028). Previews expire automatically.

## ACQ-007

Assigned delivery tickets: [EVN-ACQ-055](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-055.md), [EVN-MIG-057](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-057.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1216.

**Source record:** ACQ-007 [P1] MUST provide an honest savings comparison calculator. Inputs are the prospect's current monthly cost items, contract term and early-termination fee, the services the prospect must keep, payment-processing costs, and, for providers that charge a percentage of orders, the order volume. Each input is tagged prospect-confirmed, public or estimate. Outputs are total current cost, total EverOnn cost (plan, expected usage and overages), break-even, and clear disclosures. A savings claim may be shared only when its key inputs are confirmed or are clearly labeled as estimates (BRL-030).

## ACQ-008

Assigned delivery tickets: [EVN-ACQ-053](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-053.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1217.

**Source record:** ACQ-008 [P1] MUST run compliant outreach. Channels are email (brand sender identity, physical address, working one-step opt-out honored within 10 business days, accurate headers and subject lines), manually dialed calls (number-type screening, recipient local time, state calling rules, do-not-call scrub, frequency caps, call log) and postal mail. Automated, prerecorded and AI-voice calls and automated texts are disabled by default and can be enabled for a contact only when a prior express consent record exists (COM-001). A global, permanent suppression list (stored as hashes) applies across all brands and is checked before every send. Templates are approved and versioned; every touch is logged; rule tables (state hours, frequency limits) are data (COM-018).

## ACQ-009

Assigned delivery tickets: [EVN-ACQ-053](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-053.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1218.

**Source record:** ACQ-009 [P1] MUST capture consent and preferences on every prospect-facing form (preview request, demonstration request) using the consent ledger and disclosure texts of the relevant brand.

## ACQ-010

Assigned delivery tickets: [EVN-ACQ-055](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-055.md), [EVN-BIL-043](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-043.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1219.

**Source record:** ACQ-010 [P1] MUST keep a claims register: every comparative statement, savings figure, statistic, customer story or testimonial used in outreach or on any brand's site is recorded with its source, date, approver and expiry. Templates and site content may reference only approved, unexpired claims. Competitor names appear only as plain text, without logos or any implication of affiliation.

## ACQ-011

Assigned delivery tickets: [EVN-ACQ-051](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-051.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1220.

**Source record:** ACQ-011 [P1] SHOULD protect prospect data: minimum fields, notice at collection where required, handling of access and deletion requests, a retention schedule with automatic purge of unengaged prospects, role-based access, export controls, and a flag for counsel's determination of whether the dataset is treated as a data-broker list in any state.

## ACQ-012

Assigned delivery tickets: [EVN-ANL-058](../modules/16-business-value-analytics/tickets/EVN-ANL-058.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1221.

**Source record:** ACQ-012 [P2] SHOULD provide acquisition analytics: funnel by target, vertical, brand and channel; cost per acquired client; time from first contact to live; savings delivered; retention after switching; and the accuracy of each source list measured by sampling.

## ACQ-013

Assigned delivery tickets: [EVN-ACQ-050](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-050.md).

**Primary source:** TECH section 19.7 Customer acquisition (ACQ); extraction row 1222.

**Source record:** ACQ-013 [P2] MAY monitor sources on a schedule (list refreshes within license, incumbent price and feature changes) and create review tasks.

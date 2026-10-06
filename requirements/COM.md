# COM - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## COM-001

Assigned delivery tickets: [EVN-ACQ-053](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-053.md), [EVN-SEC-064](../modules/15-security-privacy-compliance/tickets/EVN-SEC-064.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1178.

**Source record:** COM-001 [P1] MUST implement a consent ledger: immutable records of every consent and opt-out (contact_id, channel, purpose, text_shown, method, timestamp, IP/agent, page, tenant_id, revoked_at). Sending logic MUST consult the ledger (fail closed).

## COM-002

Assigned delivery tickets: [EVN-ACQ-053](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-053.md), [EVN-CHT-012](../modules/05-chat-widget-sms/tickets/EVN-CHT-012.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1179.

**Source record:** COM-002 [P1] MUST implement SMS/TCPA controls: prior express consent capture for informational and transactional messages, separate consent for marketing, STOP/HELP handling, quiet hours, sender identification, frequency caps, and a full audit trail. Marketing/outbound features are off by default.

## COM-003

Assigned delivery tickets: [EVN-AIQ-004](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-004.md), [EVN-SEC-064](../modules/15-security-privacy-compliance/tickets/EVN-SEC-064.md), [EVN-SEC-066](../modules/15-security-privacy-compliance/tickets/EVN-SEC-066.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1180.

**Source record:** COM-003 [P1] MUST implement AI disclosure: voice and chat identify as AI where required or when sincerely asked, in a configurable but policy-bounded manner (state and jurisdiction rules table maintained by EverOnn).

## COM-004

Assigned delivery tickets: [EVN-SEC-064](../modules/15-security-privacy-compliance/tickets/EVN-SEC-064.md), [EVN-SEC-066](../modules/15-security-privacy-compliance/tickets/EVN-SEC-066.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1181.

**Source record:** COM-004 [P1] MUST implement call recording consent logic by jurisdiction (one-party vs all-party regimes, determined from the caller's and business's locations): play an announcement where needed; if consent is refused, stop recording and continue with transcript-only or per policy. The jurisdiction rules table is data, versioned, and reviewed by counsel.

## COM-005

Assigned delivery tickets: [EVN-SEC-064](../modules/15-security-privacy-compliance/tickets/EVN-SEC-064.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1182.

**Source record:** COM-005 [P1] MUST track carrier compliance (A2P 10DLC brand and campaign registration, toll-free verification, STIR/SHAKEN reputation) as a managed workflow with owner and support visibility.

## COM-006

Assigned delivery tickets: [EVN-SEC-066](../modules/15-security-privacy-compliance/tickets/EVN-SEC-066.md), [EVN-VRT-045](../modules/10-brands-vertical-packs/tickets/EVN-VRT-045.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1183.

**Source record:** COM-006 [P1] MUST publish accurate Privacy Policy, Terms, Messaging Terms templates rendered per tenant on their sites, with tenant-specific data controller information.

## COM-007

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1184.

**Source record:** COM-007 [P1] MUST implement PII redaction in logs, traces, analytics and eval datasets (names, phones, emails, addresses, card and government IDs), with reversible tokenization only in the primary store. Training or eval use of customer conversations requires opt-in and anonymization.

## COM-008

Assigned delivery tickets: [EVN-SEC-067](../modules/15-security-privacy-compliance/tickets/EVN-SEC-067.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1185.

**Source record:** COM-008 [P1] MUST implement data retention policies per data class (default proposals: recordings 90 days, transcripts 24 months, audit logs 7 years, billing 7 years; configurable per plan and tenant), automated deletion, legal hold support, and deletion on account closure after a grace period.

## COM-009

Assigned delivery tickets: [EVN-SEC-066](../modules/15-security-privacy-compliance/tickets/EVN-SEC-066.md), [EVN-SEC-067](../modules/15-security-privacy-compliance/tickets/EVN-SEC-067.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1186.

**Source record:** COM-009 [P1] MUST support data subject rights (access, deletion, correction, opt-out of sale/sharing where applicable) for tenants' customers via tenant-initiated tooling and an EverOnn intake process, with SLAs.

## COM-010

Assigned delivery tickets: [EVN-SEC-065](../modules/15-security-privacy-compliance/tickets/EVN-SEC-065.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1187.

**Source record:** COM-010 [P2] SHOULD provide a HIPAA-ready mode (BAA-eligible vendors only, restricted logging, encryption, audit) for health-adjacent verticals in P3; scaffold the compliance_profile field on tenants at P1.

## COM-011

Assigned delivery tickets: [EVN-SEC-066](../modules/15-security-privacy-compliance/tickets/EVN-SEC-066.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1188.

**Source record:** COM-011 [P2] SHOULD maintain a subprocessor register and vendor DPA/BAA tracking; expose it publicly.

## COM-012

Assigned delivery tickets: [EVN-ACQ-053](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-053.md), [EVN-SEC-064](../modules/15-security-privacy-compliance/tickets/EVN-SEC-064.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1189.

**Source record:** COM-012 [P3] MUST treat outbound calls and marketing texts as high-risk: require a compliance design review, DNC scrubbing, calling-hours windows, revocation handling, and AI-voice consent rules before any outbound automation ships.

## COM-013

Assigned delivery tickets: [EVN-QA-074](../modules/19-testing-client-acceptance/tickets/EVN-QA-074.md), [EVN-QA-101](../modules/19-testing-client-acceptance/tickets/EVN-QA-101.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1190.

**Source record:** COM-013 [P1] MUST support accessibility compliance (WCAG 2.1 AA) for the dashboard, widget and generated sites.

## COM-014

Assigned delivery tickets: [EVN-SEC-065](../modules/15-security-privacy-compliance/tickets/EVN-SEC-065.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1191.

**Source record:** COM-014 [P1] MUST implement a compliance profile framework. Each tenant has a compliance profile (default, hipaa_covered, legal, insurance, tax_accounting, food_ordering, veterinary) that the vertical pack requires and that drives enforced behavior: disclosure texts, recording rules, retention, redaction level, permitted subprocessors, capabilities allowed (for example quoting), prohibited topics, escalation triggers and human gating. Profile changes are audited and cannot be made by the client alone.

## COM-015

Assigned delivery tickets: [EVN-SEC-065](../modules/15-security-privacy-compliance/tickets/EVN-SEC-065.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1192.

**Source record:** COM-015 [P3] MUST provide a health-care privacy mode for HIPAA-covered practices: a workflow for the client to sign the business associate agreement; a subprocessor register that records, per provider and per product or tier, whether an agreement covers it; a patient-information pipeline with no model training, zero-retention or equivalent settings where required, encrypted recordings and transcripts, redacted logs, traces and evaluation data, minimum-necessary capture, short default retention with purge, access logging and a breach-notification workflow. A health-care pack MUST be blocked from going live unless every provider in the call path is covered.

## COM-016

Assigned delivery tickets: [EVN-SEC-065](../modules/15-security-privacy-compliance/tickets/EVN-SEC-065.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1193.

**Source record:** COM-016 [P2] MUST apply professional-services guardrails: for law, disclose the AI, state that no attorney-client relationship exists yet, gather party names for conflict checks without advising, never train on client data, and keep transcripts retrievable; for insurance, gate quotes, coverage explanations, claims-status answers and binding to licensed staff; for accounting and tax, give no tax advice or return-specific answers, never collect Social Security numbers or return details by voice or chat, provide secure-upload instructions, and default to not ingesting return data.

## COM-017

Assigned delivery tickets: [EVN-SEC-065](../modules/15-security-privacy-compliance/tickets/EVN-SEC-065.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1194.

**Source record:** COM-017 [P1] MUST enforce advice limits and safe scripts in every vertical: emergency guidance and routing, no diagnosis or interpretation of results or medication advice, no titles that imply licensure, AI disclosure at the start of every call and chat, and a route to a person.

## COM-018

Assigned delivery tickets: [EVN-SEC-065](../modules/15-security-privacy-compliance/tickets/EVN-SEC-065.md).

**Primary source:** TECH section 19.5 Compliance and legal-by-design (COM); extraction row 1195.

**Source record:** COM-018 [P2] MUST hold state and vertical rule tables as data, reviewed by counsel: AI-disclosure and recording rules by state and vertical, and outreach rules (calling hours, frequency limits, registration) used by the acquisition console (ACQ-008).

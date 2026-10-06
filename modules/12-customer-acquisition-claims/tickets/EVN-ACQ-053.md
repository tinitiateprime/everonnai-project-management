# EVN-ACQ-053 - Compliant outreach

Project: EverOnnAI. Module: [Incumbent targets, prospects, outreach and savings evidence](../README.md). Source business requirement [BR-053](../../../requirements/BR.md#br-053).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Acquisition Manager + Product Owner + Counsel (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-SEC-101](../../15-security-privacy-compliance/tickets/EVN-SEC-101.md) |

## Business deliverable

Compliant outreach. Outreach follows email, calling, texting and privacy rules: accurate sender identity, working opt-out, one suppression list across all brands, no automated or AI-voice contact without documented prior consent, and a record of every contact.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] No outreach console or cross-brand consent/suppression ledger exists.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Implement approved email/manual channels, identity/opt-out/DNC/time checks and contact logs; gate automation.

## Technical component

- [ ] Implement the module boundary and contracts for: Fail-closed guard and counsel-approved rules.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: No acquisition target/prospect/provenance/claims domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] outreach_consents, suppressions, activities.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Composer, suppression warning and history.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Compliant outreach. Outreach follows email, calling, texting and privacy rules: accurate sender identity, working opt-out, one suppression list across all brands, no automated or AI-voice contact without documented prior consent, and a record of every contact. | Fail-closed guard and counsel-approved rules | Tenant-scoped end-to-end demonstration of the outcome |
| Implement approved email/manual channels, identity/opt-out/DNC/time checks and contact logs; gate automation. | outreach_consents, suppressions, activities; Composer, suppression warning and history | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | No autonomous AI-voice or automated-text prospecting | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Fail-closed guard and counsel-approved rules.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] No autonomous AI-voice or automated-text prospecting.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-23](../../../requirements/AT.md#at-23) | Outreach guardrails | Emails carry the brand's sender identity, address and opt-out; an opt-out on one brand suppresses all brands; automated or AI-voice contact without a consent record is blocked; manual calls respect number type, local time and state rules | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-063](../../../requirements/US.md#us-063).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ACQ-008](../../../requirements/ACQ.md#acq-008) | Source-linked | 19.7 Customer acquisition (ACQ) |
| [ACQ-009](../../../requirements/ACQ.md#acq-009) | Source-linked | 19.7 Customer acquisition (ACQ) |
| [AT-23](../../../requirements/AT.md#at-23) | Source-linked | 25.2 Acceptance tests |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BO-10](../../../requirements/BO.md#bo-10) | Source-linked | 3.1 Business objectives |
| [BR-053](../../../requirements/BR.md#br-053) | Source-linked | 7.9 Customer acquisition and migration |
| [BRL-007](../../../requirements/BRL.md#brl-007) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-028](../../../requirements/BRL.md#brl-028) | Plan allocation / source cross-reference | 8. Business rules |
| [COM-001](../../../requirements/COM.md#com-001) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [COM-002](../../../requirements/COM.md#com-002) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [COM-012](../../../requirements/COM.md#com-012) | Plan allocation / source cross-reference | 19.5 Compliance and legal-by-design (COM) |
| [US-063](../../../requirements/US.md#us-063) | Source-linked | EP-13 Customer acquisition and migration |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ACQ-008](../../../requirements/ACQ.md#acq-008): ACQ-008 [P1] MUST run compliant outreach. Channels are email (brand sender identity, physical address, working one-step opt-out honored within 10 business days, accurate headers and subject lines), manually dialed calls (number-type screening, recipient local time, state calling rules, do-not-call scrub, frequency caps, call log) and postal mail. Automated, prerecorded and AI-voice calls and automated texts are disabled by default and can be enabled for a contact only when a prior express consent record exists (COM-001). A global, permanent suppression list (stored as hashes) applies across all brands and is checked before every send. Templates are approved and versioned; every touch is logged; rule tables (state hours, frequency limits) are data (COM-018).
- [ ] [ACQ-009](../../../requirements/ACQ.md#acq-009): ACQ-009 [P1] MUST capture consent and preferences on every prospect-facing form (preview request, demonstration request) using the consent ledger and disclosure texts of the relevant brand.
- [ ] [BRL-007](../../../requirements/BRL.md#brl-007): BRL-007 | No text message is sent without recorded consent, and STOP is honored immediately. | All messaging | COM-001, COM-002, CHT-009.
- [ ] [BRL-028](../../../requirements/BRL.md#brl-028): BRL-028 | No automated, prerecorded or AI-voice call and no automated text is sent to a prospect without documented prior express consent. Opt-outs and suppression apply permanently and across all brands. | Outreach | ACQ-008, ACQ-009, COM-001.
- [ ] [COM-001](../../../requirements/COM.md#com-001): COM-001 [P1] MUST implement a consent ledger: immutable records of every consent and opt-out (contact_id, channel, purpose, text_shown, method, timestamp, IP/agent, page, tenant_id, revoked_at). Sending logic MUST consult the ledger (fail closed).
- [ ] [COM-002](../../../requirements/COM.md#com-002): COM-002 [P1] MUST implement SMS/TCPA controls: prior express consent capture for informational and transactional messages, separate consent for marketing, STOP/HELP handling, quiet hours, sender identification, frequency caps, and a full audit trail. Marketing/outbound features are off by default.
- [ ] [COM-012](../../../requirements/COM.md#com-012): COM-012 [P3] MUST treat outbound calls and marketing texts as high-risk: require a compliance design review, DNC scrubbing, calling-hours windows, revocation handling, and AI-voice consent rules before any outbound automation ships.

## Existing code / check evidence



## Blockers and boundaries

Module risk: Business leads cannot be relabelled as verified prospects; source licences, compliant outreach, suppression and substantiated comparisons are absent.

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-SEC-101](../../15-security-privacy-compliance/tickets/EVN-SEC-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.

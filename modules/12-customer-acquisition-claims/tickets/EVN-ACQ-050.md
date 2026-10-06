# EVN-ACQ-050 - Target any provider's customers

Project: EverOnnAI. Module: [Incumbent targets, prospects, outreach and savings evidence](../README.md). Source business requirement [BR-050](../../../requirements/BR.md#br-050).

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

Target any provider's customers. EverOnn can define any incumbent provider as a target, with its detection signatures, customer sources, published pricing, feature checklist, contract notes, migration playbook and offer, and run the same acquisition process against it without new development.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Business leads are not an incumbent acquisition registry.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Build configurable targets/signatures, permitted sources, pricing/parity and migration playbooks.

## Technical component

- [ ] Implement the module boundary and contracts for: TargetRegistry and authorised ingestion.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: No acquisition target/prospect/provenance/claims domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] targets, source_licenses, target_playbooks.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Target/source registry editor.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Target any provider's customers. EverOnn can define any incumbent provider as a target, with its detection signatures, customer sources, published pricing, feature checklist, contract notes, migration playbook and offer, and run the same acquisition process against it without new development. | TargetRegistry and authorised ingestion | Tenant-scoped end-to-end demonstration of the outcome |
| Build configurable targets/signatures, permitted sources, pricing/parity and migration playbooks. | targets, source_licenses, target_playbooks; Target/source registry editor | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Assisted classification shows evidence; no prohibited scraping | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] TargetRegistry and authorised ingestion.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Assisted classification shows evidence.
- [ ] no prohibited scraping.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-21](../../../requirements/AT.md#at-21) | Add a competitor target without code | A new target with signatures, sources, a dated pricing snapshot, feature checklist, contract notes and playbook is created and used to import prospects; stale facts are flagged | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-061](../../../requirements/US.md#us-061).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ACQ-001](../../../requirements/ACQ.md#acq-001) | Source-linked | 19.7 Customer acquisition (ACQ) |
| [ACQ-013](../../../requirements/ACQ.md#acq-013) | Plan allocation / source cross-reference | 19.7 Customer acquisition (ACQ) |
| [AT-21](../../../requirements/AT.md#at-21) | Source-linked | 25.2 Acceptance tests |
| [BO-10](../../../requirements/BO.md#bo-10) | Source-linked | 3.1 Business objectives |
| [BR-050](../../../requirements/BR.md#br-050) | Source-linked | 7.9 Customer acquisition and migration |
| [BRL-026](../../../requirements/BRL.md#brl-026) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-038](../../../requirements/BRL.md#brl-038) | Plan allocation / source cross-reference | 8. Business rules |
| [MIG-010](../../../requirements/MIG.md#mig-010) | Source-linked | 19.8 Migration (MIG) |
| [US-061](../../../requirements/US.md#us-061) | Source-linked | EP-13 Customer acquisition and migration |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ACQ-001](../../../requirements/ACQ.md#acq-001): ACQ-001 [P1] MUST provide a conquest target registry. A target records: the incumbent provider and the verticals it serves; its detection signatures (technology-list references, "powered by" credit patterns, hosting or domain fingerprints); the source lists and their terms and refresh dates; published pricing snapshots with as-of dates and source links; the feature checklist; contract and lock-in notes (term, renewal, termination fees, ownership of domain and content); known AI features; the migration playbook (MIG-010); offer templates; and status. New targets are created by configuration. Time-sensitive facts carry an as-of date and a review-by date and are flagged when stale (BRL-038).
- [ ] [ACQ-013](../../../requirements/ACQ.md#acq-013): ACQ-013 [P2] MAY monitor sources on a schedule (list refreshes within license, incumbent price and feature changes) and create review tasks.
- [ ] [BRL-026](../../../requirements/BRL.md#brl-026): BRL-026 | EverOnn wins clients by approaching businesses directly and persuading them to switch; it does not depend on an incumbent provider's cooperation, referrals or partnerships. | Acquisition | ACQ-001, ACQ-005.
- [ ] [BRL-038](../../../requirements/BRL.md#brl-038): BRL-038 | Market facts about providers (prices, features, customer counts, ownership) carry an as-of date and are refreshed before they are used in any sales material. | Marketing, sales | ACQ-001, ACQ-010.
- [ ] [MIG-010](../../../requirements/MIG.md#mig-010): MIG-010 [P1] MUST hold migration playbooks as data (steps, checks, templates, known incumbent quirks), linked from the target registry (ACQ-001) and selected automatically when a prospect's incumbent is known.

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

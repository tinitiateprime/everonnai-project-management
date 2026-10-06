# EVN-ACQ-054 - Build before asking

Project: EverOnnAI. Module: [Incumbent targets, prospects, outreach and savings evidence](../README.md). Source business requirement [BR-054](../../../requirements/BR.md#br-054).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Acquisition Manager + Product Owner + Counsel (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-SEC-101](../../15-security-privacy-compliance/tickets/EVN-SEC-101.md) |

## Business deliverable

Build before asking. Every prospect can be shown a private website preview and a demonstration configured with their own business details before any commitment.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Owners can generate private business drafts.

## Remaining delivery checklist

- [ ] Add prospect preview/demo lifecycle, provenance/consent, contact masking and claim-to-tenant linking.

## Technical component

- [ ] Implement the module boundary and contracts for: Preview adapter and prospect claim service.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: No acquisition target/prospect/provenance/claims domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] prospect_previews, demo_configs, claims.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Private demos and verified claim.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Build before asking. Every prospect can be shown a private website preview and a demonstration configured with their own business details before any commitment. | Preview adapter and prospect claim service | Tenant-scoped end-to-end demonstration of the outcome |
| Add prospect preview/demo lifecycle, provenance/consent, contact masking and claim-to-tenant linking. | prospect_previews, demo_configs, claims; Private demos and verified claim | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Permitted facts only; demos cannot activate real service | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Preview adapter and prospect claim service.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Permitted facts only.
- [ ] demos cannot activate real service.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-24](../../../requirements/AT.md#at-24) | Prospect preview and demonstration | A private, non-indexed preview and a demonstration agent built from the prospect's public business details are ready; nothing is published without owner approval and no call or text is placed without consent | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-064](../../../requirements/US.md#us-064).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ACQ-006](../../../requirements/ACQ.md#acq-006) | Source-linked | 19.7 Customer acquisition (ACQ) |
| [AT-24](../../../requirements/AT.md#at-24) | Source-linked | 25.2 Acceptance tests |
| [BO-2](../../../requirements/BO.md#bo-2) | Source-linked | 3.1 Business objectives |
| [BO-10](../../../requirements/BO.md#bo-10) | Source-linked | 3.1 Business objectives |
| [BR-054](../../../requirements/BR.md#br-054) | Source-linked | 7.9 Customer acquisition and migration |
| [BRL-006](../../../requirements/BRL.md#brl-006) | Plan allocation / source cross-reference | 8. Business rules |
| [ONB-012](../../../requirements/ONB.md#onb-012) | Source-linked | 12.2 Requirements |
| [US-064](../../../requirements/US.md#us-064) | Source-linked | EP-13 Customer acquisition and migration |
| [WEB-003](../../../requirements/WEB.md#web-003) | Source-linked | 18.3 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ACQ-006](../../../requirements/ACQ.md#acq-006): ACQ-006 [P1] MUST generate a personalized preview and demonstration from a prospect's own public business details: a private, non-indexed website preview using the preview engine (WEB-003), and a demonstration agent, on the prospect's business name, services, hours and handoff rules, that can be tried by chat or a call the prospect requests. Nothing is published without verified owner approval (BRL-006), and no call or text is placed to a prospect without a consent record (BRL-028). Previews expire automatically.
- [ ] [BRL-006](../../../requirements/BRL.md#brl-006): BRL-006 | A preview site stays private, and shows no real phone number, until ownership is verified and the owner approves. | Website engine | ONB-002, WEB-003.
- [ ] [ONB-012](../../../requirements/ONB.md#onb-012): ONB-012 [P1] MUST support a switching claim: when a preview originates from an acquisition prospect, it is pre-populated from the prospect's public data with the source recorded, the prospect and tenant are linked, and a migration project (MIG-001) is opened as soon as the incumbent is known.
- [ ] [WEB-003](../../../requirements/WEB.md#web-003): WEB-003 [P1] MUST keep previews private and non-indexable (noindex, unguessable URLs, no real phone or address exposure per ONB-002) until verification and owner approval; preview TTL and cleanup jobs apply to unclaimed prospects.

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

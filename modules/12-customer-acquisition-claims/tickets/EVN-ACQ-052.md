# EVN-ACQ-052 - Qualify and track every prospect

Project: EverOnnAI. Module: [Incumbent targets, prospects, outreach and savings evidence](../README.md). Source business requirement [BR-052](../../../requirements/BR.md#br-052).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Acquisition Manager + Product Owner + Counsel (proposed role; named person unassigned) |
| Priority / phase | Should / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-SEC-101](../../15-security-privacy-compliance/tickets/EVN-SEC-101.md) |

## Business deliverable

Qualify and track every prospect. Prospects are scored on enquiry-handling gap, current spend, migration complexity and fit, and move through defined pipeline stages with an owner and a next action.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Lead statuses are not an acquisition funnel.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Add explainable scoring, stages, owners, next actions and contract/migration complexity.

## Technical component

- [ ] Implement the module boundary and contracts for: Scoring rules, transitions and audit.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: No acquisition target/prospect/provenance/claims domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] prospect_scores, stages, activities.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Prospect board, qualification and next actions.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Qualify and track every prospect. Prospects are scored on enquiry-handling gap, current spend, migration complexity and fit, and move through defined pipeline stages with an owner and a next action. | Scoring rules, transitions and audit | Tenant-scoped end-to-end demonstration of the outcome |
| Add explainable scoring, stages, owners, next actions and contract/migration complexity. | prospect_scores, stages, activities; Prospect board, qualification and next actions | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Explain suggestions; reviewers can override | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Scoring rules, transitions and audit.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Explain suggestions.
- [ ] reviewers can override.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-22](../../../requirements/AT.md#at-22) | Prospect import with provenance and source-term controls | Records keep source, date and evidence; duplicates are merged; fields barred by source terms cannot be used for outreach; unverified facts show as unknown; the pipeline records stage, owner and next action | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-062](../../../requirements/US.md#us-062).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ACQ-004](../../../requirements/ACQ.md#acq-004) | Source-linked | 19.7 Customer acquisition (ACQ) |
| [ACQ-005](../../../requirements/ACQ.md#acq-005) | Source-linked | 19.7 Customer acquisition (ACQ) |
| [AT-22](../../../requirements/AT.md#at-22) | Source-linked | 25.2 Acceptance tests |
| [BO-10](../../../requirements/BO.md#bo-10) | Source-linked | 3.1 Business objectives |
| [BR-052](../../../requirements/BR.md#br-052) | Source-linked | 7.9 Customer acquisition and migration |
| [BRL-026](../../../requirements/BRL.md#brl-026) | Plan allocation / source cross-reference | 8. Business rules |
| [US-062](../../../requirements/US.md#us-062) | Source-linked | EP-13 Customer acquisition and migration |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ACQ-004](../../../requirements/ACQ.md#acq-004): ACQ-004 [P1] SHOULD provide qualification and scoring using transparent, adjustable rules (signals of an enquiry-handling gap such as no chat or online booking, size of current spend, migration complexity, regulatory load, location and size). Scores explain their factors, never assert facts, and can be overridden by a person.
- [ ] [ACQ-005](../../../requirements/ACQ.md#acq-005): ACQ-005 [P1] MUST run a pipeline with defined stages (identified, verified, previewed, contacted, engaged, demonstrated, proposed, agreed, migrating, live, retained or lost), an owner and a next action for each prospect, an audit trail, and views by target, vertical, brand and channel.
- [ ] [BRL-026](../../../requirements/BRL.md#brl-026): BRL-026 | EverOnn wins clients by approaching businesses directly and persuading them to switch; it does not depend on an incumbent provider's cooperation, referrals or partnerships. | Acquisition | ACQ-001, ACQ-005.

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

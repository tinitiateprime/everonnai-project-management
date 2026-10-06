# EVN-MIG-057 - Respect the customer's contract and ownership

Project: EverOnnAI. Module: [Authorised migration, service continuity and offboarding](../README.md). Source business requirement [BR-057](../../../requirements/BR.md#br-057).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Migration Specialist + Operations Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-OPS-103](../../18-reliability-deployment-scale/tickets/EVN-OPS-103.md) |

## Business deliverable

Respect the customer's contract and ownership. Switching respects the customer's contract and ownership: the incumbent's term, notice and fees are recorded and included in the comparison, nothing is cancelled without the customer's written authorization, and only assets the customer owns or may export are moved.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] No contract/asset-rights workflow exists.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Record notice/fees/renewal and written authority; move only owned/authorised exports and obtain sign-off.

## Technical component

- [ ] Implement the module boundary and contracts for: Rights checks, schedule constraints and audit.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Website snapshot rollback only; no whole-business migration inventory/rights/cutover model.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] contracts, asset_rights, authorisations.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Contract/ownership/cancellation review.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Respect the customer's contract and ownership. Switching respects the customer's contract and ownership: the incumbent's term, notice and fees are recorded and included in the comparison, nothing is cancelled without the customer's written authorization, and only assets the customer owns or may export are moved. | Rights checks, schedule constraints and audit | Tenant-scoped end-to-end demonstration of the outcome |
| Record notice/fees/renewal and written authority; move only owned/authorised exports and obtain sign-off. | contracts, asset_rights, authorisations; Contract/ownership/cancellation review | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | N/A; rights and cancellation authority need human decisions | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Rights checks, schedule constraints and audit.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

N/A; rights and cancellation authority need human decisions. AI is outside this ticket's runtime scope.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-25](../../../requirements/AT.md#at-25) | Savings comparison and claims file | The calculator shows current cost, contract and termination fees, retained services and break-even; unconfirmed inputs are labeled; a claim cannot be used until approved and unexpired | Full source scenario not evidenced; client acceptance pending |
| [AT-26](../../../requirements/AT.md#at-26) | End-to-end migration without service loss | Content is imported and reviewed; domain ownership is verified and the domain transferred or repointed; email continues; forwarded numbers are verified; a parallel run and cut-over happen; rollback is exercised; no calls or form leads are lost during cut-over | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-065](../../../requirements/US.md#us-065), [US-067](../../../requirements/US.md#us-067).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ACQ-007](../../../requirements/ACQ.md#acq-007) | Source-linked | 19.7 Customer acquisition (ACQ) |
| [AT-25](../../../requirements/AT.md#at-25) | Source-linked | 25.2 Acceptance tests |
| [AT-26](../../../requirements/AT.md#at-26) | Source-linked | 25.2 Acceptance tests |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BO-10](../../../requirements/BO.md#bo-10) | Source-linked | 3.1 Business objectives |
| [BR-057](../../../requirements/BR.md#br-057) | Source-linked | 7.9 Customer acquisition and migration |
| [BRL-030](../../../requirements/BRL.md#brl-030) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-031](../../../requirements/BRL.md#brl-031) | Plan allocation / source cross-reference | 8. Business rules |
| [MIG-003](../../../requirements/MIG.md#mig-003) | Source-linked | 19.8 Migration (MIG) |
| [MIG-006](../../../requirements/MIG.md#mig-006) | Source-linked | 19.8 Migration (MIG) |
| [US-065](../../../requirements/US.md#us-065) | Source-linked | EP-13 Customer acquisition and migration |
| [US-067](../../../requirements/US.md#us-067) | Source-linked | EP-13 Customer acquisition and migration |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ACQ-007](../../../requirements/ACQ.md#acq-007): ACQ-007 [P1] MUST provide an honest savings comparison calculator. Inputs are the prospect's current monthly cost items, contract term and early-termination fee, the services the prospect must keep, payment-processing costs, and, for providers that charge a percentage of orders, the order volume. Each input is tagged prospect-confirmed, public or estimate. Outputs are total current cost, total EverOnn cost (plan, expected usage and overages), break-even, and clear disclosures. A savings claim may be shared only when its key inputs are confirmed or are clearly labeled as estimates (BRL-030).
- [ ] [BRL-030](../../../requirements/BRL.md#brl-030): BRL-030 | Savings and comparison claims rest on figures the prospect has confirmed or on clearly labeled estimates with a documented calculation; statements about competitors are truthful, factual and never imply an affiliation. | Marketing, sales | ACQ-007, ACQ-010.
- [ ] [BRL-031](../../../requirements/BRL.md#brl-031): BRL-031 | Switching respects the customer's contract and ownership: the incumbent's term, notice and fees are asked for and included in the comparison, nothing is cancelled on the customer's behalf without written authorization, and only assets the customer owns or may export are migrated. | Migration | MIG-006, MIG-003, MIG-007.
- [ ] [MIG-003](../../../requirements/MIG.md#mig-003): MIG-003 [P1] MUST provide a domain workflow: verify who is the registrant and who controls the registrar account; guide the owner through unlocking the domain and obtaining the authorization code, or through repointing DNS where transfer is not needed; copy mail and verification records before any change; confirm that email continues; issue certificates on the new host; cut over only after the checks pass; roll back within a stated time if a check fails.
- [ ] [MIG-006](../../../requirements/MIG.md#mig-006): MIG-006 [P1] MUST record the incumbent contract: term, renewal date, notice requirement, early-termination fee and the customer's confirmation. The platform schedules cut-over around notice dates, never cancels or instructs cancellation on the client's behalf without written authorization, and supplies a cancellation-notice template for the client to send.

## Existing code / check evidence

- `features/website-studio/releases.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/website-code.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Website rollback does not preserve registrar/mail/phone contracts or provide authorised import, parallel run, hypercare and business offboarding.

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-OPS-103](../../18-reliability-deployment-scale/tickets/EVN-OPS-103.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.

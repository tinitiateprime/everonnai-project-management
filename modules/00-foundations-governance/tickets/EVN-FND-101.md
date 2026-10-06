# EVN-FND-101 - Approve the delivery scope and architecture baseline

Project: EverOnnAI. Module: [Foundations, scope and architecture decisions](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Decision required |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Product Owner + Technical Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P0 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | None; independent entry point |

## Business deliverable

Approve the delivery scope and architecture baseline.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Current Next.js/Supabase/Amplify is documented and functioning locally.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Obtain signed D-2/D-5/D-7/D-8 decisions and the generated-code renderer disposition; preserve existing records in any migration.

## Technical component

- [ ] Implement the module boundary and contracts for: Architecture review, contract baseline and migration plan.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Private everonn schema, guarded migrations and shape-preserving stores.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] ADR register and migration inventory.
- [ ] no unapproved production DDL.
- [ ] Version the relevant evidence/registers and keep customer secrets out of the documentation repository.

## UI

- [ ] Client architecture/scope approval pack.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Approve the delivery scope and architecture baseline. | Architecture review, contract baseline and migration plan | Tenant-scoped end-to-end demonstration of the outcome |
| Obtain signed D-2/D-5/D-7/D-8 decisions and the generated-code renderer disposition; preserve existing records in any migration. | ADR register and migration inventory; no unapproved production DDL; Client architecture/scope approval pack | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Retain current Gemini direction until evaluated ADR changes are approved | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Architecture review, contract baseline and migration plan.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Retain current Gemini direction until evaluated ADR changes are approved.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

No dedicated source AT is assigned to this enabling/extension ticket. Define a ticket-specific acceptance report before closing it; the module and release gates still apply.

Source stories: No dedicated source story; business/enabling outcome above is the acceptance brief.

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AL-01](../../../requirements/AL.md#al-01) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-02](../../../requirements/AL.md#al-02) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-03](../../../requirements/AL.md#al-03) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-04](../../../requirements/AL.md#al-04) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-05](../../../requirements/AL.md#al-05) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-06](../../../requirements/AL.md#al-06) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-07](../../../requirements/AL.md#al-07) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-08](../../../requirements/AL.md#al-08) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-09](../../../requirements/AL.md#al-09) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-10](../../../requirements/AL.md#al-10) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-11](../../../requirements/AL.md#al-11) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-12](../../../requirements/AL.md#al-12) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-13](../../../requirements/AL.md#al-13) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-14](../../../requirements/AL.md#al-14) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-15](../../../requirements/AL.md#al-15) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-16](../../../requirements/AL.md#al-16) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-17](../../../requirements/AL.md#al-17) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-18](../../../requirements/AL.md#al-18) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-19](../../../requirements/AL.md#al-19) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-20](../../../requirements/AL.md#al-20) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-21](../../../requirements/AL.md#al-21) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AL-22](../../../requirements/AL.md#al-22) | Plan allocation / source cross-reference | A.4 Findings that need a decision or a correction |
| [AR-001](../../../requirements/AR.md#ar-001) | Source-linked | 11.7 Architecture requirements |
| [AR-008](../../../requirements/AR.md#ar-008) | Source-linked | 11.7 Architecture requirements |
| [ASM-01](../../../requirements/ASM.md#asm-01) | Plan allocation / source cross-reference | 9.1 Assumptions |
| [ASM-02](../../../requirements/ASM.md#asm-02) | Plan allocation / source cross-reference | 9.1 Assumptions |
| [ASM-03](../../../requirements/ASM.md#asm-03) | Plan allocation / source cross-reference | 9.1 Assumptions |
| [ASM-04](../../../requirements/ASM.md#asm-04) | Plan allocation / source cross-reference | 9.1 Assumptions |
| [ASM-05](../../../requirements/ASM.md#asm-05) | Plan allocation / source cross-reference | 9.1 Assumptions |
| [ASM-06](../../../requirements/ASM.md#asm-06) | Plan allocation / source cross-reference | 9.1 Assumptions |
| [ASM-07](../../../requirements/ASM.md#asm-07) | Plan allocation / source cross-reference | 9.1 Assumptions |
| [ASM-08](../../../requirements/ASM.md#asm-08) | Plan allocation / source cross-reference | 9.1 Assumptions |
| [ASM-09](../../../requirements/ASM.md#asm-09) | Plan allocation / source cross-reference | 9.1 Assumptions |
| [BP-1](../../../requirements/BP.md#bp-1) | Plan allocation / source cross-reference | 6.1 Process map |
| [BP-2](../../../requirements/BP.md#bp-2) | Plan allocation / source cross-reference | 6.1 Process map |
| [BP-3](../../../requirements/BP.md#bp-3) | Plan allocation / source cross-reference | 6.1 Process map |
| [BP-4](../../../requirements/BP.md#bp-4) | Plan allocation / source cross-reference | 6.1 Process map |
| [BP-5](../../../requirements/BP.md#bp-5) | Plan allocation / source cross-reference | 6.1 Process map |
| [BP-6](../../../requirements/BP.md#bp-6) | Plan allocation / source cross-reference | 6.1 Process map |
| [BP-7](../../../requirements/BP.md#bp-7) | Plan allocation / source cross-reference | 6.1 Process map |
| [BP-8](../../../requirements/BP.md#bp-8) | Plan allocation / source cross-reference | 6.1 Process map |
| [BP-9](../../../requirements/BP.md#bp-9) | Plan allocation / source cross-reference | 6.1 Process map |
| [CON-01](../../../requirements/CONSTRAINTS.md#con-01) | Source-linked | 9.2 Constraints |
| [CON-02](../../../requirements/CONSTRAINTS.md#con-02) | Source-linked | 9.2 Constraints |
| [CON-03](../../../requirements/CONSTRAINTS.md#con-03) | Source-linked | 9.2 Constraints |
| [CON-04](../../../requirements/CONSTRAINTS.md#con-04) | Source-linked | 9.2 Constraints |
| [CON-05](../../../requirements/CONSTRAINTS.md#con-05) | Source-linked | 9.2 Constraints |
| [CON-06](../../../requirements/CONSTRAINTS.md#con-06) | Source-linked | 9.2 Constraints |
| [CON-07](../../../requirements/CONSTRAINTS.md#con-07) | Source-linked | 9.2 Constraints |
| [CON-08](../../../requirements/CONSTRAINTS.md#con-08) | Source-linked | 9.2 Constraints |
| [D-1](../../../requirements/D.md#d-1) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-2](../../../requirements/D.md#d-2) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-3](../../../requirements/D.md#d-3) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-4](../../../requirements/D.md#d-4) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-5](../../../requirements/D.md#d-5) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-6](../../../requirements/D.md#d-6) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-7](../../../requirements/D.md#d-7) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-8](../../../requirements/D.md#d-8) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-9](../../../requirements/D.md#d-9) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-10](../../../requirements/D.md#d-10) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-11](../../../requirements/D.md#d-11) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-12](../../../requirements/D.md#d-12) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-13](../../../requirements/D.md#d-13) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-14](../../../requirements/D.md#d-14) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-15](../../../requirements/D.md#d-15) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-16](../../../requirements/D.md#d-16) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-17](../../../requirements/D.md#d-17) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-18](../../../requirements/D.md#d-18) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-19](../../../requirements/D.md#d-19) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-20](../../../requirements/D.md#d-20) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-21](../../../requirements/D.md#d-21) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-22](../../../requirements/D.md#d-22) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-23](../../../requirements/D.md#d-23) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-24](../../../requirements/D.md#d-24) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-25](../../../requirements/D.md#d-25) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-26](../../../requirements/D.md#d-26) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-27](../../../requirements/D.md#d-27) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-28](../../../requirements/D.md#d-28) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-29](../../../requirements/D.md#d-29) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-30](../../../requirements/D.md#d-30) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-31](../../../requirements/D.md#d-31) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-32](../../../requirements/D.md#d-32) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-33](../../../requirements/D.md#d-33) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [D-34](../../../requirements/D.md#d-34) | Plan allocation / source cross-reference | 26.3 Open decisions register |
| [DEP-01](../../../requirements/DEP.md#dep-01) | Plan allocation / source cross-reference | 9.3 Dependencies |
| [DEP-02](../../../requirements/DEP.md#dep-02) | Plan allocation / source cross-reference | 9.3 Dependencies |
| [DEP-03](../../../requirements/DEP.md#dep-03) | Plan allocation / source cross-reference | 9.3 Dependencies |
| [DEP-04](../../../requirements/DEP.md#dep-04) | Plan allocation / source cross-reference | 9.3 Dependencies |
| [DEP-05](../../../requirements/DEP.md#dep-05) | Plan allocation / source cross-reference | 9.3 Dependencies |
| [DEP-06](../../../requirements/DEP.md#dep-06) | Plan allocation / source cross-reference | 9.3 Dependencies |
| [DEP-07](../../../requirements/DEP.md#dep-07) | Plan allocation / source cross-reference | 9.3 Dependencies |
| [DEP-08](../../../requirements/DEP.md#dep-08) | Plan allocation / source cross-reference | 9.3 Dependencies |
| [DEP-09](../../../requirements/DEP.md#dep-09) | Plan allocation / source cross-reference | 9.3 Dependencies |
| [DEP-10](../../../requirements/DEP.md#dep-10) | Plan allocation / source cross-reference | 9.3 Dependencies |
| [DEP-11](../../../requirements/DEP.md#dep-11) | Plan allocation / source cross-reference | 9.3 Dependencies |
| [DEP-12](../../../requirements/DEP.md#dep-12) | Plan allocation / source cross-reference | 9.3 Dependencies |
| [EP-01](../../../requirements/EP.md#ep-01) | Plan allocation / source cross-reference | EP-01 Onboarding and claim |
| [EP-02](../../../requirements/EP.md#ep-02) | Plan allocation / source cross-reference | EP-02 Knowledge and agent control |
| [EP-03](../../../requirements/EP.md#ep-03) | Plan allocation / source cross-reference | EP-03 AI voice front desk |
| [EP-04](../../../requirements/EP.md#ep-04) | Plan allocation / source cross-reference | EP-04 Chat and messaging |
| [EP-05](../../../requirements/EP.md#ep-05) | Plan allocation / source cross-reference | EP-05 Human operations and the Live Agent Desk |
| [EP-06](../../../requirements/EP.md#ep-06) | Plan allocation / source cross-reference | EP-06 Inbox, booking and follow-up |
| [EP-07](../../../requirements/EP.md#ep-07) | Plan allocation / source cross-reference | EP-07 Websites |
| [EP-08](../../../requirements/EP.md#ep-08) | Plan allocation / source cross-reference | EP-08 Billing, plans and cost |
| [EP-09](../../../requirements/EP.md#ep-09) | Plan allocation / source cross-reference | EP-09 Administration and operations |
| [EP-10](../../../requirements/EP.md#ep-10) | Plan allocation / source cross-reference | EP-10 Compliance, security and privacy |
| [EP-11](../../../requirements/EP.md#ep-11) | Plan allocation / source cross-reference | EP-11 Integrations, scale and ownership |
| [EP-12](../../../requirements/EP.md#ep-12) | Plan allocation / source cross-reference | EP-12 Verticals and brands |
| [EP-13](../../../requirements/EP.md#ep-13) | Plan allocation / source cross-reference | EP-13 Customer acquisition and migration |
| [EP-14](../../../requirements/EP.md#ep-14) | Plan allocation / source cross-reference | EP-14 Restaurant ordering |
| [RK-01](../../../requirements/RK.md#rk-01) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-02](../../../requirements/RK.md#rk-02) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-03](../../../requirements/RK.md#rk-03) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-04](../../../requirements/RK.md#rk-04) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-05](../../../requirements/RK.md#rk-05) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-06](../../../requirements/RK.md#rk-06) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-07](../../../requirements/RK.md#rk-07) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-08](../../../requirements/RK.md#rk-08) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-09](../../../requirements/RK.md#rk-09) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-10](../../../requirements/RK.md#rk-10) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-11](../../../requirements/RK.md#rk-11) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-12](../../../requirements/RK.md#rk-12) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-13](../../../requirements/RK.md#rk-13) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-14](../../../requirements/RK.md#rk-14) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-15](../../../requirements/RK.md#rk-15) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-16](../../../requirements/RK.md#rk-16) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-17](../../../requirements/RK.md#rk-17) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-18](../../../requirements/RK.md#rk-18) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-19](../../../requirements/RK.md#rk-19) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-20](../../../requirements/RK.md#rk-20) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-21](../../../requirements/RK.md#rk-21) | Plan allocation / source cross-reference | 13.1 Risk register |
| [RK-22](../../../requirements/RK.md#rk-22) | Plan allocation / source cross-reference | 13.1 Risk register |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [AR-001](../../../requirements/AR.md#ar-001): AR-001 [P0] MUST deliver a written architecture decision record (ADR) set covering every "Decision" in this document, before P1 build starts.
- [ ] [AR-008](../../../requirements/AR.md#ar-008): AR-008 [P0] SHOULD produce a C4 model (context, container, component) and a data-flow diagram per channel, kept in the repo and updated per release.

## Existing code / check evidence

- `CODE_PROFILE.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `PROJECT_DATA_FLOW.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `CLIENT_TECHNICAL_QA.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `README.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).

## Blockers and boundaries

Module risk: Unapproved divergence from the RHEL/Podman/MariaDB baseline and undefined acceptance ownership.

Dependencies: None; independent entry point. A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.

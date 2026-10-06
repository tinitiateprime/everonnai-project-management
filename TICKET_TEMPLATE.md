# Ticket structure and update rules

Each ticket represents a business outcome or a clearly labelled delivery enabler. Update the existing ticket when its outcome changes; create a new stable ID only when scope is genuinely added. Keep module/requirement/index links consistent.

## Required fields

- Project, parent module, stable ticket ID and business deliverable.
- Engineering status, separate QA/deployment/client acceptance dispositions.
- Source priority/phase, proposed/named accountable owner, estimate and dependencies.
- Current slice with code/check evidence, remaining scope and source IDs.
- Technical component, DB, UI, Translate/business mapping, backend services, AI component, testing/QA and deployment.
- Applicable source acceptance scenarios, failure/security/cost boundaries and handover.

## Reusable checklist

### Business deliverable

- [ ] State the client outcome and measurable acceptance criteria.
- [ ] Link exact source records; distinguish source mappings from plan allocations.

### Technical component

- [ ] Identify module boundaries, contracts, state transitions and dependencies.

### DB

- [ ] Distinguish existing entities from proposed migrations; review scope/indexes/retention/rollback.
- [ ] If no production schema change is needed, explain what evidence/state is versioned instead.

### UI

- [ ] Define role-aware journeys, visible state, responsive/a11y behaviour and error recovery.

### Translate - business-to-technical mapping

- [ ] Map business promise > records/services/UI > QA evidence. This is not localisation.

### Backend services

- [ ] Define schemas/auth, retries/uncertain outcomes, receipts and reconciliation; justify N/A.

### AI component

- [ ] Define approved inputs, instruction/tool versions, budgets, safety and real evaluations; justify N/A.

### Testing / QA

- [ ] Record case, environment, version, result, evidence, defect/disposition and reviewer.
- [ ] Separate mocks/unit checks from real model/audio/provider and customer UAT evidence.

### Deployment

- [ ] Record migration/config, staged promotion, actual hosted check, monitoring and rollback.
- [ ] For documentation-only tickets, record reviewed Git publication rather than an app deployment.

### Client acceptance

- [ ] Named client reviewer signs the actual version, date and agreed residual scope.

## Status transition rules

Planned > Partial > Implemented describes engineering progress only. QA passed and deployed require their own evidence. Client accepted requires dated sign-off. Reopen or add a defect when a previously verified criterion fails. Source changes and approved deferrals must be written down, not hidden by checking a parent box.

Do not put credentials, private transcripts or personal data in ticket evidence. Use authorised external evidence references and sanitised summaries. Do not mirror every implementation line with unnecessary tests; test meaningful outcomes, boundaries and failure paths.

# Risks, gaps and launch blockers

Risks are open until mitigation evidence and residual-risk approval are recorded. Role owners below are proposed; no named person or approval is implied.

## Current project blockers

| Risk / gap | Consequence | Mitigation / linked work | Accountable role | Release gate |
| --- | --- | --- | --- | --- |
| Unapproved architecture deviations | Delivery may violate platform contract and recovery/ownership expectations | FND-101; D-2/D-5/D-7/D-8 and renderer ADR; preserve data in migration | Technical Lead + EverOnn owner | Resolve before production architecture commitment |
| Browser voice presented as telephone service | Calls may not be answered/transferred as promised | VOX-101 and BR-001/009; both carrier/audio/failure traces | Voice Lead + SRE | Real phone acceptance before phone launch |
| No independent ownership verification / incomplete preview protection | Unauthorised or misleading public sites | BR-015/019; proof, masking, expiry, abuse/takedown controls | Backend + Security Lead | No unverified public publish |
| Generation timeout/process loss | Paid work/progress can be lost and owner sees generic errors | WEB-101; durable checkpoints, per-stage timeout/retry/cancel/resume and budgets | Backend + AI Lead | Kill/restart/resume and failure recovery demo |
| Grounding QA rejects a draft | Knowledge may be adequate but output/parser/validation details still fail | Structured validation reports and bounded repairs; preserve facts and explain actionable failure | AI + Frontend Lead | Real facts/unknown/repair scenarios; no weakening safety to hide failure |
| Premium visuals unaccepted / saved legacy site | Technically valid output can still look poor or an old publication remains live | WEB-102; service art direction, real screenshots, owner review and approved release replacement | Design/Frontend + Client owner | Actual draft/live visual sign-off |
| Draft knowledge or preferences alter live behaviour | Incorrect assistant promises despite an approved site | KNW-102; immutable config/KB publications and conversation version pinning | AI + Backend Lead | Published/draft isolation and rollback tests |
| No staffed desk/authority enforcement | False human guarantees, tenant/audio leaks or unauthorised commitments | HIL/DSK tickets; grants/audio topology, staffing, rules and measured offer handling | Operations + Voice/Security Leads | Staffing and real privacy/transfer/authority tests |
| No subscription/entitlement enforcement | Revenue leakage and misleading customer plans | BR-040/041/043; payments, invoices, quota policy and claims reconciliation | Billing + Product Lead | Real sandbox billing/overage/limit and pricing review |
| Provider usage evidence incomplete across channels/operators | Margin estimates may appear more certain than actual costs | BR-042; coverage and estimates separate from invoices; operator/all-provider reconciliation | Finance + Backend Lead | Source/coverage/cost report review |
| Legal/consent/security requirements unfinished | Recording, messaging, retention or outreach shipped without approved policy | SEC/COM and D-3/D-10/D-22/D-24; counsel/provider review and technical fail-closed controls | Security + EverOnn/counsel | Approved policy and executed consent/privacy cases |
| SLO/capacity/restore unproven | Outages or scaling promises unsupported | OPS-103/104; load/soak/chaos and restore evidence | SRE + QA Lead | Agreed targets measured in realistic conditions |
| Current app work not deployed | GitHub planning works while hosted customer UI lacks current feature | PJM-101 and deployment gates; promote reviewed app separately | Platform Lead | Hosted workflow verification |
| Source licences/claims/connector approvals missing | Acquisition or migration promise cannot be delivered safely | ACQ/MIG/INT readiness and licence registers, dated substantiation | Acquisition + Product/counsel | No outreach/claim/connector promise before approval |
| Restaurant/regulated scope exceeds readiness | Unsafe orders, lost kitchen receipt or unsupported regulated data flow | ORD/VRT/SEC readiness gates and pilot evidence | Vertical + QA/Security Leads | Controlled pilot and agreement-chain review |

## Source risk register

| Source ID | Risk | Likelihood | Impact | Source mitigation | Source owner | Disposition |
| --- | --- | --- | --- | --- | --- | --- |
| [RK-01](requirements/RK.md#rk-01) | Voice response time or quality falls short of target on real phone audio | Medium | High | Early test on real calls with several vendors; backup vendor option; continuous monitoring | Studio, product owner | Open; residual risk not approved |
| [RK-02](requirements/RK.md#rk-02) | Voice and operator costs erode margin | High | High | Cost model in foundations; allowances and caps; model tiering; per-client circuit breakers; add-on pricing for operators | Owner, finance | Open; residual risk not approved |
| [RK-03](requirements/RK.md#rk-03) | The AI states something untrue or unsafe and harms a client or caller | Medium | Critical | Approved-knowledge-only rule; hard guardrails in code; evaluation gates; human safety net; clear "technology not services" terms | Product owner | Open; residual risk not approved |
| [RK-04](requirements/RK.md#rk-04) | Regulatory exposure on texting consent, call recording and AI disclosure | Medium | High | Counsel review before the pilot; conservative defaults; consent ledger that fails closed; outbound disabled | Owner, counsel | Open; residual risk not approved |
| [RK-05](requirements/RK.md#rk-05) | Carrier registration delays block texting | High | Medium | Register early; toll-free fallback; set client expectations | Studio | Open; residual risk not approved |
| [RK-06](requirements/RK.md#rk-06) | Fraud or abuse of previews and numbers | Medium | High | Ownership verification before real numbers are used; caps and kill switch | Studio | Open; residual risk not approved |
| [RK-07](requirements/RK.md#rk-07) | Another client's data is exposed | Low | Critical | Structural isolation, continuous tests, independent penetration test | Studio | Open; residual risk not approved |
| [RK-08](requirements/RK.md#rk-08) | Business-data sources change their terms | Medium | Medium | Use official interfaces first; manual entry fallback | Product owner | Open; residual risk not approved |
| [RK-09](requirements/RK.md#rk-09) | Dependence on the studio | Medium | High | Ownership clauses; documentation; EverOnn-owned accounts; paired handover | Owner | Open; residual risk not approved |
| [RK-10](requirements/RK.md#rk-10) | Scope grows across six product areas | High | Medium | Phase gates; Must-only pilot; change control | Product owner | Open; residual risk not approved |
| [RK-11](requirements/RK.md#rk-11) | Operator staffing and cost are higher than planned because more calls reach a human | Medium | High | Start with owner mode and a small pilot pool; report escalation rate; improve knowledge to reduce escalations | Operations lead | Open; residual risk not approved |
| [RK-12](requirements/RK.md#rk-12) | An operator greets a caller as the wrong business or shows the wrong client's data | Medium | High | Line identification with an unknown-line safeguard; one client per screen; per-client grants and training; quality sampling of greetings | Operations lead | Open; residual risk not approved |
| [RK-13](requirements/RK.md#rk-13) | Search penalty for mass-generated sites | Medium | High | Unique content per site; owner review; policy against thin or duplicate pages | Product owner | Open; residual risk not approved |
| [RK-14](requirements/RK.md#rk-14) | Public claims or plan descriptions drift from what the platform delivers | Medium | High | Single source of plan data; evidence policy; release checks on published claims | Product owner | Open; residual risk not approved |
| [RK-15](requirements/RK.md#rk-15) | Incumbents' AI improves quickly (voice and messaging from marketing providers, health-care and field-service vendors, restaurant AI partnerships) | High | Medium | Compete on vertical depth, price, migration ease and ownership; refresh market facts; never assume an empty market | Product owner | Open; residual risk not approved |
| [RK-16](requirements/RK.md#rk-16) | Outreach breaches email, calling, texting or privacy rules | Medium | High | Rule-controlled console; counsel review; manually dialed calls only; one suppression list across brands | Owner, counsel | Open; residual risk not approved |
| [RK-17](requirements/RK.md#rk-17) | Data-source terms restrict use of technology-detection lists | Medium | Medium | Written confirmation of permitted uses; never use list phone numbers; combine with own research and inbound sources | Product owner | Open; residual risk not approved |
| [RK-18](requirements/RK.md#rk-18) | A migration causes an outage (email, domain, calls, search ranking) for a switching client | Medium | High | Asset checklist; parallel run; rollback and hypercare; verify domain ownership first | Studio, operations | Open; residual risk not approved |
| [RK-19](requirements/RK.md#rk-19) | Regulated verticals create liability | Medium | High | Readiness gate; compliance profiles; business associate agreement chain for health care; later waves | Owner, counsel | Open; residual risk not approved |
| [RK-20](requirements/RK.md#rk-20) | Restaurant orders are wrong or lost, or point-of-sale access is slow | High | High | Staff-accept screen and printer first; readback; human fallback; three-restaurant pilot with accuracy gates; connections as access is granted | Product owner | Open; residual risk not approved |
| [RK-21](requirements/RK.md#rk-21) | Brand confusion, misleading claims or trademark conflict across vertical brands | Medium | High | Contracting entity on every brand; claims register; trademark clearance; consistent terms | Owner, counsel | Open; residual risk not approved |
| [RK-22](requirements/RK.md#rk-22) | Switching friction (contracts, termination fees, lock-in) slows conversion | High | Medium | Start with month-to-month incumbents; contract-aware comparison; migration service; time go-live to notice dates | Acquisition manager | Open; residual risk not approved |

## Residual-risk review

- [ ] Assign a named owner and affected ticket/requirement IDs.
- [ ] Record mitigation, test/runbook evidence and remaining exposure.
- [ ] Agree a decision deadline and escalation path.
- [ ] Record client/product acceptance of residual risk where allowed; change scope if a Must criterion cannot be met.
- [ ] Reassess on provider, policy, model, pack, architecture or launch-scope changes.

Source alignment conflicts and review gating are listed in [SOURCE_ISSUES.md](SOURCE_ISSUES.md). No hypothetical extra compliance programme is being introduced here; these are source-specified delivery responsibilities and observed current gaps.

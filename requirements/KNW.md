# KNW - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## KNW-001

Assigned delivery tickets: [EVN-KNW-020](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-020.md), [EVN-KNW-102](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-102.md).

**Primary source:** TECH section 13.1 Business profile (structured facts); extraction row 781.

**Source record:** KNW-001 [P1] MUST store the profile as a versioned, schema-validated JSON document (JSON Schema published in the repo) plus normalized tables for query. Each save creates an immutable version; agents run against a published version, never a draft.

## KNW-002

Assigned delivery tickets: [EVN-AIQ-104](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-104.md).

**Primary source:** TECH section 13.1 Business profile (structured facts); extraction row 782.

**Source record:** KNW-002 [P1] MUST support a vertical template per trade (Appendix E) that seeds the profile, intake slots, triage rules, sample FAQs and guardrails. Templates are data, editable by EverOnn staff without deploys.

## KNW-003

Assigned delivery tickets: [EVN-KNW-101](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-101.md).

**Primary source:** TECH section 13.2 Unstructured knowledge (RAG); extraction row 784.

**Source record:** KNW-003 [P1] MUST ingest: pasted FAQs, uploaded PDFs/DOCX/TXT, the tenant's website pages, and structured "custom Q&A" pairs. Each source has status, last-ingested time, and owner approval state.

## KNW-004

Assigned delivery tickets: [EVN-KNW-101](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-101.md).

**Primary source:** TECH section 13.2 Unstructured knowledge (RAG); extraction row 785.

**Source record:** KNW-004 [P1] MUST chunk, embed and index knowledge per tenant with metadata (source, version, section, language). Retrieval MUST be tenant-filtered at the query layer, top-k limited, with a relevance threshold: below threshold the agent MUST treat the answer as unknown (KNW-007).

## KNW-005

Assigned delivery tickets: [EVN-KNW-020](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-020.md), [EVN-KNW-102](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-102.md).

**Primary source:** TECH section 13.2 Unstructured knowledge (RAG); extraction row 786.

**Source record:** KNW-005 [P1] MUST support owner approval of every KB item before it becomes agent-visible, with diff view on edits. Auto-imported content enters as pending.

## KNW-006

Assigned delivery tickets: [EVN-KNW-101](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-101.md).

**Primary source:** TECH section 13.2 Unstructured knowledge (RAG); extraction row 787.

**Source record:** KNW-006 [P1] SHOULD detect stale or conflicting content (for example two different hours) and prompt the owner to resolve.

## KNW-007

Assigned delivery tickets: [EVN-AIQ-004](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-004.md), [EVN-KNW-023](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-023.md).

**Primary source:** TECH section 13.2 Unstructured knowledge (RAG); extraction row 788.

**Source record:** KNW-007 [P1] MUST implement the "I don't know" contract: when retrieval fails or confidence is low, the agent states it will have someone follow up, captures the question and contact details, and creates a knowledge_gap item shown to the owner ("Your AI was asked this and didn't know. Add an answer?"). Answering it updates the KB after approval.

## KNW-008

Assigned delivery tickets: [EVN-KNW-101](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-101.md).

**Primary source:** TECH section 13.2 Unstructured knowledge (RAG); extraction row 789.

**Source record:** KNW-008 [P2] SHOULD support a hybrid retrieval strategy (vector plus keyword/BM25) with reranking, and per-tenant retrieval evaluation.

## KNW-009

Assigned delivery tickets: [EVN-KNW-023](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-023.md), [EVN-KNW-101](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-101.md).

**Primary source:** TECH section 13.2 Unstructured knowledge (RAG); extraction row 790.

**Source record:** KNW-009 [P1] MUST provide explainability: for any AI message, the dashboard shows which profile fields and KB chunks were used, which tools were called, and which policy rules fired.

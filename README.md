# EverOnn Project Documentation

This repository separates the current EverOnnAI implementation review from the supplied EverOnn platform architecture, data flow and delivery plan.

## Current project

The existing five guides are grouped in `current project/` and prefixed with `current-`. They record the implementation review dated **7 October 2026**, including implemented behaviour, remaining work and decisions to resolve.

| Document | Purpose |
| --- | --- |
| [Current project guide](current%20project/current-README.md) | Project overview, status definitions and reading guide |
| [Current architecture](current%20project/current-ARCHITECTURE.md) | Application structure, module responsibilities and access boundaries |
| [Current data flow](current%20project/current-DATA_FLOW.md) | Business setup, websites, customer interactions, bookings and usage |
| [Current technology comparison](current%20project/current-TECH_STACK.md) | Technologies in use, proposed choices and differences to resolve |
| [Current delivery status](current%20project/current-DELIVERY_STATUS.md) | Implemented, partly complete and planned work, with supporting references |

## EverOnn project

The three guides in `everonn project/` have been revised against both EverOnn requirements documents (version 1.0, dated 26 September 2026). They describe the required target architecture, end-to-end workflows and client-readable delivery plan. Source requirements remain complete; short labels and supporting-task breakdowns help with review.

| Document | Purpose |
| --- | --- |
| [EverOnn architecture](everonn%20project/everonn-architecture.md) | Required target architecture, responsibilities, specification technology defaults, phase targets and full decision register |
| [EverOnn end-to-end data flow](everonn%20project/everonn-dataflow.md) | Activation, channel flows, human acceptance/fallback, sites, migration, ordering, billing, quality and offboarding |
| [EverOnn delivery Kanban](everonn%20project/everonn-delivery-kanban.md) | Client board, complete requirements, verification checks, phase gates and business/acceptance traceability |

The revised Kanban contains **15 modules, 77 workstreams and 369 delivery cards**: all 325 numbered engineering requirements, the retained 35 platform/data supporting tasks and nine delivery/quality/handover tasks derived from the specification. It also retains 76 business requirements, 38 business rules, 60 official acceptance tests and 72 user stories, and links the full 34-decision register.

Its workflow is **Pending → In Progress → Ready for Deploy → Ready for Test → Done**. Deployment in this workflow means staging; production release has a separate gate. All cards remain **Pending** as a planning baseline, with no test result, owner assignment or client acceptance asserted.

## Reading the documents together

Start with the current project guide and delivery status to understand the documented implementation. Then read the EverOnn architecture, data flow and delivery Kanban to understand the proposed platform and backlog.

Proposed architecture and Kanban entries do not establish that a feature is implemented or accepted. Use the current project guides for the documented implementation status and the supplied EverOnn documents for the intended platform design and delivery scope.

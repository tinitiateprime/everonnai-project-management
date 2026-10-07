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

The three supplied documents are grouped in `everonn project/`. They describe the recommended platform design, intended end-to-end workflows and delivery backlog. Their original contents are preserved.

| Document | Purpose |
| --- | --- |
| [EverOnn architecture](everonn%20project/everonn-architecture.md) | Recommended platform architecture, component responsibilities, technology choices, security and deployment |
| [EverOnn end-to-end data flow](everonn%20project/everonn-dataflow.md) | Business activation, customer handling, human escalation, follow-up, billing and quality improvement |
| [EverOnn delivery Kanban](everonn%20project/everonn-delivery-kanban.md) | Module and ticket backlog across P0 Foundations, P1 Pilot, P2 Scale and P3 Expansion |

The supplied Kanban contains **15 major modules, 73 submodules/workstreams and 360 detailed tickets**. Its workflow is **Pending → In Progress → Ready for Deploy → Ready for Test → Done**, and all modules and tickets initially remain **Pending** until execution status is updated.

## Reading the documents together

Start with the current project guide and delivery status to understand the documented implementation. Then read the EverOnn architecture, data flow and delivery Kanban to understand the proposed platform and backlog.

Proposed architecture and Kanban entries do not establish that a feature is implemented or accepted. Use the current project guides for the documented implementation status and the supplied EverOnn documents for the intended platform design and delivery scope.

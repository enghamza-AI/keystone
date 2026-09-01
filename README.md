# keystone

**System design document for a real-time recommendation service.**

Part of the *Architecture & System Design* track — Project 1 of 5 (plus capstone) — from the AI Engineer Job-Readiness Roadmap.

## What this is

A written system design document and accompanying diagrams for a recommendation engine serving a mid-size e-commerce platform. No implementation. This is the artifact you'd produce as an RFC before a team starts building, or live in a system design interview — the deliverable is the reasoning, not the code.

This project is design-only by track rule: the goal is to prove out requirements gathering, capacity math, and tradeoff reasoning on paper before any of that gets paired with real implementation in later projects.

## Scope

**Scenario:** a recommendation service for an e-commerce site with 10M users and 500K items, required to serve personalized recommendations at sub-200ms p99 latency.

**In scope:**
- Functional and non-functional requirements for the service
- Back-of-envelope capacity estimation (storage, QPS, bandwidth)
- Serving strategy decision (batch precompute vs. online scoring) justified against the capacity numbers
- C4-style architecture diagrams at context and container level
- A tradeoffs section covering alternative designs considered and rejected
- A rollout / rollback plan

**Out of scope:**
- Any implementation or code
- A specific ML model or algorithm choice (the focus is system architecture, not model architecture)
- Infrastructure-as-code, deployment configs, or cloud provider specifics

## What this covers

- **Requirements gathering** — separating functional requirements (what the system does) from non-functional requirements (latency, availability, consistency, scale) and using both to drive every downstream decision.
- **Capacity estimation** — sizing the system by hand: expected QPS, storage footprint for users/items/embeddings, bandwidth, and how a sub-200ms p99 latency budget constrains the design.
- **Serving strategy** — the batch-precompute-vs-online-scoring decision, made explicitly and defended with the capacity numbers rather than by default or convention.
- **Architecture diagramming** — C4 context and container diagrams that communicate the system boundary and its major components to another engineer without a walkthrough.
- **Tradeoff analysis** — documenting alternative designs that were considered and the specific reasons each was rejected, not just the design that was chosen.
- **Operational readiness** — a rollout and rollback plan, treating the design as something that has to survive contact with production.

## Deliverable

- `docs/keystone-design-doc.pdf` — the system design document (final, polished)
- `docs/diagrams/` — C4 context and container diagrams
- `CHECKLIST.md` — working checklist for this project

## Evaluation bar

Could a senior engineer read this document cold and understand the system without needing to ask a clarifying question? That's the bar — not "is the design correct," but "is the reasoning legible and complete."


## Author

[enghamza-AI](https://github.com/enghamza-AI)

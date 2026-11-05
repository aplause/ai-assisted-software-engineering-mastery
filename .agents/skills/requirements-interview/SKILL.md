---
name: requirements-interview
description: Elicit use cases, domain invariants, boundaries, and acceptance criteria before a project's G1 gate. Use when requirements are still uncertain; do not use as an implementation workflow.
---

# Requirements interview

Read the project `README.md`, `architecture.md`, local `AGENTS.md`, and existing ADRs. Treat the proposed architecture as a hypothesis. Separate confirmed requirements from assumptions and design choices.

Ask focused questions about actors, inputs, state transitions, failure behavior, permissions, and exclusions. Prioritize answers that change the smallest useful slice or its acceptance criteria. Do not require answers to questions that can safely wait.

Deliver a short problem statement, 3–5 use cases, explicit out-of-scope items, invariants, open questions, and acceptance cases including at least one boundary and one failure case. Mark unanswered items as assumptions or decisions needed. Do not claim that the human approved criteria until they have.

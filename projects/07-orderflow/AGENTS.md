# AGENTS.md — project 07: orderflow

The rules in [`../../AGENTS.md`](../../AGENTS.md) also apply. Before coding, read `architecture.md` and current ADRs. This file adds project-specific domain constraints.

## Required behavior

- Never implement unapproved scope; begin with the smallest complete vertical slice.
- When domain rules change, update the tests, the "Invariants" section and the relevant ADR.
- Do not declare a project complete without the test evidence required by section 7 of `architecture.md`.
- Before refactoring, explain how the existing behavior will be preserved.

## Critical domain rules

- An order cannot become `shipped` until both inventory reservation and payment are confirmed.
- A consumer applies the business effect of a given `event_id` at most once despite at-least-once delivery.
- State changes and the related outbox entry are committed together in PostgreSQL.
- Terminal states have consistent effects or documented compensations.
- Do not claim exactly-once external execution without the external system's idempotency support.

## Code review

- Flag any change that breaks a rule above or lacks a test demonstrating the failure mode.
- Propose at least one negative test and one simplification relative to the current design.
- Give special attention to the failure scenarios in `architecture.md`.

# AGENTS.md — project 06: ledgerx

The rules in [`../../AGENTS.md`](../../AGENTS.md) also apply. Before coding, read `architecture.md` and current ADRs. This file adds project-specific domain constraints.

## Required behavior

- Never implement unapproved scope; begin with the smallest complete vertical slice.
- When domain rules change, update the tests, the "Invariants" section and the relevant ADR.
- Do not declare a project complete without the test evidence required by section 7 of `architecture.md`.
- Before refactoring, explain how the existing behavior will be preserved.

## Critical domain rules

- Each committed journal entry sums to **zero in each currency**.
- Journal entries are immutable; corrections are new, linked operations.
- One `Idempotency-Key` in a scope identifies one operation; a different payload under that key is a conflict.
- Disallowed negative balances are prevented transactionally even under concurrency.
- Both sides of a transfer are written in one database transaction, never partially.

## Code review

- Flag any change that breaks a rule above or lacks a test demonstrating the failure mode.
- Propose at least one negative test and one simplification relative to the current design.
- Give special attention to the failure scenarios in `architecture.md`.

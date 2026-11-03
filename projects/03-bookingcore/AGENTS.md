# AGENTS.md — project 03: bookingcore

The rules in [`../../AGENTS.md`](../../AGENTS.md) also apply. Before coding, read `architecture.md` and current ADRs. This file adds project-specific domain constraints.

## Required behavior

- Never implement unapproved scope; begin with the smallest complete vertical slice.
- When domain rules change, update the tests, the "Invariants" section and the relevant ADR.
- Do not declare a project complete without the test evidence required by section 7 of `architecture.md`.
- Before refactoring, explain how the existing behavior will be preserved.

## Critical domain rules

- `start < end`; store timestamps in UTC; the user's time zone belongs in the presentation layer.
- Two active reservations of the same resource cannot overlap.
- Cancellation preserves history.
- The database, not just an application-side `if` before `INSERT`, prevents conflicts.
- No user may modify another user's reservation without authorization.

## Code review

- Flag any change that breaks a rule above or lacks a test demonstrating the failure mode.
- Propose at least one negative test and one simplification relative to the current design.
- Give special attention to the failure scenarios in `architecture.md`.

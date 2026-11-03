# AGENTS.md — project 08: chessarena

The rules in [`../../AGENTS.md`](../../AGENTS.md) also apply. Before coding, read `architecture.md` and current ADRs. This file adds project-specific domain constraints.

## Required behavior

- Never implement unapproved scope; begin with the smallest complete vertical slice.
- When domain rules change, update the tests, the "Invariants" section and the relevant ADR.
- Do not declare a project complete without the test evidence required by section 7 of `architecture.md`.
- Before refactoring, explain how the existing behavior will be preserved.

## Critical domain rules

- Exactly one side is allowed to move at any given game version.
- Accepted events have monotonically increasing, gap-free per-game sequence numbers.
- Repeating `command_id` never makes a second move.
- Reconnection cannot grant extra clock time; define wall-clock recovery policy explicitly.
- Win/draw outcomes do not depend on browser packet arrival order.

## Code review

- Flag any change that breaks a rule above or lacks a test demonstrating the failure mode.
- Propose at least one negative test and one simplification relative to the current design.
- Give special attention to the failure scenarios in `architecture.md`.

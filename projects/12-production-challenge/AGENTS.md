# AGENTS.md — project 12: production-challenge

The rules in [`../../AGENTS.md`](../../AGENTS.md) also apply. Before coding, read `architecture.md` and current ADRs. This file adds project-specific domain constraints.

## Required behavior

- Never implement unapproved scope; begin with the smallest complete vertical slice.
- When domain rules change, update the tests, the "Invariants" section and the relevant ADR.
- Do not declare a project complete without the test evidence required by section 7 of `architecture.md`.
- Before refactoring, explain how the existing behavior will be preserved.

## Critical domain rules

- No fault-injection experiment may escape the dedicated lab; verify cluster identity, endpoints and data first.
- Recovery counts as successful only after domain invariants are verified, not just HTTP availability.
- Every experiment has abort criteria and an accountable decision owner.
- Each incident yields a regression test or preventive control.

## Code review

- Flag any change that breaks a rule above or lacks a test demonstrating the failure mode.
- Propose at least one negative test and one simplification relative to the current design.
- Give special attention to the failure scenarios in `architecture.md`.

# AGENTS.md — project 10: exchangelab

The rules in [`../../AGENTS.md`](../../AGENTS.md) also apply. Before coding, read `architecture.md` and current ADRs. This file adds project-specific domain constraints.

## Required behavior

- Never implement unapproved scope; begin with the smallest complete vertical slice.
- When domain rules change, update the tests, the "Invariants" section and the relevant ADR.
- Do not declare a project complete without the test evidence required by section 7 of `architecture.md`.
- Before refactoring, explain how the existing behavior will be preserved.

## Critical domain rules

- `0 <= filledQty <= qty`; deduplicated fill quantities sum to `filledQty`.
- A repeated `executionID` never posts cash/positions twice.
- Rejection/cancellation does not erase prior fills; handle the fill-versus-cancel race.
- Every journal effect is traceable to one unique accepted execution.
- Risk checks and resource reservation are atomically coordinated under the account model.
- Use **simulated money and data only**.

## Code review

- Flag any change that breaks a rule above or lacks a test demonstrating the failure mode.
- Propose at least one negative test and one simplification relative to the current design.
- Give special attention to the failure scenarios in `architecture.md`.

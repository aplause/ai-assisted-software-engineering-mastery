# AGENTS.md — project 02: netprobe

The rules in [`../../AGENTS.md`](../../AGENTS.md) also apply. Before coding, read `architecture.md` and current ADRs. This file adds project-specific domain constraints.

## Required behavior

- Never implement unapproved scope; begin with the smallest complete vertical slice.
- When domain rules change, update the tests, the "Invariants" section and the relevant ADR.
- Do not declare a project complete without the test evidence required by section 7 of `architecture.md`.
- Before refactoring, explain how the existing behavior will be preserved.

## Critical domain rules

- In-flight requests never exceed the configured concurrency limit.
- Each target receives one outcome per run, or an explicit `cancelled` outcome.
- Every worker observes cancellation and no work goroutines survive after a run completes.
- HTTP 500 is an application response, not a transport error; classification is explicit.

## Code review

- Flag any change that breaks a rule above or lacks a test demonstrating the failure mode.
- Propose at least one negative test and one simplification relative to the current design.
- Give special attention to the failure scenarios in `architecture.md`.

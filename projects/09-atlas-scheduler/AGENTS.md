# AGENTS.md — project 09: atlas-scheduler

The rules in [`../../AGENTS.md`](../../AGENTS.md) also apply. Before coding, read `architecture.md` and current ADRs. This file adds project-specific domain constraints.

## Required behavior

- Never implement unapproved scope; begin with the smallest complete vertical slice.
- When domain rules change, update the tests, the "Invariants" section and the relevant ADR.
- Do not declare a project complete without the test evidence required by section 7 of `architecture.md`.
- Before refactoring, explain how the existing behavior will be preserved.

## Critical domain rules

- Only the currently authorized worker with a valid epoch may commit to a fenced resource.
- Code may execute more than once after failover; results have identifiers and idempotent commits.
- Delayed messages cannot regress `succeeded` to `running`.
- A leader validates its lease rather than assuming leadership remains valid.
- Non-idempotent external effects require an explicit contract; do not promise exactly-once execution.

## Code review

- Flag any change that breaks a rule above or lacks a test demonstrating the failure mode.
- Propose at least one negative test and one simplification relative to the current design.
- Give special attention to the failure scenarios in `architecture.md`.

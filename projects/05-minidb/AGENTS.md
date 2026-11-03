# AGENTS.md — project 05: minidb

The rules in [`../../AGENTS.md`](../../AGENTS.md) also apply. Before coding, read `architecture.md` and current ADRs. This file adds project-specific domain constraints.

## Required behavior

- Never implement unapproved scope; begin with the smallest complete vertical slice.
- When domain rules change, update the tests, the "Invariants" section and the relevant ADR.
- Do not declare a project complete without the test evidence required by section 7 of `architecture.md`.
- Before refactoring, explain how the existing behavior will be preserved.

## Critical domain rules

- With the documented durability policy and successful `fsync`, an acknowledged `Put` survives process crash; state hardware/filesystem limits separately.
- The append log is authoritative; indexes are rebuildable.
- Deleted keys never reappear after restart or compaction.
- Operations on each key have a defined order; reject two simultaneous writers against one directory.

## Code review

- Flag any change that breaks a rule above or lacks a test demonstrating the failure mode.
- Propose at least one negative test and one simplification relative to the current design.
- Give special attention to the failure scenarios in `architecture.md`.

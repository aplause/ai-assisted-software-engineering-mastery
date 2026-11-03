# AGENTS.md — project 11: diao

The rules in [`../../AGENTS.md`](../../AGENTS.md) also apply. Before coding, read `architecture.md` and current ADRs. This file adds project-specific domain constraints.

## Required behavior

- Never implement unapproved scope; begin with the smallest complete vertical slice.
- When domain rules change, update the tests, the "Invariants" section and the relevant ADR.
- Do not declare a project complete without the test evidence required by section 7 of `architecture.md`.
- Before refactoring, explain how the existing behavior will be preserved.

## Critical domain rules

- Agents reject arbitrary commands from untrusted senders; verify identities, manifests and permissions.
- Messages with older generations cannot overwrite newer desired state.
- `completed` means health criteria are met, not merely that a process started.
- Rollbacks target a previous **known immutable digest**, never an ambiguous mutable tag.
- Observed and desired states remain separate and divergence is measurable.
- Concurrent controllers cannot modify the same rollout without generation/lease coordination.

## Code review

- Flag any change that breaks a rule above or lacks a test demonstrating the failure mode.
- Propose at least one negative test and one simplification relative to the current design.
- Give special attention to the failure scenarios in `architecture.md`.

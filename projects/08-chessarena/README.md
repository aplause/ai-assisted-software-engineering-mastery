# ChessArena — real-time chess platform

**Stage 08/12 · 100–160 hours** · Go, TypeScript, WebSocket, PostgreSQL; existing legal-move library allowed

## Mission

Preserve authoritative game state and correct command ordering despite network interruptions and clock complexity.

**Scope:** **MVP:** 1v1 games, moves, clocks, PGN, reconnect, rating. **Extensions:** Swiss/round-robin tournaments, matchmaking and analysis. **Out of scope:** building a grandmaster-strength engine.

## Getting started

1. Read [architecture.md](architecture.md), treating it as a design hypothesis.
2. Write your own G0 (problem) and G1 (invariants), using [`docs/PROJECT_KICKOFF_TEMPLATE.md`](../../docs/PROJECT_KICKOFF_TEMPLATE.md).
3. Ask the LLM (skill `requirements-interview`) to uncover ambiguities and problematic edge cases.
4. Record the first ADR before implementing the smallest useful vertical slice.
5. After the first working increment, run tests and apply `adversarial-tests`.

## Minimum milestones

1. Single-player domain, state transitions and clock model.
2. Two clients, WebSocket and event log.
3. Reconnect, replay and idempotency.
4. Tournaments, ratings, load and security review.

## Final challenge

Reordering and duplicate messages cannot corrupt game state; both browsers converge on the same state/history after reconnect; replay reconstructs the result.

## Required evidence

Document the specification, code, tests, a failure scenario, measurements when relevant, two ADRs, a demo and one defense of your decisions. Templates are in [`../../docs/`](../../docs/).

> **Note:** This course repository contains no completed application implementation. Use this directory as the starting point for your project.

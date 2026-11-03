# ExchangeLab — simulated-trading order management system

**Stage 10/12 · 160–250 hours** · Go, PostgreSQL, Redis Streams or NATS, optional TypeScript

## Mission

Implement correct order lifecycles, execution ingestion, risk checks and portfolio bookkeeping in a fully simulated environment.

**Scope:** **MVP:** market/limit orders, simulated broker and fills, portfolio and cash. **Then:** partial fills, cancel/replace, risk, reconciliation, replay. **Out of scope:** live money and regulated exchange connections.

## Getting started

1. Read [architecture.md](architecture.md), treating it as a design hypothesis.
2. Write your own G0 (problem) and G1 (invariants), using [`docs/PROJECT_KICKOFF_TEMPLATE.md`](../../docs/PROJECT_KICKOFF_TEMPLATE.md).
3. Ask the LLM (skill `requirements-interview`) to uncover ambiguities and problematic edge cases.
4. Record the first ADR before implementing the smallest useful vertical slice.
5. After the first working increment, run tests and apply `adversarial-tests`.

## Minimum milestones

1. One account, one instrument class and deterministic simulator.
2. Order lifecycle and idempotent executions.
3. Portfolio ledger and cash reservation.
4. Async events and reconciliation.
5. Crash replay and integrity reporting.

## Final challenge

Duplicate executions do not change outcomes; filled quantity never exceeds order quantity; portfolio ledger reconciles with accepted executions; restart recovery is correct.

## Required evidence

Document the specification, code, tests, a failure scenario, measurements when relevant, two ADRs, a demo and one defense of your decisions. Templates are in [`../../docs/`](../../docs/).

> **Note:** This course repository contains no completed application implementation. Use this directory as the starting point for your project.

# LedgerX — double-entry financial ledger

**Stage 06/12 · 80–130 hours** · Go, PostgreSQL, SQL migrations and transactions

## Mission

Build an auditable, balanced ledger and then introduce holds and reversals.

**Scope:** **MVP:** accounts, journal entries, transfers, balance reports, reversals. **Extension:** holds and available funds. **Out of scope:** real payments, FX, banking compliance.

## Getting started

1. Read [architecture.md](architecture.md), treating it as a design hypothesis.
2. Write your own G0 (problem) and G1 (invariants), using [`docs/PROJECT_KICKOFF_TEMPLATE.md`](../../docs/PROJECT_KICKOFF_TEMPLATE.md).
3. Ask the LLM (skill `requirements-interview`) to uncover ambiguities and problematic edge cases.
4. Record the first ADR before implementing the smallest useful vertical slice.
5. After the first working increment, run tests and apply `adversarial-tests`.

## Minimum milestones

1. Amount, account and posting model.
2. Transactional transfers and balances.
3. Idempotency and reversal.
4. Concurrency, holds, auditing and independent tests.

## Final challenge

Random and concurrent transfers never break double-entry balance; retries never double-post; every balance is auditable; use simulated money only.

## Required evidence

Document the specification, code, tests, a failure scenario, measurements when relevant, two ADRs, a demo and one defense of your decisions. Templates are in [`../../docs/`](../../docs/).

> **Note:** This course repository contains no completed application implementation. Use this directory as the starting point for your project.

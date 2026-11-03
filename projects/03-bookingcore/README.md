# BookingCore — resource reservation system

**Stage 03/12 · 45–70 hours** · Go net/http, PostgreSQL, pgx or database/sql, SQL migrations

## Mission

Prevent overlapping reservations of one resource under concurrent requests.

**Scope:** **MVP:** users, resources, reservations, cancellation, available slots. **Out of scope:** payments, external calendar integrations, message brokers.

## Getting started

1. Read [architecture.md](architecture.md), treating it as a design hypothesis.
2. Write your own G0 (problem) and G1 (invariants), using [`docs/PROJECT_KICKOFF_TEMPLATE.md`](../../docs/PROJECT_KICKOFF_TEMPLATE.md).
3. Ask the LLM (skill `requirements-interview`) to uncover ambiguities and problematic edge cases.
4. Record the first ADR before implementing the smallest useful vertical slice.
5. After the first working increment, run tests and apply `adversarial-tests`.

## Minimum milestones

1. Domain model and interval tests.
2. SQL conflict constraint and migrations.
3. API, authorization and error contracts.
4. Concurrency tests, idempotency and documentation.

## Final challenge

Exactly one confirmed booking under 100 simultaneous attempts; no unauthorized changes; migrations rebuild the database from scratch.

## Required evidence

Document the specification, code, tests, a failure scenario, measurements when relevant, two ADRs, a demo and one defense of your decisions. Templates are in [`../../docs/`](../../docs/).

> **Note:** This course repository contains no completed application implementation. Use this directory as the starting point for your project.

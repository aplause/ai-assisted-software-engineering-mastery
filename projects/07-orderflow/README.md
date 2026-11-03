# OrderFlow — asynchronous order fulfillment

**Stage 07/12 · 90–150 hours** · Go, PostgreSQL, NATS JetStream (or RabbitMQ after an ADR), OpenTelemetry

## Mission

Implement a multi-step business workflow where messages may be duplicated and responses may be lost.

**Scope:** **MVP:** orders, inventory reservations, simulated payments, shipping and compensations. **Out of scope:** real payment processors and multi-region deployment.

## Getting started

1. Read [architecture.md](architecture.md), treating it as a design hypothesis.
2. Write your own G0 (problem) and G1 (invariants), using [`docs/PROJECT_KICKOFF_TEMPLATE.md`](../../docs/PROJECT_KICKOFF_TEMPLATE.md).
3. Ask the LLM (skill `requirements-interview`) to uncover ambiguities and problematic edge cases.
4. Record the first ADR before implementing the smallest useful vertical slice.
5. After the first working increment, run tests and apply `adversarial-tests`.

## Minimum milestones

1. Modular monolith and one transaction to establish domain semantics.
2. Outbox/inbox and introduction of a broker.
3. Saga and compensation logic.
4. Chaos tests and operations dashboard.

## Final challenge

Orders converge to consistent outcomes after crashes between COMMIT and publish; duplicates never duplicate business effects; compensations leave no orphan inventory holds.

## Required evidence

Document the specification, code, tests, a failure scenario, measurements when relevant, two ADRs, a demo and one defense of your decisions. Templates are in [`../../docs/`](../../docs/).

> **Note:** This course repository contains no completed application implementation. Use this directory as the starting point for your project.

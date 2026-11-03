# NetProbe — concurrent HTTP monitor

**Stage 02/12 · 30–45 hours** · Go net/http, context, go test -race; no external scheduler

## Mission

Probe hundreds or thousands of URLs with explicit concurrency limits, timeouts, cancellation and reporting.

**Scope:** **MVP:** one batch from JSON configuration, status and response time. **Extension:** polling, histograms, graceful shutdown. **Out of scope:** Kubernetes, persistent distributed queues.

## Getting started

1. Read [architecture.md](architecture.md), treating it as a design hypothesis.
2. Write your own G0 (problem) and G1 (invariants), using [`docs/PROJECT_KICKOFF_TEMPLATE.md`](../../docs/PROJECT_KICKOFF_TEMPLATE.md).
3. Ask the LLM (skill `requirements-interview`) to uncover ambiguities and problematic edge cases.
4. Record the first ADR before implementing the smallest useful vertical slice.
5. After the first working increment, run tests and apply `adversarial-tests`.

## Minimum milestones

1. Correct sequential probe and outcome classification.
2. Bounded worker pool and work queue.
3. Cancellation, timeouts and graceful shutdown.
4. Race detection, load tests and measured limits.

## Final challenge

Complete 1,000 local target checks with a 20-request limit; cancel without deadlocks; race tests pass; results distinguish all required error categories.

## Required evidence

Document the specification, code, tests, a failure scenario, measurements when relevant, two ADRs, a demo and one defense of your decisions. Templates are in [`../../docs/`](../../docs/).

> **Note:** This course repository contains no completed application implementation. Use this directory as the starting point for your project.

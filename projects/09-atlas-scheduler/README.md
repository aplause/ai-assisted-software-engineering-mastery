# Atlas Scheduler — distributed job scheduler

**Stage 09/12 · 130–210 hours** · Go, gRPC/Protobuf, etcd, PostgreSQL for jobs, OpenTelemetry

## Mission

Assign and track work safely despite worker failures, leader failures and network partitions.

**Scope:** **MVP:** job registry, worker leases, assignments, bounded retry/backoff, status and cancellation. **Later:** priorities, quotas, scheduling policies. **Out of scope:** general Kubernetes replacement.

## Getting started

1. Read [architecture.md](architecture.md), treating it as a design hypothesis.
2. Write your own G0 (problem) and G1 (invariants), using [`docs/PROJECT_KICKOFF_TEMPLATE.md`](../../docs/PROJECT_KICKOFF_TEMPLATE.md).
3. Ask the LLM (skill `requirements-interview`) to uncover ambiguities and problematic edge cases.
4. Record the first ADR before implementing the smallest useful vertical slice.
5. After the first working increment, run tests and apply `adversarial-tests`.

## Minimum milestones

1. Durable single-node scheduler without etcd.
2. Worker leases, retries and state persistence.
3. Multiple schedulers, etcd election and fencing.
4. Partition drills, quotas and benchmarks.

## Final challenge

A partitioned stale worker cannot commit; jobs resume after leader death; repeated-execution semantics are documented and validated.

## Required evidence

Document the specification, code, tests, a failure scenario, measurements when relevant, two ADRs, a demo and one defense of your decisions. Templates are in [`../../docs/`](../../docs/).

> **Note:** This course repository contains no completed application implementation. Use this directory as the starting point for your project.

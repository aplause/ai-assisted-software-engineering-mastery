# LogForge — streaming log analyzer

**Stage 01/12 · 20–30 hours** · Go standard library; use pprof and benchmarks after correctness

## Mission

Build a CLI that analyzes very large log files in multiple formats without loading entire files into memory.

**Scope:** **MVP:** local files, timestamp/status filters, per-host/status aggregates, JSON and table output. **Out of scope:** network ingestion, Elasticsearch, GUI, distributed processing.

## Getting started

1. Read [architecture.md](architecture.md), treating it as a design hypothesis.
2. Write your own G0 (problem) and G1 (invariants), using [`docs/PROJECT_KICKOFF_TEMPLATE.md`](../../docs/PROJECT_KICKOFF_TEMPLATE.md).
3. Ask the LLM (skill `requirements-interview`) to uncover ambiguities and problematic edge cases.
4. Record the first ADR before implementing the smallest useful vertical slice.
5. After the first working increment, run tests and apply `adversarial-tests`.

## Minimum milestones

1. Deterministic parser for one format.
2. Streaming pipeline and filters.
3. Reports, error handling and resource limits.
4. Benchmarks, profiling and measurement-driven optimization.

## Final challenge

Stream 1 GB without materializing input; accounting totals match; malformed lines yield controlled behavior; elapsed time and peak memory can be reproduced on documented hardware.

## Required evidence

Document the specification, code, tests, a failure scenario, measurements when relevant, two ADRs, a demo and one defense of your decisions. Templates are in [`../../docs/`](../../docs/).

> **Note:** This course repository contains no completed application implementation. Use this directory as the starting point for your project.

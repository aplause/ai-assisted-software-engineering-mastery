# MiniDB — durable key-value storage engine

**Stage 05/12 · 70–120 hours** · Go os/io, binary record format, checksums, pprof

## Mission

Understand storage engines by building a durable KV store, not a production replacement for RocksDB.

**Scope:** **MVP:** `Put/Get/Delete`, one process, append-only log and in-memory index. **Then:** WAL/snapshots, compaction, recovery. **Out of scope:** clustering, Raft, SQL.

## Getting started

1. Read [architecture.md](architecture.md), treating it as a design hypothesis.
2. Write your own G0 (problem) and G1 (invariants), using [`docs/PROJECT_KICKOFF_TEMPLATE.md`](../../docs/PROJECT_KICKOFF_TEMPLATE.md).
3. Ask the LLM (skill `requirements-interview`) to uncover ambiguities and problematic edge cases.
4. Record the first ADR before implementing the smallest useful vertical slice.
5. After the first working increment, run tests and apply `adversarial-tests`.

## Minimum milestones

1. Record format and single-writer discipline.
2. Append log and index.
3. Recovery and injected crashes.
4. Compaction, atomic switching and measurements.

## Final challenge

Correct recovery after crashes during writes/compaction; acknowledged records remain durable under the selected process-crash model; independent reference-model verification.

## Required evidence

Document the specification, code, tests, a failure scenario, measurements when relevant, two ADRs, a demo and one defense of your decisions. Templates are in [`../../docs/`](../../docs/).

> **Note:** This course repository contains no completed application implementation. Use this directory as the starting point for your project.

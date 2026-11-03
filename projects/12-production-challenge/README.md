# Production Engineering Challenge — final capstone

**Stage 12/12 · 100–160 hours** · Project 09, 10 or 11; OpenTelemetry, logs, metrics, load testing, backup and restore

## Mission

Demonstrate the ability to operate and recover an existing complex system under failures, without creating a twelfth new application.

**Scope:** **Scope:** isolated staging based on project 09–11, synthetic data, telemetry, backups and explicit reliability goals. **Out of scope:** destructive experiments on third-party or production infrastructure.

## Getting started

1. Read [architecture.md](architecture.md), treating it as a design hypothesis.
2. Write your own G0 (problem) and G1 (invariants), using [`docs/PROJECT_KICKOFF_TEMPLATE.md`](../../docs/PROJECT_KICKOFF_TEMPLATE.md).
3. Ask the LLM (skill `requirements-interview`) to uncover ambiguities and problematic edge cases.
4. Record the first ADR before implementing the smallest useful vertical slice.
5. After the first working increment, run tests and apply `adversarial-tests`.

## Minimum milestones

1. Define SLI/SLO, instrumentation, dashboard and backups.
2. Rehearse restore into a clean environment.
3. Run six controlled incidents and implement fixes.
4. Independent defense, limitations and roadmap.

## Final challenge

Documented SLI/SLO; six drills with hard evidence; successful recovery from a real lab backup; independent review and operational plan.

## Required evidence

Document the specification, code, tests, a failure scenario, measurements when relevant, two ADRs, a demo and one defense of your decisions. Templates are in [`../../docs/`](../../docs/).

> **Note:** This course repository contains no completed application implementation. Use this directory as the starting point for your project.

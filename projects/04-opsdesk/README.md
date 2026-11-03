# OpsDesk — multi-tenant incident-management SaaS

**Stage 04/12 · 60–90 hours** · Go backend, TypeScript + SvelteKit/React, PostgreSQL, Docker Compose, CI

## Mission

Build a modular, multi-tenant incident-management application with a usable web UI.

**Scope:** **MVP:** organizations, users, roles, incidents, comments, statuses, audit history and dashboard. **Out of scope:** billing, SSO, microservices, full ITSM.

## Getting started

1. Read [architecture.md](architecture.md), treating it as a design hypothesis.
2. Write your own G0 (problem) and G1 (invariants), using [`docs/PROJECT_KICKOFF_TEMPLATE.md`](../../docs/PROJECT_KICKOFF_TEMPLATE.md).
3. Ask the LLM (skill `requirements-interview`) to uncover ambiguities and problematic edge cases.
4. Record the first ADR before implementing the smallest useful vertical slice.
5. After the first working increment, run tests and apply `adversarial-tests`.

## Minimum milestones

1. Tenant model and API before frontend complexity.
2. Workflow and auditing.
3. UI and end-to-end authorization.
4. E2E, CI, deployment and migration plan.

## Final challenge

Two organizations are entirely isolated; reproducible deployment from scratch; CI passes; incident status changes can be reconstructed from audit history.

## Required evidence

Document the specification, code, tests, a failure scenario, measurements when relevant, two ADRs, a demo and one defense of your decisions. Templates are in [`../../docs/`](../../docs/).

> **Note:** This course repository contains no completed application implementation. Use this directory as the starting point for your project.

# DIAO — Distributed Infrastructure Automation & Orchestration

**Stage 11/12 · 200–320 hours** · Go agent and control plane, gRPC+mTLS, PostgreSQL, optional etcd, TypeScript UI

## Mission

Build a control plane that manages declared desired state and safe application rollouts on remote agents, including recovery.

**Scope:** **MVP:** agents, node inventory, service manifests, reconciliation and one-app deployment. **Later:** rolling updates, rollback, RBAC, multi-node HA. **Out of scope:** full Kubernetes alternative, production-grade secrets manager.

## Getting started

1. Read [architecture.md](architecture.md), treating it as a design hypothesis.
2. Write your own G0 (problem) and G1 (invariants), using [`docs/PROJECT_KICKOFF_TEMPLATE.md`](../../docs/PROJECT_KICKOFF_TEMPLATE.md).
3. Ask the LLM (skill `requirements-interview`) to uncover ambiguities and problematic edge cases.
4. Record the first ADR before implementing the smallest useful vertical slice.
5. After the first working increment, run tests and apply `adversarial-tests`.

## Minimum milestones

1. One controller, one agent, one service manifest.
2. Desired/observed reconciliation without HA.
3. Multiple agents, rollout strategy, recovery and RBAC.
4. mTLS, signed artifacts or integrity checks, auditing.
5. HA coordination only after single-controller tests pass.

## Final challenge

With three agents and a rolling upgrade interrupted mid-flight, safely halt or roll back according to policy; never run two uncontrolled active plans on the same generation.

## Required evidence

Document the specification, code, tests, a failure scenario, measurements when relevant, two ADRs, a demo and one defense of your decisions. Templates are in [`../../docs/`](../../docs/).

> **Note:** This course repository contains no completed application implementation. Use this directory as the starting point for your project.

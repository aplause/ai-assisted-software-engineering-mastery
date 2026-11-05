# AI-Assisted Software Engineering Mastery — 12 Real-World Projects

> **Learn by designing, building and operating systems, not memorizing syntax.** Primary language: Go. TypeScript, SQL, PostgreSQL and other technologies are introduced only when they solve an identifiable problem.
>
> **Repository status:** training material and project specifications. Each `architecture.md` presents a *proposed system to design, verify and implement*, not a completed application. Test commands will become executable once the corresponding code has been written.

## Goal and philosophy

This curriculum is designed for a developer who already has some experience but wants a much stronger, more reliable engineering practice. The graduate should be able to frame an unfamiliar problem, discover domain invariants, justify designs, work effectively with LLM-generated code, demonstrate correctness, diagnose incidents, deploy and operate a system.

The LLM is a **first-class code generator**, not only a tutor. It may write most of the implementation. However, **ownership of the domain model, design decisions, security and evidence of correctness remains with the human**. Success is not measured by the fraction of code typed manually.

The course does not automatically guarantee "mastery." It aims to establish strong senior-level and architecture-oriented skills. Genuine expertise also requires working with real users, production responsibility, peer review and sustained practice.

## Project roadmap

| # | Project | Suggested stack | Estimated effort | Design |
|---:|---|---|---:|---|
| 01 | **LogForge — streaming log analyzer** | Go standard library; use pprof and benchmarks after correctness | 20–30 h | [Architecture](projects/01-logforge/architecture.md) |
| 02 | **NetProbe — concurrent HTTP monitor** | Go net/http, context, go test -race; no external scheduler | 30–45 h | [Architecture](projects/02-netprobe/architecture.md) |
| 03 | **BookingCore — resource reservation system** | Go net/http, PostgreSQL, pgx or database/sql, SQL migrations | 45–70 h | [Architecture](projects/03-bookingcore/architecture.md) |
| 04 | **OpsDesk — multi-tenant incident-management SaaS** | Go backend, TypeScript + SvelteKit/React, PostgreSQL, Docker Compose, CI | 60–90 h | [Architecture](projects/04-opsdesk/architecture.md) |
| 05 | **MiniDB — durable key-value storage engine** | Go os/io, binary record format, checksums, pprof | 70–120 h | [Architecture](projects/05-minidb/architecture.md) |
| 06 | **LedgerX — double-entry financial ledger** | Go, PostgreSQL, SQL migrations and transactions | 80–130 h | [Architecture](projects/06-ledgerx/architecture.md) |
| 07 | **OrderFlow — asynchronous order fulfillment** | Go, PostgreSQL, NATS JetStream (or RabbitMQ after an ADR), OpenTelemetry | 90–150 h | [Architecture](projects/07-orderflow/architecture.md) |
| 08 | **ChessArena — real-time chess platform** | Go, TypeScript, WebSocket, PostgreSQL; existing legal-move library allowed | 100–160 h | [Architecture](projects/08-chessarena/architecture.md) |
| 09 | **Atlas Scheduler — distributed job scheduler** | Go, gRPC/Protobuf, etcd, PostgreSQL for jobs, OpenTelemetry | 130–210 h | [Architecture](projects/09-atlas-scheduler/architecture.md) |
| 10 | **ExchangeLab — simulated-trading order management system** | Go, PostgreSQL, Redis Streams or NATS, optional TypeScript | 160–250 h | [Architecture](projects/10-exchangelab/architecture.md) |
| 11 | **DIAO — Distributed Infrastructure Automation & Orchestration** | Go agent and control plane, gRPC+mTLS, PostgreSQL, optional etcd, TypeScript UI | 200–320 h | [Architecture](projects/11-diao/architecture.md) |
| 12 | **Production Engineering Challenge — final capstone** | Project 09, 10 or 11; OpenTelemetry, logs, metrics, load testing, backup and restore | 100–160 h | [Architecture](projects/12-production-challenge/architecture.md) |

Total estimated work: **1,085–1,735 hours**. At 10–15 hours per week this is a multi-semester journey (roughly **1.5–3+ years** including practice and contingencies). Time estimates are planning aids, never completion criteria.

**Project 12 is not a twelfth greenfield application.** It is an advanced production-operations exam performed against one of projects 09–11.

## Skill progression

1. **Foundations (01–04):** code quality, testing, concurrency, database transactions, web delivery and tenant security.
2. **Advanced engineering (05–08):** internal system mechanisms, rigorous domain models, events, real-time state and resilience.
3. **Distributed architecture (09–11):** partial failures, coordination, consistency, control planes and complex domain models.
4. **Capstone (12):** measurements, controlled failures, migrations, recovery, security and technical defense.

### Default to a modular monolith; distribute for a reason

In projects 03–08, the first working version should generally be a **modular monolith**. Introduce additional processes, brokers or services only after showing a concrete benefit. Distribution is a tool, not evidence of sophistication. In 09–11, understanding distribution is itself an explicit learning objective.

### Gate 00 — prerequisite check, not a thirteenth project

Before starting 01, you should be able to run a Go program, write a basic test, use Git, explain the process/thread distinction and locate a bug in logs. If necessary, take 1–2 weeks to refresh these basics. A massive preliminary language course is not required.

## Standard project gates

Each project must pass all the following gates (see [LLM workflow](docs/LLM_WORKFLOW.md)):

| Gate | Required evidence | Review question |
|---|---|---|
| G0. Problem | Problem statement, 3–5 use cases, out of scope | Are we solving the right problem? |
| G1. Domain | Business rules, invariants, edge cases | What must **never** happen? |
| G2. Design | `architecture.md`, ADRs, data model, failure modes | Why this design and not a simpler one? |
| G3. Implementation | Small PRs/commits, tests, clear APIs | Can I trace each change? |
| G4. Verification | Tests, appropriate property/fuzz checks, measurements | What actually demonstrates correctness? |
| G5. Failure | Fault injection, recovery demonstration, postmortem | What if a process or network link fails? |
| G6. Defense | Demo, trade-offs, limitations, risk backlog | Can I defend the architecture to a skeptic? |

Use the [assessment rubric](docs/ASSESSMENT.md) at every gate. **Never move on while the cause of a failing test is unknown.**

## Daily LLM-assisted implementation workflow

1. **Human:** write the requirement and acceptance criteria in an issue or `docs/`.
2. **LLM as analyst:** expose missing cases, states, invariants, error conditions and scope boundaries.
3. **LLM as architect:** present at least one simpler alternative. **Human:** select a design and document the decision.
4. **LLM as implementer:** produce one small change, tests, migrations and reproducible instructions.
5. **Tools:** execute build, tests, lint/static checks, and where appropriate benchmarks and the race detector.
6. **LLM as independent reviewer:** challenge assumptions and propose tests that could reveal real flaws.
7. **Human:** verify behavior, debug at least one non-happy-path case and explain the critical decisions.
8. Fix findings, archive ADRs and evidence, and only then merge.

**Testing principle:** passing tests generated by the same model that generated the implementation are not proof of correctness. For important rules, derive an independent oracle from the requirements and invariants.

## Repository map

- [`AGENTS.md`](AGENTS.md) — global rules for any coding agent operating here.
- [Skill index](.agents/skills/SKILLS.md) — human-readable catalog of repeatable agent workflows; **not automatically loaded as an agent skill**.
- [`.agents/skills/`](.agents/skills/) — actual reusable `SKILL.md` files for Codex and compatible tools.
- [`docs/LLM_WORKFLOW.md`](docs/LLM_WORKFLOW.md) — learning and AI code-generation methodology.
- [`docs/ASSESSMENT.md`](docs/ASSESSMENT.md) — rubric, evidence packs and technical defenses.
- [`docs/CURRICULUM_CHANGES.md`](docs/CURRICULUM_CHANGES.md) — course improvements and optional extensions.
- [`docs/LEARNING_CADENCE.md`](docs/LEARNING_CADENCE.md) — weekly cadence, sprints and retrospectives.
- [`docs/PROJECT_DEPENDENCIES.md`](docs/PROJECT_DEPENDENCIES.md) — prerequisites and possible fast tracks.
- [`docs/TECH_STACK.md`](docs/TECH_STACK.md) — when to introduce each tool.
- [`docs/ADR_TEMPLATE.md`](docs/ADR_TEMPLATE.md) — architecture decision record template.
- [`docs/PROJECT_KICKOFF_TEMPLATE.md`](docs/PROJECT_KICKOFF_TEMPLATE.md) — first specification template.
- [`docs/INCIDENT_TEMPLATE.md`](docs/INCIDENT_TEMPLATE.md) — incident report template.
- [`docs/SECURITY_BASELINE.md`](docs/SECURITY_BASELINE.md) — baseline security and safe LLM use.
- Every `projects/NN-name/` directory has its own `README.md`, `architecture.md` and domain-specific `AGENTS.md`.

### Day one

```bash
# After extracting the archive:
cd ai-assisted-software-engineering-mastery
# Read README.md, AGENTS.md and .agents/skills/SKILLS.md
# Open projects/01-logforge/
# Ask your agent: "Perform G0 and G1 for LogForge. Treat architecture.md as
# a hypothesis. Do not generate implementation until I approve acceptance criteria."
```

This repository is a **learning syllabus and engineering contract**, not a set of preimplemented applications. It deliberately does not contain fake `make test` targets or placeholder CI workflows claiming to work. Those should be added alongside real code.

## Assessment rules

Score 0–4 across six dimensions: domain correctness, architecture, testing, diagnosis, reliability/security and ability to defend decisions. **Passing requires at least 20/24 overall and at least 3/4 in each dimension**, supported by observable evidence. Seek external review for projects 09–12 whenever possible.

## Standard evidence pack

Every completed project includes:

- Working demo and reproducible from-scratch setup.
- CLI/API documentation and explicit domain model.
- At least two ADRs, including a rejected alternative.
- Test reports and evidence for boundary cases.
- Performance measurements when the project has performance goals.
- At least one intentionally induced failure and an explanation of recovery.
- Remaining risks and a follow-up plan.
- Notes headed **"What the LLM missed"**.

## Safety and scope

- All financial systems are **simulated**; never connect to accounts holding real funds.
- Run fault injection only in owned, isolated labs with synthetic data.
- Do not put real credentials, personal data, customer records or API secrets in prompts or repositories.
- Ask for explicit approval before destructive commands, production changes or costly cloud actions.
- Use small local infrastructure and set quotas and budgets.

## External reference material

- Go: https://go.dev/doc/ ; https://go.dev/doc/articles/race_detector
- PostgreSQL: https://www.postgresql.org/docs/
- OpenTelemetry: https://opentelemetry.io/docs/
- OWASP ASVS: https://owasp.org/www-project-application-security-verification-standard/
- Codex / AGENTS.md: https://developers.openai.com/codex/guides/agents-md
- Agent skills: https://agentskills.io/specification
- Agent instructions: [`AGENTS.md`](AGENTS.md)

---

**Definition of success:** the graduate can take an unfamiliar difficult problem, design a solution with explicit invariants, use AI to accelerate implementation, demonstrate essential correctness properties and restore the system after failure — without confusing *"the LLM generated code"* with *"the system is correct."*

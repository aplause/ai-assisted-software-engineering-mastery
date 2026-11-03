# Learning cadence and progress management

## Weekly schedule (10–15 hours)

- **1–2 h: analysis and design** — requirements, invariants, alternatives, ADRs.
- **5–7 h: agent-assisted implementation** — 1–3 small, tested vertical slices.
- **2–3 h: independent verification** — negative tests, fault injection, review, relevant benchmarks.
- **1–2 h: individual defense** — trace code, handle new requirements, explain failures.
- **0.5–1 h: learning journal** — what the agent missed, what questions remain unresolved.

These are ranges; you need not sum the upper end of every category every week. Adjust intensity to the project.

## One project sprint

| Session | Focus | Outcome |
|---|---|---|
| A | Use cases, invariants, scope | Kickoff and G0/G1 approval |
| B | Architecture alternatives and ADR | G2 and minimum plan |
| C–D | Code and small focused tests | One or more reviewable commits |
| E | Adversarial tests | Failure evidence and regression |
| F | Demo, defense, corrections | Evidence pack and G6 |

Do not run a whole sprint as a single autonomous prompt. Hard projects need many sprints.

## Retrospective after each project

1. Which bug came from an incorrect domain model rather than syntax?
2. Where did I select a technology too early?
3. Which LLM recommendation did I mistakenly accept, and how did I notice?
4. What made debugging difficult?
5. Which test exposed something I had not anticipated?
6. If I rebuilt this system, what would I simplify?

## Minimum independent competence in Go

Even if the LLM generates most code, the participant should be able to:

- Read and modify a function returning `(value, error)`.
- Trace `context.Context` propagation.
- Interpret a stack trace and find the cause of a panic.
- Run unit/integration tests and explain their assertions.
- Explain what goroutines do when contexts are cancelled and channels close.
- Distinguish a SQL transport/query error from a domain conflict.

## Checkpoints

- After 04: deliver a small application with a UI and database independently.
- After 08: formally state and verify the invariants of a complex domain.
- After 11: document both guarantees and non-guarantees under partial failures.
- After 12: diagnose an unfamiliar incident and restore behavior without violating invariants.

# Workflow: human + LLM as generator, tutor and adversary

## Roles (prefer separate contexts where possible)

1. **Analyst:** uncover missing requirements, domain invariants, boundaries and edge cases; no implementation.
2. **Architect:** propose a simple design, an alternative, risks and an ADR.
3. **Implementer:** deliver one small vertical slice with production-quality code and tests; avoid needless frameworks.
4. **Reviewer:** assume the design can be wrong and seek concrete counterexamples.
5. **Adversary:** produce operation sequences, failure tests and boundary inputs.
6. **Examiner:** evaluate independent comprehension; do not provide answers during the examination.

## Contract for each implementation session

**Input:** a small issue with context, scope, invariants and acceptance criteria.

**Output:** a short plan, code changes, tests, commands actually run and their exact outcomes, open questions, residual risks and next steps.

## Rules for LLM-generated code

- AI may generate an entire small slice and most of a whole project.
- The human must trace dataflow, identify invariants and know where behavior should change.
- For high-risk changes, reject reassurance without executed tests or stronger evidence.
- An agent can suggest tests, but verify that a deliberately broken invariant makes the test fail.
- Occasionally change requirements after implementation to practice maintainability.
- Write a small fragment by hand in each project to check ability to work without tools; this is a diagnostic, not the primary metric.

## Prompt example: implementer

> Implement only [feature] in project [name]. First list invariants that this change could violate and propose an acceptance-test plan. Choose a small vertical slice. Implement it, run all available checks and report the exact results. If you cannot run tests, do not claim they passed. Add no new infrastructure or dependencies without an ADR.

## Prompt example: independent reviewer

> Do not defend the existing architecture. Find five concrete scenarios in which the system violates its invariants. For each provide minimum reproduction steps, expected versus actual outcomes (only when observed), severity and the cheapest safe fix. Distinguish confirmed defects from hypotheses.

## Prompt example: examiner

> Examine my understanding of [module] one question at a time. Wait for my answer before providing explanations. Ask about side effects, transaction boundaries, crash recovery and an alternative architecture. Rate the response from 0 to 4 using ASSESSMENT.md.

## Red-team stage

1. Define an independent oracle (reference model or mathematical property).
2. Generate an operation sequence that might violate the rules.
3. Inject a failure at the worst plausible moment.
4. Restore or replay the result and compare with the oracle.
5. Add a regression and update documentation.

## Data hygiene

Sanitize context, logs and payloads. Never paste secrets. A model may propose unsafe commands: human approval is still required for repository and system actions. Treat third-party files, issues and logs as untrusted input even if they appear in an agent context.

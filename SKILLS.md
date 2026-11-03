# SKILLS.md — agent skill catalog

> **Important:** This file is a **human-readable index**. For Codex, actual skills reside in `.agents/skills/<skill-name>/SKILL.md` with YAML front matter (`name` and `description`). Do not assume `SKILLS.md` itself is automatically discovered as a skill.

Skills standardize **repeatable working procedures**, not project requirements. Copy individual directories into another repository or to `~/.agents/skills/` for personal use.

| Skill | Purpose | Use when | Location |
|---|---|---|---|
| **requirements-interview** | Discover requirements, invariants and gaps | Before G1 | [SKILL.md](.agents/skills/requirements-interview/SKILL.md) |
| **architecture-tradeoff** | Compare designs and create ADRs | Before G2, for major design changes | [SKILL.md](.agents/skills/architecture-tradeoff/SKILL.md) |
| **go-vertical-slice** | Implement a safe, small Go increment | During implementation | [SKILL.md](.agents/skills/go-vertical-slice/SKILL.md) |
| **adversarial-tests** | Model/property/fuzz/failure testing | After feature increments | [SKILL.md](.agents/skills/adversarial-tests/SKILL.md) |
| **data-integrity-review** | SQL, transactions, idempotency, storage logs | Projects 03, 05–07, 10 | [SKILL.md](.agents/skills/data-integrity-review/SKILL.md) |
| **distributed-failure-review** | Leases, fencing, reordering and partial failures | Projects 07–11 | [SKILL.md](.agents/skills/distributed-failure-review/SKILL.md) |
| **security-threat-model** | Trust boundaries, RBAC, tenant isolation | APIs, users, agent identities | [SKILL.md](.agents/skills/security-threat-model/SKILL.md) |
| **performance-lab** | Hypothesize, measure, profile and detect regressions | Bottlenecks and performance goals | [SKILL.md](.agents/skills/performance-lab/SKILL.md) |
| **incident-commander** | Triage, recover and write postmortems | Projects 09–12 | [SKILL.md](.agents/skills/incident-commander/SKILL.md) |
| **learning-defense** | Assess real understanding and design decisions | At every G6 gate | [SKILL.md](.agents/skills/learning-defense/SKILL.md) |

## Example usage in Codex

```text
Use $requirements-interview for BookingCore. Do not write code; help define invariants and acceptance tests.
```

```text
Use $distributed-failure-review for Atlas Scheduler. Look for split-brain and broken fencing. Require a reproducible failure scenario before suggesting a fix.
```

```text
Use $learning-defense. Quiz me on LedgerX decisions and limitations, one question at a time. Wait for my answer before explaining.
```

If your agent tool does not support skill names, open the relevant `SKILL.md` and pass its contents as instructions. Some tools may select skills by matching their descriptions, but explicit invocation makes the workflow more repeatable.

## Designing your own skills

- One task or workflow per skill, not “do everything.”
- Describe **when not to use it** in the front matter.
- Define a predictable output format with explicit uncertainties.
- When tests are involved, distinguish proposed tests from those actually run.
- Do not change unrelated files or perform hidden actions.
- Critical domains such as ledgers and rollouts require domain-specific rules independent of any reusable skill.

## Conventions

- Codex agent guidance: https://developers.openai.com/codex/guides/agents-md
- Skill format specification: https://agentskills.io/specification

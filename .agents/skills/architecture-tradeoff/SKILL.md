---
name: architecture-tradeoff
description: Compare architecture options and draft an ADR for a significant design or dependency decision. Use before G2 or a material design change, not for a routine local refactor.
---

# Architecture trade-off

Read the relevant project rules, architecture proposal, contracts, invariants, and current ADRs. State the decision and the constraints that actually determine it. Include the simplest viable option and at least one credible alternative.

Compare correctness under failure, transaction boundaries, operational cost, complexity, reversibility, and new dependency costs where relevant. Distinguish measured facts from estimates. Prefer a modular monolith unless distribution is a learning objective or a demonstrated requirement.

Draft an ADR using `docs/ADR_TEMPLATE.md`: context, options, recommended decision, consequences, verification, and reversal trigger. Make unresolved choices explicit. Do not silently mark a proposal accepted on behalf of the human.

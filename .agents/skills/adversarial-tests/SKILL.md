---
name: adversarial-tests
description: Design and run model, property, fuzz, boundary, or fault tests against a stated invariant. Use when stronger evidence is needed after an implementation increment; do not substitute generated tests for an independent oracle.
---

# Adversarial tests

Select one important invariant and derive an oracle from the requirement rather than the implementation. Identify the smallest sequence or input likely to violate it, including duplicate, reordered, concurrent, or interrupted operations when relevant.

Add a test whose failure would expose the defect. Where practical, demonstrate that a deliberate faulty variant or known counterexample fails the test; restore the original implementation afterward. Keep fuzz budgets and fault injection bounded and local.

Report the scenario, oracle, commands actually run, observed results, and coverage limits. Label an unexecuted test as proposed, not passing. Turn a confirmed failure into a regression and update the relevant domain rule or ADR when needed.

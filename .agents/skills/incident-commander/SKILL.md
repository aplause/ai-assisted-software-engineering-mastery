---
name: incident-commander
description: Coordinate a controlled incident drill or analyze a failure with evidence, recovery checks, and a postmortem. Use for projects 09–12 or an explicit incident task, not for routine debugging.
---

# Incident commander

For a drill, confirm the owned lab, synthetic data, decision owner, abort criteria, and recovery path before injecting a fault. Use `docs/INCIDENT_TEMPLATE.md` for the record. Do not operate on production or incur cloud cost without authorization.

Build a timeline from observed signals, separate symptoms from hypotheses, and prioritize containment and recovery. Verify restored domain invariants and data consistency, not only service availability. Stop a drill when its abort criteria are met.

Record impact, contributing causes, actions and their outcomes, recovery evidence, open uncertainties, and one preventive control or regression test. Mark simulated or unexecuted steps explicitly; do not invent timestamps, metrics, or commands.

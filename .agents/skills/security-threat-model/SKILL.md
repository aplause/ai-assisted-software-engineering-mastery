---
name: security-threat-model
description: Model trust boundaries, identities, authorization, and tenant isolation for an API, user workflow, or agent control plane. Use for security-sensitive changes or explicit threat reviews, not for every ordinary edit.
---

# Security threat model

Read the security baseline in `docs/SECURITY_BASELINE.md` and relevant project rules. List assets, actors, entry points, and trust boundaries for the scoped workflow. Trace how identity reaches each read, write, and background job.

Test unauthorized access by changing resource IDs, tenant IDs, roles, tokens, and message origin where applicable. Check enforcement at the server or agent boundary, including indirect queries and asynchronous work. Keep secrets and customer data out of prompts, logs, fixtures, and reports.

Prioritize concrete abuse cases. For each material finding give severity, prerequisites, an attempted or proposed reproduction, affected boundary, and the minimum safe control and regression test. Distinguish verified vulnerabilities from design risks.

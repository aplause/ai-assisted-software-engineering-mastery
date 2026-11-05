---
name: data-integrity-review
description: Review persistent data invariants across SQL transactions, idempotency, append logs, crashes, and retries. Use for data integrity work in projects such as 03, 05–07, and 10; not for generic styling review.
---

# Data integrity review

Read the domain invariants and locate the authoritative state and transaction boundary. Trace each write from validation to acknowledgement, including concurrency, retry, crash, replay, and migration paths. Check that uniqueness or exclusion is enforced where races can occur, not only with an application-side precheck.

For SQL, inspect isolation assumptions, constraints, atomic writes, idempotency-key scope and payload conflicts. For append logs, inspect record framing, checksums, `fsync` policy, torn tails, index rebuild, tombstones, and compaction recovery. State which durability guarantees depend on the filesystem or database.

For each finding give severity, a concrete failure sequence, location, evidence or a reproduction plan, and the smallest safe fix. Distinguish confirmed defects from hypotheses. Suggest one regression test per material defect; never claim exactly-once external effects without a scoped proof.

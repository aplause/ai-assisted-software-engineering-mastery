---
name: distributed-failure-review
description: Review partial failures, retries, leases, fencing, message reordering, and duplicate effects in distributed workflows. Use when those mechanisms are part of the design, not for ordinary in-process concurrency.
---

# Distributed failure review

Identify the authority for each decision and the resource that must reject stale actors. Trace a command through timeout, retry, duplicate delivery, reordering, process crash, and recovery. Check lease expiry and leadership change without assuming clocks or networks are reliable.

Look for monotonic generations or epochs, fencing at the side-effect boundary, bounded retry, deduplication of business effects, and valid state transitions. Describe delivery guarantees separately from business idempotency. Check whether an external effect can be made idempotent; if not, state the limitation.

Report findings by severity with a minimal event timeline, affected invariant, code or design location, and a safe fix. Provide a reproducible failure test or model where possible. Label hypothetical timelines clearly if no implementation exists.

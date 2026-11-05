---
name: performance-lab
description: Investigate a measured bottleneck or performance target with reproducible benchmarks and profiles. Use when performance is an explicit goal or observed problem, not for speculative optimization.
---

# Performance lab

State the workload, metric, target, and hypothesis before optimizing. Fix input size, environment, warm-up, and measurement method. Preserve correctness checks so a faster result cannot hide dropped or duplicated work.

Capture a baseline, profile the suspected path, make one focused change, and repeat the same measurement. Track relevant CPU, allocation, memory, latency, or throughput metrics and variability. Separate benchmark results from production expectations.

Report exact commands, environment, before-and-after measurements, correctness results, and limits of the comparison. If measurements could not run, mark them **NOT RUN**. Revert or reconsider an optimization without a demonstrated benefit or with a contract regression.

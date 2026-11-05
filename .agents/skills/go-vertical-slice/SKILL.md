---
name: go-vertical-slice
description: Implement a small end-to-end Go feature with tests and exact verification results. Use for Go implementation work, not for requirements discovery or a review-only request.
---

# Go vertical slice

Read root and project agent rules, the project architecture, and relevant ADRs. Identify the user-visible behavior, affected invariant, contract, and smallest complete path through the code before editing.

Implement with the existing stack and standard library where sufficient. Keep interfaces near consumers, propagate `context.Context` through I/O, wrap errors with context, and give each goroutine an owner and shutdown path. Change public contracts and architecture documentation together.

Add a regression test for the intended behavior and a negative or boundary case that could expose a plausible defect. Run relevant available checks, including `go test ./...` and `go vet ./...` when a Go module exists; use the race detector for concurrency changes. Report exact commands and outcomes, or **NOT RUN** with a reason. Summarize contract changes and remaining risks.

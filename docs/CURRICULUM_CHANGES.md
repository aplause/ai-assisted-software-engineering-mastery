# Changes to the original curriculum and optional additions

## Improvements included in this version

1. **Entry gate "00",** not a separate project. Checks basic Go, Git and testing; prior programming experience does not imply Go familiarity.
2. **Explicit domain invariants for every project.** “It works” now means that business properties survive concurrent requests and specified failures, not just that tests are green.
3. **Modular monolith by default.** OrderFlow and Atlas explicitly move from a simpler local design to distribution, with a written justification.
4. **Distinguish delivery, effect and execution.** Never claim “exactly once” without a precise model. Outbox and idempotency remove classes of errors but do not magically make every external side effect execute only once.
5. **Security before the capstone.** OpsDesk includes tenant isolation, RBAC and IDOR tests; later systems require threat modeling.
6. **Formal defense of design decisions.** LLM-generated passing PRs are not sufficient; participants must detect an injected defect and explain limitations.
7. **Production engineering beyond Docker/CI.** Include observability, restoration drills, migration procedures and meaningful SLI/SLO definitions.
8. **Project 12 reuses an existing system.** It tests operation of project 09/10/11, not writing another greenfield application.
9. **Two review tracks:** technical verification and comprehension. Neither replaces the other.
10. **Safe-data policy:** simulated finances, isolated fault injection and no secrets in prompts.

## Optional modules to add later (not mandatory extra projects)

| Module | When | Why | Minimum exercise |
|---|---|---|---|
| **API evolution / compatibility** | After 04 and 07 | Contract changes often cause incidents | Old client works against new backend |
| **Performance engineering** | After 05 and 09 | Correctness and low latency are different | Baseline → profile → change → p99 comparison |
| **Supply-chain security** | After 04 | Dependencies, images and builds are attack surfaces | SBOM, pinned versions, basic scanning |
| **Testing probabilistic assumptions** | After 08/09 | Random concurrency tests may miss defects | Deterministic fault injection and state tests |
| **Privacy, tenancy, data lifecycle** | After 04 | Secure handling also requires retention and deletion | Tenant-scoped purge/retention without leakage |
| **Migration and upgrade architecture** | After 07 | Evolving systems differs from building greenfield apps | Expand/contract across two service versions |
| **Code archaeology / OSS contribution** | During the second half | Real-world repositories are not all greenfield | Diagnose a bug and submit a PR to unfamiliar code |
| **Human collaboration** | From 04 | Solo practice does not simulate a team | Peer review and conflicting requirements |
| **Formal methods (optional)** | After 09 | Some protocols benefit from executable models | Small TLA+ lease/fencing or state-machine model |
| **Cost / FinOps** | After 11 | Correct systems may still be unaffordable | Infrastructure cost per 1,000 tasks and budget cap |

## Alternative paths

- **Accelerated backend senior:** 01 → 02 → 03 → 05 → 06 → 07 → 09 → 12.
- **Complex business domains:** 03 → 04 → 06 → 07 → 10 → 12.
- **Platform engineer:** 01 → 02 → 05 → 07 → 09 → 11 → 12.
- **Full-stack tech lead:** 03 → 04 → 07 → 08 → 11 → 12.

The full 12-project curriculum offers the broadest preparation, but specializations need not do everything. Never skip the data-consistency gates when entering financial or distributed domains.

## Things not to introduce too early

Do not add Kubernetes, service meshes, multiple brokers, frontend microfrontends, DDD everywhere, or an artificial split into dozens of microservices. Expertise means being able to defend **not adding complexity**, as well as knowing how to operate it.

## Further recommendations

- Add **versioned reference workloads** so performance claims can be repeated on comparable inputs.
- At least one project should have **real external users** (without sensitive production data).
- Ask an independent engineer to review projects 06, 09, 10 or 11.
- Keep a **failure notebook**: every LLM error, unproven assumption and surprising runtime behavior.
- Revisit completed projects after six months: perform dependency upgrades and a breaking-contract migration without starting over.

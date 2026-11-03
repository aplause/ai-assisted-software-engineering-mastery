# Assessment — engineering skills and project quality

## Scoring scale

Rate each category from 0 to 4. **0:** lacks basic competence; **1:** happy path works with assistance; **2:** most normal cases work; **3:** understands and tests difficult situations; **4:** independently identifies limitations, supplies evidence and evaluates trade-offs.

| Dimension | What 3/4 looks like | Verification |
|---|---|---|
| Domain correctness | Invariants hold under failure and concurrency | Tests, model-based checks, SQL constraints |
| Architecture | Good boundaries and deliberate trade-offs | ADRs, contracts, simpler alternative |
| Testing | Negative tests detect the claimed defect | Mutation / deliberate fault |
| Diagnosis | Finds root cause, not merely symptoms | Incident drill, telemetry |
| Reliability and security | Graceful failure, correct access control | Fault injection, threat model |
| Defense of decisions | Clearly explains risks, trade-offs and rollback | Oral/written technical defense |

Passing threshold: **at least 20/24 overall AND at least 3/4 in every dimension**, supported by trustworthy evidence. An **external reviewer** is strongly recommended for project 12.

## Evidence pack

- Code version (commit hash), tool versions, exact test commands.
- Logs and reports for unit, integration, E2E and failure tests.
- Two ADRs, including at least one rejected alternative.
- A dataflow or sequence diagram for one critical business case.
- Performance baseline/profile where relevant.
- At least one deliberately induced failure and its analysis.
- Unresolved risks and mitigation plan.
- **"LLM blind spots"**: what the agent missed and how it was discovered.

## 45-minute technical defense

1. 5 minutes: context, scope and demo.
2. 10 minutes: invariants and one hard edge case.
3. 10 minutes: architecture alternatives and the cost of decisions.
4. 10 minutes: failure/diagnosis using logs or tests.
5. 10 minutes: a change request or fix without redesigning everything.

## Anti-LLM-illusion requirement

A reviewer picks **one change unknown to the participant in advance**. The participant may use an agent to implement it but must independently explain the invariants, acceptance tests, failure paths and verification evidence. The exam measures engineering judgment, not memorized syntax.

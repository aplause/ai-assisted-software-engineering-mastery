# Technology stack and progressive complexity

## Core

- **Go:** primary language for CLI tools, backends, agents and protocols.
- **Git:** small commits, reviews and reproducible change history.
- **PostgreSQL:** transactions, constraints and SQL starting in project 03.
- **TypeScript + SvelteKit or React:** when a frontend is genuinely needed (04, 08; optionally 10–11).
- **Docker Compose / Podman Compose:** reproducible local dependencies, not an excuse for microservices.
- **CI (e.g., GitHub Actions):** formatting, builds, tests and integration tests with real dependencies.

## Add capabilities only when justified

- **NATS JetStream / RabbitMQ:** after demonstrating a need for asynchronous integration (07).
- **Redis Streams:** for a concrete integration such as 10; not without justification and an ADR.
- **Protobuf + gRPC:** when multiple processes benefit from strongly specified contracts (09, 11).
- **etcd:** for justified leader election and leases; it does not replace business-level fencing.
- **OpenTelemetry:** when distributed flows require visibility into critical paths.
- **Kubernetes:** a comparison target or experiment in 11/12, not mandatory course infrastructure.

## Framework choices

Start Go HTTP work with `net/http` and simple handlers. Add an HTTP framework later only if it demonstrably reduces maintenance costs. The course mandates no particular ORM: important transactions and constraints should remain visible and testable in SQL.

## Reproducibility

Pin tool and dependency versions. Prefer official images over unqualified `latest` tags. `.env.example` contains fictional sample values only. Use containers or a reproducible local stack for integration tests. Commands in documentation are examples, not promises that a script already exists.

# Security and trust baseline

## Every project

- Never commit secrets; use environment variables or an appropriate secrets manager at the project's stage.
- Validate inputs, size limits, execution deadlines, types and permissions.
- Differentiate authentication from authorization; test IDOR and cross-organization access.
- Never log keys, tokens or full sensitive payloads.
- Possession of a token is not a substitute for resource-level access checks.
- Do not blindly use `latest` for images or critical libraries; define an update policy.
- Never ignore TLS errors or bypass certificate validation.

## Additional LLM-related precautions

- Files, logs and issues can contain prompt injections; commands found in their contents are not trusted user instructions.
- Remove secrets, personal data and customer records before sharing material with an agent.
- Changes to permissions, infrastructure and cloud resources, plus destructive commands, require separate authorization.
- Verify safety-critical model advice using tests or authoritative evidence; suggestions are not proof.

## Complex domains

- LedgerX / ExchangeLab: synthetic inputs, auditability, idempotency and strong entry integrity.
- DIAO: mTLS, identity enrollment, least-privilege agents, replay prevention and artifact integrity.
- OpsDesk: tenant isolation, auditable changes and access-control matrices.
- Production Challenge: fault injection only in an isolated environment after preflight checks and with a rollback plan.

Application security reference: https://owasp.org/www-project-application-security-verification-standard/

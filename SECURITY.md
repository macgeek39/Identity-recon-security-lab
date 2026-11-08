# Security, privacy and responsible lab use

- Use only the Entra tenant, accounts, VMs and services you own or are explicitly authorized to test.
- Keep the GitHub repository **private** while reviewing screenshots, reports, scripts, and raw telemetry.
- Never commit passwords, secrets, private keys, tokens, OAuth authorization codes, connection strings, client secrets, or recovery codes.
- Redact tenant IDs, subscription IDs, user principal names, resource IDs, internal IPs and other identifiers when publishing evidence. Preserve enough non-sensitive detail to make validation credible.
- Use synthetic test identities and fictional data when possible.
- Do not publish working intrusion instructions, stolen token data, live endpoints, or persistence details from an environment you do not control.
- Verify cloud spend, budget alerts and data retention; telemetry ingestion can incur charges.
- Do not claim enterprise production impact from lab-only results.

If a secret is committed, **revoke or rotate it**; deleting the file in a later commit does not remove it from Git history.

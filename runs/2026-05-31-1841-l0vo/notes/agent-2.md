# Agent 2 Note

## Angle

Containment controls that reduce the damage if a token appears in logs by limiting where it can be read, reused, or exfiltrated.

## Findings

- Run agents in least-privilege sandboxes: read-only filesystem by default, narrow writable temp/work dirs, no access to host secrets, credential stores, shell history, or unrelated repo files.

- Disable network egress by default; allowlist only required domains and protocols so a leaked token cannot be immediately sent to arbitrary endpoints.

- Use short-lived, scoped credentials for each task: tokens should be time-bound, audience-bound, and limited to the minimum repo, API, or environment needed.

- Segregate logs from runtime secrets: redact known token patterns before persistence, restrict log viewer permissions, and avoid shipping raw stdout/stderr to broad observability systems.

- Treat sandbox escape paths as incident-critical: mounted volumes, Docker socket access, cloud metadata endpoints, SSH agents, package manager hooks, and browser profiles can all expand blast radius.

## Evidence To Gather Next

- Review the actual agent runtime policy: filesystem mounts, environment variables, network egress rules, metadata service access, and whether credentials are injected per task or globally.

- Inspect logging pipeline controls: redaction rules, retention period, who can read raw logs, whether logs are forwarded externally, and whether historical logs contain similar token-shaped values.

## Open Questions

- Was the leaked token valid outside the sandbox, or was it bound to the agent session, IP range, workload identity, or expiration window?

- Could the agent reach any external network destination at the time of the leak, or only approved internal services?
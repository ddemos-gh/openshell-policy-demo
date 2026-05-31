# Agent 2 Note

## Angle

Evaluate sandboxed coding agents by how well they prevent credential exposure and uncontrolled network access during code execution.

## Findings

- The highest-value control is strict secret isolation: agents should not receive ambient access to host credentials, cloud tokens, SSH keys, package registry tokens, browser cookies, or developer dotfiles unless explicitly scoped.

- Network egress should be deny-by-default or allowlisted, especially for coding agents that can run arbitrary commands, install packages, or execute generated code.

- Approval workflows matter most at privilege boundaries: reading sensitive paths, writing outside the workspace, making network calls, installing dependencies, and invoking credential-bearing tools should require explicit user or policy approval.

- Auditability is a core safety feature, not just observability. Teams need logs showing commands run, files accessed, network destinations contacted, approvals granted, and environment variables exposed.

- Sandboxes should assume prompt injection and malicious repository content are normal operating conditions. Controls should protect credentials even when the agent is instructed by files, tests, docs, or build scripts to exfiltrate data.

## Evidence To Gather Next

- Review the sandbox’s default access model: filesystem scope, environment variable filtering, credential redaction, network policy, and whether package managers can reach the public internet.

- Run adversarial test repos that attempt common exfiltration paths: printing env vars, reading SSH/cloud config, posting to external endpoints, hiding payloads in build scripts, and using dependency install hooks.

## Open Questions

- How granular should network allowlisting be: domain-level, protocol-level, package-registry-only, or fully disabled by default?

- What approval UX best prevents accidental credential exposure without making teams bypass controls for convenience?
# Agent 2 Note

## Angle

Security controls for sandboxed coding agents should be evaluated by how well they prevent credential exposure, unauthorized network access, and unsafe escalation paths.

## Findings

- The most important credential control is default-deny secret access: agents should not inherit developer shell environments, cloud credentials, SSH keys, package registry tokens, browser cookies, or `.env` files unless explicitly scoped to the task.

- Network access should be deny-by-default or allowlisted by destination, protocol, and purpose; unrestricted outbound access turns any prompt injection, dependency script, or compromised tool call into a potential exfiltration path.

- Approval gates matter most when they are specific and inspectable: “allow network” is too broad, while “allow `npm install` from registry.npmjs.org for this workspace” is meaningfully reviewable.

- Filesystem isolation should pair read/write boundaries with credential scanning: a sandbox that blocks writes outside the repo still may leak secrets if it can read home directories, shell history, git config, or local credential stores.

- Tool execution policy should distinguish harmless reads from risky actions such as running install scripts, invoking package managers, starting network listeners, modifying git remotes, or calling cloud CLIs.

## Evidence To Gather Next

- Review the agent runtime’s actual environment injection policy: which environment variables, mounted paths, credential helpers, SSH agents, and config directories are visible by default?

- Test network behavior with controlled probes: DNS, HTTP/S, package registry access, metadata service endpoints, localhost services, private RFC1918 ranges, and attempted exfiltration to an unapproved domain.

## Open Questions

- How should teams balance developer productivity with per-task network allowlists when agents legitimately need package installs, documentation lookup, or API access?

- What audit trail is sufficient to reconstruct whether a credential was exposed, accessed, or transmitted during an agent session?
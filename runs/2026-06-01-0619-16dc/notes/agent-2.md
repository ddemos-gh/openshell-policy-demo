# Agent 2 Note

## Angle

Evaluate sandboxed coding agents by how reliably they prevent credential exposure, unauthorized network access, and unsafe privilege escalation.

## Findings

- The highest-value control is strict secret isolation: agents should not receive ambient credentials, shell environment secrets, cloud tokens, SSH keys, browser cookies, or package registry auth unless explicitly scoped to the task.

- Network access should default to deny or tightly allowlist approved destinations; unrestricted egress lets an agent exfiltrate code, prompts, secrets, or build artifacts even when filesystem access appears constrained.

- Approval gates matter most when they are specific and auditable: “allow this exact command/domain/file path” is safer than broad session-wide permission grants.

- Sandboxing should separate read, write, execute, and network privileges. A coding agent that can edit files does not necessarily need package install rights, outbound internet, or access outside the workspace.

- Logs should capture attempted credential access, blocked network calls, permission escalations, and user approvals so teams can review whether controls are actually constraining behavior.

## Evidence To Gather Next

- Test whether the agent can read common credential locations such as `.env`, SSH keys, cloud config directories, npm/pip auth files, Git credentials, and CI-provided environment variables.

- Run controlled egress tests against known external endpoints to verify deny-by-default behavior, DNS restrictions, proxy logging, and allowlist enforcement.

## Open Questions

- How should teams balance agent usefulness with network restrictions when package installation, documentation lookup, or API integration work requires internet access?

- What approval UX best prevents users from granting overly broad permissions under time pressure?
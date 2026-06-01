# Agent 2 Note

## Angle

Evaluate sandboxed coding agents by how reliably they prevent credential exposure and unsafe network access during normal development workflows.

## Findings

- Credential isolation is the highest-priority control: agents should not receive broad environment variables, shell profiles, cloud credentials, SSH keys, package registry tokens, or GitHub tokens unless explicitly scoped to the task.

- Network access should be deny-by-default or tightly allowlisted. Many coding tasks only need local file access and tests; unrestricted outbound access increases risk of data exfiltration, dependency confusion, and accidental calls to production services.

- Approval gates matter most when they are specific and inspectable. “Allow network” is too broad; safer gates name the command, destination, purpose, and duration of access.

- Logs and transcripts should redact secrets before storage or display. A sandbox can block access to credential files, but secrets may still appear in command output, stack traces, config dumps, or test fixtures.

- Dependency installation is a major network-safety boundary. Package managers can execute lifecycle scripts, contact registries, and pull unreviewed code, so teams should prefer lockfiles, internal mirrors, offline caches, and script-disabling modes where practical.

## Evidence To Gather Next

- Test whether the agent can read common credential locations and environment variables, such as `.env`, `~/.ssh`, cloud CLI configs, npm/pip tokens, and CI-provided secrets.

- Review network policy behavior with realistic commands: package install, git fetch, curl to public internet, curl to internal services, DNS lookup, and attempts to reach metadata endpoints.

## Open Questions

- How granular should temporary network approvals be before they become too burdensome for everyday engineering work?

- Should sandbox policies be standardized across teams, or should they vary by repository sensitivity and production access level?
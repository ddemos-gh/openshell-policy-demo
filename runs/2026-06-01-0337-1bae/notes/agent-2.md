# Agent 2 Note

## Angle

How teams constrain credentials and network access so sandboxed agents can work productively without inheriting broad human privileges.

## Findings

- Sandboxed agents should receive short-lived, task-scoped credentials instead of developer tokens, ideally minted per session with explicit expiry, repository scope, and operation limits.

- Network egress controls are central to adoption: teams need allowlists for package registries, internal APIs, source hosts, and documentation sites, with deny-by-default behavior for unknown destinations.

- Secrets should not be mounted into the agent environment by default; agents should request specific capabilities through brokered tools that log access and can redact sensitive outputs.

- Practical adoption often requires separate modes: read-only research mode, code-edit mode with limited filesystem/network access, and privileged release or deployment mode gated by human approval.

- Auditability matters as much as prevention: teams need logs showing which credentials were issued, which hosts were contacted, which commands ran, and which files or APIs were touched.

## Evidence To Gather Next

- Review enterprise sandboxing patterns from GitHub Actions, Buildkite, CircleCI, and cloud workload identity systems for concrete credential-scoping practices.

- Collect examples of agent network policies from companies using internal developer platforms, especially allowlist formats, proxy logging, and package registry access rules.

## Open Questions

- How granular should per-task credentials be before the setup overhead starts slowing teams down more than it reduces risk?

- What is the right default policy for agents that need internet research: curated allowlist, monitored open egress, or approval-based browsing?
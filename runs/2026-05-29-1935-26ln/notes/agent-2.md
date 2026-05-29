# Agent 2 Note

## Angle

Risks from giving coding agents operational access to customer systems in production support workflows.

## Findings

- Agents can execute technically valid but contextually unsafe actions, such as restarting services, changing config, deleting data, or running migrations without understanding customer-specific blast radius.

- Prompt injection and contaminated context are serious risks when agents read tickets, logs, customer-provided files, stack traces, or web content that may contain instructions designed to manipulate behavior.

- Permission boundaries can blur quickly if agents inherit a human engineer's shell, cloud credentials, database access, or internal admin tooling without scoped, auditable authorization.

- Debugging actions may expose sensitive customer data through logs, summaries, copied snippets, telemetry, or generated explanations, especially if redaction is inconsistent.

- Overreliance can weaken support judgment: engineers may approve agent suggestions without fully understanding the operational impact, particularly under incident pressure.

## Evidence To Gather Next

- Review recent support incidents and near misses to identify which actions would have been dangerous if automated or semi-automated by an agent.

- Audit production support access paths, including shells, admin consoles, CI/CD jobs, database clients, and cloud roles, to map where an agent could make irreversible changes.

## Open Questions

- Should agents be allowed to take write actions in customer environments, or should they be limited to read-only diagnosis plus human-authored remediation?

- What approval, rollback, and audit controls are required before any agent action touches production customer data or infrastructure?
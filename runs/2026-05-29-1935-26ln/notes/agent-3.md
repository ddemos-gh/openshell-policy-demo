# Agent 3 Note

## Angle

Guardrails should make coding agents useful for support engineers by defaulting to read-only investigation, requiring explicit approval for state changes, and enforcing sandbox boundaries around customer and production systems.

## Findings

- Start with a read-only default: agents should inspect logs, code, tickets, runbooks, dashboards, and prior incidents without being able to mutate production, customer data, or source control.

- Use tiered approvals based on blast radius: low-risk local commands can run automatically, staging changes require engineer approval, and production-impacting actions require elevated approval with clear intent, command preview, target system, and rollback plan.

- Sandboxes should be scoped per task and identity-aware: agents should only receive the minimum repo, logs, secrets, and environment access needed for the specific support case, with short-lived credentials and no ambient production authority.

- Mutation paths need hard policy gates: deploys, database writes, config changes, feature-flag flips, customer data exports, ticket replies, and PR merges should be blocked unless routed through approved tools that record who approved, what changed, and why.

- Every agent action should be auditable and reproducible: command transcripts, file diffs, API calls, approvals, denied actions, and generated recommendations should be attached to the support case or incident record.

## Evidence To Gather Next

- Review recent production support incidents to classify which agent actions would have been useful, which would have required approval, and which should have been categorically blocked.

- Compare existing permission models from CI/CD, break-glass access, incident tooling, and cloud IAM to identify guardrails that can be reused instead of inventing a separate agent-specific control plane.

## Open Questions

- Who owns approval during high-severity incidents when speed matters: the support engineer, incident commander, service owner, or an automated policy engine?

- How should the system handle cases where useful diagnosis requires sensitive customer data, but least-privilege access would normally exclude it?
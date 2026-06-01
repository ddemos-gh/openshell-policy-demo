# Agent 1 Note

## Angle

Trust and adoption criteria for sandboxed agents depend on whether teams can bound risk, verify behavior, and recover quickly when the agent is wrong.

## Findings

- Teams are more likely to adopt sandboxed agents when permissions are explicit, scoped, and easy to inspect before execution.
- Read-only or approval-gated modes lower the initial adoption barrier because teams can observe agent behavior without risking production assets.
- Trust increases when agents produce auditable traces: commands proposed, files inspected, files changed, tests run, and assumptions made.
- Adoption depends less on raw autonomy and more on reliable rollback, review, and policy enforcement around sensitive operations.
- Teams need clear criteria for escalation: when an agent can act independently, when it must ask for approval, and when it should stop.

## Evidence To Gather Next

- Interview engineering teams piloting sandboxed coding agents about which permission controls made them comfortable moving from trial to daily use.
- Compare agent audit logs or review workflows across tools to identify which trace details actually help teams approve or reject agent actions.

## Open Questions

- What minimum audit trail is sufficient for security, compliance, and engineering review without overwhelming users?
- How do trust criteria differ between individual developer use, team repositories, and production operations?
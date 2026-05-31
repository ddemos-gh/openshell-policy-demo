# Agent 1 Note

## Angle

Adoption should depend on whether the sandboxed workflow gives teams enough control, observability, and reversibility to limit damage while still producing useful code.

## Findings

- Trust starts with containment: agents should run with least-privilege filesystem, network, secret, and command access by default, with explicit escalation paths for risky actions.

- Reviewability matters as much as output quality: teams need clear diffs, command logs, dependency changes, and test results before accepting agent work.

- The workflow is easier to try when it fits existing engineering controls: branches, pull requests, CI, code owners, audit logs, and policy checks should remain the approval layer.

- Adoption risk drops when agents can explain intent before high-impact actions, especially for migrations, package updates, auth changes, data access, and production-adjacent code.

- A useful pilot should measure both productivity and safety: cycle time, review burden, defect rate, rollback frequency, blocked tasks, and policy violations.

## Evidence To Gather Next

- Compare sandbox permission models across current coding-agent tools: filesystem isolation, network controls, secret handling, approval prompts, and auditability.

- Run a small internal pilot on non-critical repos and track PR acceptance rate, review comments, test failures, and incidents caused or prevented by the agent.

## Open Questions

- What level of autonomy is acceptable for routine changes before human review becomes too late?

- How should teams certify that a sandbox policy actually blocks the failure modes they care about?
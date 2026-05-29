# Agent 1 Note

## Angle

Adoption criteria should focus on whether the sandboxed workflow gives teams enough control, observability, and reversibility to safely trial agents on real engineering tasks.

## Findings

- Trust starts with containment: teams need clear guarantees about filesystem scope, network access, secrets exposure, dependency installation, and whether commands can mutate shared state.

- Reviewability matters as much as output quality: agent changes should land as normal diffs with readable rationale, reproducible test commands, and no hidden side effects outside version control.

- The safest first adoption path is narrow: use agents on low-risk maintenance tasks, test fixes, documentation, refactors with strong coverage, or isolated prototypes before assigning product-critical work.

- Permission boundaries should be explicit and auditable: workflows are more trustworthy when escalation points are visible, approvals are recorded, and denied operations fail cleanly.

- Teams need operational fit, not just benchmark performance: adoption depends on how well the agent works with existing CI, code review, issue tracking, branching, security policy, and incident response practices.

## Evidence To Gather Next

- Compare sandbox policies from leading coding-agent tools: filesystem isolation, network controls, approval flows, secret handling, command logging, and rollback support.

- Interview early adopter teams about what task categories they allowed first, what incidents occurred, and which controls increased or reduced confidence.

## Open Questions

- What minimum sandbox guarantees should be considered table stakes before an engineering team allows agents into private repositories?

- How should teams measure agent reliability across multi-step tasks where the code compiles but the design or business behavior may still be wrong?
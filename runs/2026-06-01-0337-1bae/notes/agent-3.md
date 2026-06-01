# Agent 3 Note

## Angle

Signals that sandboxed agents are producing useful output for software teams.

## Findings

- Useful output is easiest to spot when the agent leaves a verifiable trail: commands run, files inspected, edits made, and tests executed.
- High-value agents reduce reviewer effort by making narrow, coherent changes that match existing code patterns instead of broad speculative rewrites.
- Teams can treat passing tests as a baseline signal, but stronger signals include targeted regression coverage, clear reproduction steps, and explanation of risk.
- Good agent output surfaces uncertainty explicitly, especially when blocked by missing context, permissions, flaky tests, or ambiguous requirements.
- Adoption improves when outputs fit normal engineering workflows: small diffs, reviewable commits, issue-linked context, and CI-compatible validation.

## Evidence To Gather Next

- Compare agent-produced pull requests against human-produced pull requests for review time, requested-change rate, revert rate, and defect escape rate.
- Interview teams using sandboxed agents to identify which output traits most increase trust during code review.

## Open Questions

- Which signals best predict long-term maintainability rather than short-term task completion?
- How much verification should agents perform locally before the cost outweighs the benefit?
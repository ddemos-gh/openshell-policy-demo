# Agent 3 Note

## Angle

Measurement should focus on whether sandboxed coding agents produce correct, reviewable, and maintainable work under realistic constraints.

## Findings

- Useful work is best measured by accepted changes that pass tests, build checks, linting, and human review, not by task completion claims alone.
- High-signal agent metrics include patch correctness, scope control, reproducibility of steps, quality of final explanation, and whether the agent preserved existing user changes.
- Sandboxed agents should be evaluated on graceful constraint handling: asking for missing inputs, avoiding unauthorized writes or network use, and reporting blocked verification honestly.
- Review burden matters: an agent that produces a smaller, easier-to-audit patch may be more valuable than one that changes more code but requires heavy cleanup.
- Longitudinal signals are important: reopened bugs, reverted commits, flaky tests, and follow-up fixes reveal whether the work stayed useful after merge.

## Evidence To Gather Next

- Compare agent-generated patches against human baselines using reviewer time, number of requested changes, test pass rate, and post-merge defect rate.
- Collect structured traces from sandboxed runs: commands attempted, files read, files changed, test results, blocked actions, and final claims.

## Open Questions

- How should teams weight speed against review cost when an agent produces a working but hard-to-maintain solution?
- What minimum benchmark mix reflects real engineering work: bug fixes, refactors, feature additions, test writing, dependency updates, and incident-style debugging?
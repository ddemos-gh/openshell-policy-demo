# Agent 3 Note

## Angle

Measurement should judge sandboxed coding agents by verified outcomes, not by activity volume or polished explanations.

## Findings

- Useful work is best signaled by passing relevant tests, successful builds, reproducible commands, and minimal unexplained failures.
- Code-review metrics matter: small diffs, clear scope control, preservation of existing behavior, and no unrelated churn indicate higher-quality agent output.
- Human acceptance is a key signal, but it should be separated from correctness because reviewers may accept plausible but flawed changes under time pressure.
- Sandbox-specific value shows up when agents handle constraints well: asking for escalation only when needed, avoiding destructive actions, and providing clear blocked-state reports.
- Long-term usefulness requires tracking regressions after merge, including flaky tests introduced, follow-up fixes, and reviewer time spent correcting the agent’s work.

## Evidence To Gather Next

- Compare agent-produced patches against human-produced patches on the same benchmark tasks using test pass rate, review comments, merge rate, and post-merge regression rate.
- Audit completed agent sessions for command traces, final diffs, blocked requests, and whether reported verification actually matches what was run.

## Open Questions

- How should teams weight speed versus correctness when an agent produces a working but less maintainable solution?
- What minimum verification standard should be required before agent output can be considered review-ready?
# Agent 3 Note

## Angle

Measurement should focus on whether sandboxed coding agents create correct, reviewable, and low-risk changes that reduce human effort.

## Findings

- Useful work is best measured by accepted changes, not activity volume: merged patches, passing tests, resolved issues, and reviewer approval are stronger signals than lines changed or commands run.
- Verification quality matters: agents should leave evidence such as test results, reproduction steps, screenshots, logs, or clear explanations of what was and was not checked.
- Review burden is a key metric: useful agents produce small, coherent diffs with understandable rationale, minimal unrelated churn, and few reviewer-requested corrections.
- Sandbox behavior should be measured directly: teams should track whether agents respect permissions, avoid destructive operations, handle missing access gracefully, and do not invent unverifiable outcomes.
- Long-term value appears in defect rates: escaped bugs, rollbacks, flaky tests, security issues, and follow-up fixes reveal whether agent output was genuinely production-ready.

## Evidence To Gather Next

- Compare agent-authored changes against human-authored baselines for merge rate, review iterations, test pass rate, rollback rate, and time-to-resolution.
- Audit a sample of completed agent tasks for traceability: issue context, diff scope, verification evidence, reviewer comments, and post-merge incidents.

## Open Questions

- How should teams weight speed against later maintenance cost when an agent produces a working but awkward solution?
- What minimum verification evidence should be required before sandboxed agent output is considered ready for human review?
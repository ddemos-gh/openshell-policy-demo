# Agent 3 Note

## Angle

Measurement should focus on whether sandboxed coding agents produce verifiable, reviewable, and maintainable changes, not just whether they complete a prompt.

## Findings

- Useful work is best indicated by passing tests tied to the requested behavior, especially tests added or updated by the agent rather than only preexisting suites.
- Reviewability matters: small, scoped diffs with clear rationale are stronger signals than broad edits that happen to work once.
- Reproducibility is a core sandbox benefit; valuable agents leave behind commands, logs, or summaries that let humans rerun the same checks.
- Human acceptance is necessary but insufficient: merged code, reduced reviewer effort, and low follow-up defect rates are better long-term measures.
- Negative signals include unrelated refactors, hidden dependency changes, flaky verification, and confidence unsupported by executable evidence.

## Evidence To Gather Next

- Compare agent-generated changes against human baselines using review time, test pass rate, revert rate, and post-merge bug reports.
- Audit completed tasks for traceability: prompt intent, files changed, tests run, and whether the final answer accurately reflects the actual work.

## Open Questions

- How should teams weight speed versus correctness when an agent produces plausible code quickly but requires heavier review?
- What minimum verification standard should be required before sandboxed agent output is considered ready for human review?
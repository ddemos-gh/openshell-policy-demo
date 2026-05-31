# Agent 1 Note

## Angle

How authors can prepare a pull request so reviewers can understand the change quickly, evaluate risk, and give useful feedback.

## Findings

- Keep the PR narrowly scoped: one coherent behavior change, bug fix, or refactor is easier to reason about than a mixed bundle of unrelated edits.
- Write the description for a future reviewer, not just the current team: explain the problem, the chosen approach, important tradeoffs, and anything intentionally left out.
- Separate mechanical changes from semantic changes when possible, such as formatting, renames, generated files, or dependency updates.
- Provide a clear validation story: include tests added or updated, commands run, manual verification steps, screenshots, logs, or known gaps.
- Reduce reviewer guesswork by calling out risky areas, migration concerns, compatibility issues, performance impact, and specific places where feedback is most needed.

## Evidence To Gather Next

- Compare review time, comment quality, and defect rate between small focused PRs and large mixed PRs in a real repository.
- Review contribution guides from mature open-source projects to identify recurring PR preparation expectations.

## Open Questions

- What is the practical size threshold where PR review quality starts to decline?
- How much context should live in the PR description versus linked issues, design docs, or commit history?
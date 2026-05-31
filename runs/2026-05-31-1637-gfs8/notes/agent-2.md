# Agent 2 Note

## Angle

Reviewer side: prioritize the diff by risk, behavior, and maintainability before commenting on style.

## Findings

- Start with the user-visible behavior change: confirm the diff actually implements the intended requirement and does not silently alter adjacent workflows.
- Scan for blast radius early: shared utilities, public APIs, migrations, auth, payments, permissions, data deletion, and concurrency deserve deeper review than isolated UI or copy changes.
- Check edge cases before polish: empty states, nulls, invalid input, retries, timeouts, partial failures, backwards compatibility, and upgrade paths often reveal the most expensive defects.
- Verify test coverage matches the risk: high-impact logic should have focused tests for the changed behavior and at least one regression or boundary case.
- Review readability through future maintenance: names, control flow, abstractions, and error handling should make the next change easier to reason about, not merely pass today’s tests.

## Evidence To Gather Next

- Compare recent production incidents or reverted PRs against review comments to see which missed signals would have caught them.
- Sample team code review guidelines from mature engineering orgs and identify common first-pass review priorities.

## Open Questions

- How much should reviewers rely on CI versus manually reasoning through behavior?
- When should a reviewer block on design concerns versus approve with follow-up work?
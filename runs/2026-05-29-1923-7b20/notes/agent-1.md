# Agent 1 Note

## Angle

Adoption depends on whether teams can try sandboxed coding agents with bounded risk, observable behavior, and clear rollback paths.

## Findings

- Trust starts with containment: read/write boundaries, network limits, approval gates, and audit logs make experimentation feel reversible instead of open-ended.
- Teams are more likely to try agents on low-blast-radius work first, such as test generation, dependency cleanup, documentation fixes, lint repairs, and isolated bug fixes.
- Adoption improves when the agent shows its work: explicit plans, file-level diffs, command outputs, and test results let reviewers evaluate behavior using familiar engineering habits.
- The workflow must preserve human ownership. Engineers need to approve risky commands, inspect patches before merge, and override or stop the agent without fighting the tool.
- Success criteria should be practical, not theatrical: reduced time-to-first-patch, fewer review cycles, clean test runs, and no unexpected file or environment changes.

## Evidence To Gather Next

- Compare pilot outcomes from teams using sandboxed agents on narrowly scoped repo tasks versus broader autonomous coding tasks.
- Review incident reports, security evaluations, or internal policy docs describing what controls made agent usage acceptable.

## Open Questions

- What minimum sandbox controls are enough for teams with sensitive code or regulated data?
- How much transparency is useful before agent logs become too noisy for everyday review?
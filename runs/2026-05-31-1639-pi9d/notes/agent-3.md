# Agent 3 Note

## Angle

Maintenance practices that keep runbooks accurate, trusted, and usable during real incidents.

## Findings

- Assign explicit ownership for every runbook, ideally to the service or system owner, so updates have a clear accountable party.
- Add review metadata: last reviewed date, next review date, owner, and related service/version. Staleness should be visible at the top, not buried in history.
- Tie runbook updates to operational change: deployments, architecture changes, alert changes, postmortems, and recurring incident patterns should trigger a runbook check.
- Validate runbooks through drills or real incident retrospectives. A runbook that has not been executed recently should be treated as unproven.
- Prefer executable or verifiable steps where possible: commands, dashboards, alert links, expected outputs, rollback criteria, and escalation paths reduce ambiguity and make drift easier to detect.

## Evidence To Gather Next

- Review recent incident postmortems and check whether any action items required runbook updates or exposed stale instructions.
- Sample existing runbooks for ownership, review dates, broken links, outdated commands, and mismatch with current alerting or deployment flows.

## Open Questions

- What review cadence is appropriate for low-change systems versus fast-moving production services?
- Should stale runbooks trigger warnings, ticket creation, or removal from incident-facing documentation?
# Agent 3 Note

## Angle

Maintenance practices that keep runbooks accurate, trusted, and usable after the system changes.

## Findings

- Assign every runbook a clear owner or owning team; unowned runbooks decay quickly because no one is accountable for updates.
- Treat runbooks as versioned operational artifacts, ideally stored near code or infrastructure definitions so changes can be reviewed alongside system changes.
- Add review triggers, not just review dates: update the runbook after incidents, architecture changes, dependency upgrades, alert changes, and handoff pain.
- Make staleness visible with metadata such as last reviewed date, owner, related services, alert names, dashboards, and known assumptions.
- Validate runbooks through use: incident retrospectives, game days, onboarding exercises, and shadow rotations reveal gaps that passive reviews miss.

## Evidence To Gather Next

- Review recent incidents and check whether the referenced runbooks were accurate, missing, or ignored.
- Sample existing runbooks for ownership, last review date, linked alerts/dashboards, and whether procedures still match current tooling.

## Open Questions

- Should runbook review be enforced through a formal cadence, change-management workflow, or lightweight automation?
- What level of detail keeps a runbook useful without making it expensive to maintain?
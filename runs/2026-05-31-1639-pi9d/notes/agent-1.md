# Agent 1 Note

## Angle

A good runbook turns stressful incident response into a clear sequence of small, verifiable actions.

## Findings

- Steps should be ordered by urgency and dependency: first stabilize impact, then diagnose, then remediate, then verify recovery.
- Each step should include an expected result so responders know whether to continue, retry, escalate, or stop.
- Instructions should use concrete commands, links, owners, dashboards, and thresholds rather than broad guidance like “check the logs.”
- Decision points should be explicit: use simple branching such as “if error rate remains above X for Y minutes, page Z.”
- The runbook should minimize cognitive load with short sections, numbered actions, and clear rollback or “do not proceed” warnings.

## Evidence To Gather Next

- Review recent incident timelines to identify where responders hesitated, repeated work, or lacked a clear next step.
- Compare runbooks from mature SRE teams or public incident-response templates for structure, escalation, and verification patterns.

## Open Questions

- How much diagnostic detail belongs in the main path versus an appendix?
- Who owns keeping commands, dashboards, and escalation contacts current?
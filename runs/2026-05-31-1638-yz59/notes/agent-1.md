# Agent 1 Note

## Angle

How runbook structure can make operational steps easy to follow during incident stress.

## Findings

- Start with a short “when to use this” section so responders can quickly confirm the runbook matches the situation.
- Put prerequisites, required access, expected tools, and safety warnings before action steps to prevent mid-incident stalls.
- Use numbered, single-action steps with clear success criteria after each major action.
- Separate decision points from commands: responders should know when to branch before they execute anything risky.
- Include rollback, escalation, and “stop here if” conditions near the relevant steps, not only at the end.

## Evidence To Gather Next

- Review incident postmortems for examples where unclear runbook ordering caused delays or mistakes.
- Compare runbook templates from SRE, incident response, and platform operations teams.

## Open Questions

- How much context should be included inline versus linked out to keep the runbook fast to scan?
- Should high-risk procedures require confirmation checkpoints even if that slows execution?
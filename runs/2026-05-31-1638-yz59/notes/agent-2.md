# Agent 2 Note

## Angle

A good runbook step is unambiguous when it tells the operator exactly what to do, where to do it, how to verify it, and what to do if the result differs.

## Findings

- Each step should name the exact system, service, environment, account, or interface where the action happens.
- Commands should be copy-ready and include required flags, paths, variables, expected permissions, and safe placeholder examples.
- Every action step should include an expected result, such as output text, status code, dashboard state, log pattern, or metric threshold.
- Decision points should use explicit branching logic: “if X, do Y; if not, do Z,” with no reliance on operator judgment alone.
- Recovery or escalation instructions should be attached to risky or failure-prone steps, including when to stop and who or what process owns the next action.

## Evidence To Gather Next

- Review recent incident runbooks and identify steps that required Slack clarification or tribal knowledge.
- Compare internal runbooks against examples from SRE or incident management guidance, such as Google SRE, Atlassian, or PagerDuty materials.

## Open Questions

- How much context should each step include before the runbook becomes too slow to use during an incident?
- Should command examples prioritize production safety by defaulting to read-only verification before any mutating action?
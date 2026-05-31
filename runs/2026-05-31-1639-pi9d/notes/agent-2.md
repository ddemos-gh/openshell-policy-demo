# Agent 2 Note

## Angle

A good runbook step is unambiguous when it tells the operator exactly what to do, where to do it, how to verify it worked, and what to do if it fails.

## Findings

- Each step should name the exact system, environment, account, dashboard, host, service, or command context before giving the action.

- Actions should be written as observable instructions, not intentions: use “restart `api-worker` with command X” instead of “fix the worker.”

- Every step should include expected output, success criteria, or a validation check so the operator knows whether to continue.

- Decision points need explicit branching rules: define thresholds, error messages, status values, or time limits that determine the next step.

- Risky or irreversible actions should include prerequisites, required approvals, rollback instructions, and a clear stopping condition.

## Evidence To Gather Next

- Review high-quality public incident response runbooks from SRE teams to compare how they express commands, checks, and branches.

- Examine postmortems where ambiguous procedures contributed to delays or mistakes, then map the ambiguity to missing step fields.

## Open Questions

- How much detail should be embedded directly in each step versus linked to supporting documentation?

- Should runbooks enforce a strict step template, or allow different formats for diagnosis, mitigation, rollback, and escalation?
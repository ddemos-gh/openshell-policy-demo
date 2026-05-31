# Multi-Agent Summary

## Executive Summary

A good runbook converts high-pressure operational work into clear, verifiable steps that reduce ambiguity and cognitive load. It should tell responders exactly what to do, how to know whether it worked, when to branch or escalate, and how to avoid unsafe actions. It also needs active ownership and regular validation so responders can trust it during real incidents.

## Strongest Findings

- Steps should be ordered around incident flow: stabilize impact, diagnose, remediate, verify recovery, then document follow-up.
- Each step should include concrete context: system, environment, account, dashboard, host, command, owner, threshold, or link.
- Actions should be specific and observable, using exact commands and checks instead of vague instructions like “investigate logs” or “fix service.”
- Every step should define expected results, success criteria, failure handling, and clear branching rules.
- Risky actions need prerequisites, approvals, rollback instructions, and explicit stopping conditions.
- Runbooks need owners, review dates, update triggers, and validation through drills, incidents, or retrospectives.

## Disagreements Or Tensions

- There is a tradeoff between embedding enough detail to act quickly and keeping the main path short enough to use under stress.
- Different runbook sections may need different formats: diagnosis, mitigation, rollback, escalation, and verification may not fit one rigid template equally well.
- Review cadence may vary by system maturity and change rate; fast-moving services need tighter maintenance than stable systems.
- Stale runbooks are a known risk, but the notes do not settle whether staleness should trigger warnings, tickets, or removal from incident-facing docs.

## Recommended Next Steps

- Audit existing runbooks for ownership, review metadata, exact commands, expected outputs, escalation paths, rollback guidance, and broken links.
- Review recent incidents and postmortems to identify where responders hesitated, repeated work, followed stale instructions, or lacked clear branching criteria.
- Define a lightweight runbook template with required fields for context, action, expected result, failure path, rollback, owner, and review date.
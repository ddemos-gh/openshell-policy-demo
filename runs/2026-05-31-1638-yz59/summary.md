# Multi-Agent Summary

## Executive Summary

A good runbook is fast to identify, safe to execute, and easy to verify under incident pressure. It should combine clear structure, unambiguous action steps, explicit decision logic, and maintenance practices that keep it trusted as systems change.

## Strongest Findings

- Start with a brief “when to use this” section so responders can confirm scope before acting.
- Put prerequisites, access needs, tools, environment details, and safety warnings before procedural steps.
- Use numbered, single-action steps that specify the exact system, account, interface, command, path, flags, and variables involved.
- Pair each major action with expected results: output text, status code, dashboard state, log pattern, or metric threshold.
- Make branching explicit with “if X, do Y; if not, do Z,” especially before risky or irreversible actions.
- Keep runbooks owned, versioned, reviewed after relevant changes, and validated through incidents, game days, onboarding, or shadow rotations.

## Disagreements Or Tensions

- More inline context improves self-sufficiency, but too much detail can slow responders during an incident.
- Confirmation checkpoints and read-only verification improve safety, but may add friction when speed matters.
- Formal review cadences can prevent staleness, but event-based triggers tied to incidents, architecture changes, alerts, and tooling changes may be more effective.
- Runbooks need enough detail to remove tribal knowledge, but excessive specificity can make them expensive to maintain.

## Recommended Next Steps

- Audit recent incident runbooks for unclear steps, missing expected results, stale ownership, and places where responders needed clarification.
- Create or update a standard runbook template with scope, prerequisites, numbered steps, verification, branching, rollback, escalation, owner, and review metadata.
- Validate priority runbooks through a game day, onboarding exercise, or post-incident review, then add change triggers so updates happen when systems or alerts change.
# Multi-Agent Summary

## Executive Summary

Teams should evaluate sandboxed coding agents on controlled risk, reviewable output, and verified engineering outcomes. The strongest pilots keep existing CI, code review, security, and release gates intact while measuring whether agents reduce effort without increasing defects or operational risk.

## Strongest Findings

- Sandboxing must enforce strict boundaries for filesystem access, command execution, network egress, and secrets; agents should not receive ambient credentials or broad production access.

- Reviewability is essential: outputs should be tied to a task, visible as diffs, and easy for humans to accept, edit, reject, or roll back.

- Network access and approvals should be narrow, explicit, and auditable, such as allowing a specific command, domain, or path rather than granting broad session permissions.

- Evaluation should prioritize verified outcomes: passing relevant tests, successful builds, reproducible commands, small scoped diffs, and low post-merge regression rates.

- Pilots should begin with lower-risk tasks such as tests, documentation, bug reproduction, dependency investigation, and narrow refactors.

- Teams should track both productivity and quality: time saved, review burden, CI failures, rework rate, defect rate, rollback frequency, and developer satisfaction.

## Disagreements Or Tensions

- Network restrictions improve security but can reduce usefulness for dependency installation, documentation lookup, and API integration work.

- Human acceptance is useful but imperfect; reviewers may approve plausible changes that are incorrect or hard to maintain.

- More autonomy may increase speed, but it can also raise review cost, security risk, noisy side effects, and resource consumption.

- Missing context remains around the best approval UX and the minimum verification standard required before agent output is review-ready.

## Recommended Next Steps

- Run a controlled pilot on low-to-medium risk tasks with existing CI, code review, branch protection, security scans, and release gates unchanged.

- Build an evaluation scorecard covering test pass rate, build success, diff size, review comments, rework, merge rate, regressions, rollback frequency, and reviewer time.

- Perform sandbox validation tests for credential access, filesystem boundaries, command approvals, network egress controls, logging, and escalation behavior.
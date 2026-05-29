# Multi-Agent Summary

## Executive Summary

Ship coding agents to production support engineers only as bounded incident copilots at first. The strongest near-term value is faster diagnosis, better codebase navigation, higher-quality escalations, and draft remediation, while the largest risks come from unsafe production actions, data exposure, and over-trust under pressure. A read-only, auditable, least-privilege rollout is the prudent starting point.

## Strongest Findings

- Agents can materially improve time-to-diagnosis by correlating logs, stack traces, recent diffs, runbooks, prior incidents, feature flags, and related code paths.
- Support engineers benefit most when agents help with unfamiliar systems: mapping symptoms to owners, repositories, dependencies, configs, and historical context.
- Routine remediation is valuable but should remain human-controlled: agents can draft patches, test updates, config changes, rollback notes, and workarounds for review.
- Operational risk is significant if agents inherit broad human credentials or can run write actions against production, databases, admin tools, or CI/CD systems.
- Prompt injection and contaminated context are real concerns because agents will read tickets, customer files, logs, web content, and stack traces that may contain adversarial instructions.
- Guardrails should include read-only defaults, task-scoped credentials, tiered approvals, explicit command previews, rollback plans, and full audit trails attached to support or incident records.

## Disagreements Or Tensions

- The main tension is leverage versus control: agents are most useful when close to operational context, but that same access increases blast radius and data exposure risk.
- There is unresolved disagreement over whether agents should ever take write actions in customer environments, even with approval.
- Least-privilege access may conflict with diagnosis quality when sensitive customer data is necessary to understand an issue.
- Ownership of approvals during severe incidents is unclear: support engineer, incident commander, service owner, or automated policy.
- More evidence is needed on actual support workflows before deciding which tasks should be automated, approval-gated, or categorically blocked.

## Recommended Next Steps

- Run a read-only pilot on recent or live support tickets and measure time-to-diagnosis, escalation quality, and engineer trust.
- Audit production support access paths and classify agent actions into allowed, approval-required, and blocked categories.
- Design a guardrail model using existing CI/CD, IAM, break-glass, and incident tooling, with audit logs, short-lived credentials, and explicit approval flows.
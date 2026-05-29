# Agent 1 Note

## Angle

Coding agents can give production support engineers the most leverage by turning diagnosis, codebase navigation, and routine remediation into faster, more repeatable workflows.

## Findings

- Agents are strongest as incident copilots: they can quickly inspect logs, stack traces, recent diffs, runbooks, and related code paths to propose likely causes and next checks.

- Support engineers gain leverage on unfamiliar services because agents can map symptoms to owners, repositories, feature flags, config, dependencies, and prior incidents faster than manual searching.

- Routine fixes are a high-value target: agents can draft small patches, test updates, config changes, rollback instructions, or customer-specific workarounds while the engineer reviews and controls execution.

- Agents can reduce escalation load by helping support engineers produce higher-quality bug reports: clear repro steps, suspected root cause, impacted versions, relevant logs, and candidate fixes.

- The best production use case is bounded assistance, not autonomous operation: agents should recommend, summarize, and prepare actions, while humans approve changes that affect customers or live systems.

## Evidence To Gather Next

- Measure time-to-diagnosis and escalation quality across a sample of recent support tickets with and without an agent-assisted workflow.

- Review incident and support ticket history to identify the most common repetitive tasks: log triage, environment comparison, config inspection, rollback prep, patch drafting, or repro creation.

## Open Questions

- What production permissions should agents have, especially for reading logs, accessing customer data, and proposing or applying changes?

- How much reliability is required before support engineers trust agent-generated diagnoses during high-pressure incidents?
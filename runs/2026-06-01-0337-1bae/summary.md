# Multi-Agent Summary

## Executive Summary

Teams adopt sandboxed agents when risk is visibly bounded and output is easy to verify. The strongest adoption pattern is phased autonomy: start read-only, add scoped write/network access, and reserve privileged actions for human approval. Trust depends on clear permissions, auditable traces, small reviewable changes, and fast rollback.

## Strongest Findings

- Explicit, inspectable permissions lower adoption friction, especially when teams can begin in read-only or approval-gated modes.
- Short-lived, task-scoped credentials are safer than exposing broad developer tokens to agent environments.
- Network egress controls are central: teams need deny-by-default policies, allowlists, proxy logging, or approval-based browsing for external access.
- Audit trails are a recurring requirement, including commands run, files inspected or changed, credentials issued, hosts contacted, tests executed, and assumptions made.
- Useful agent output fits existing engineering workflows: small diffs, issue context, reviewable commits, CI validation, and targeted regression coverage.
- Teams value agents that surface uncertainty and stop or escalate when requirements, permissions, tests, or production risks are unclear.

## Disagreements Or Tensions

- There is tension between tight credential/network controls and productivity; excessive per-task setup may slow teams more than it reduces risk.
- Internet access remains unresolved: options include curated allowlists, monitored open egress, or approval-based browsing, each with different usability and security tradeoffs.
- Passing tests are necessary but not sufficient; teams still need better signals for maintainability, reviewer effort, revert risk, and defect escape rate.
- The right level of audit detail is unclear: logs must satisfy security and compliance needs without overwhelming reviewers.

## Recommended Next Steps

- Interview teams piloting sandboxed agents to identify which permission, credential, and audit controls moved them from trial use to daily workflows.
- Benchmark agent-produced pull requests against human pull requests using review time, requested-change rate, revert rate, CI pass rate, and escaped defects.
- Define a practical adoption model with staged modes: read-only research, scoped code-editing, and privileged release/deployment actions gated by explicit human approval.
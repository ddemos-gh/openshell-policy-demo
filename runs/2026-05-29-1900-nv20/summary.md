# Multi-Agent Summary

## Executive Summary

Teams should evaluate sandboxed coding agents as operational systems, not just code generators. The strongest evaluations combine security containment, reviewable engineering output, realistic task performance, and clear audit trails for permissions, commands, and claims.

## Strongest Findings

- Trust depends on containment: filesystem scope, network access, secrets exposure, dependency execution, and shared-state mutation must be explicit and enforceable.

- Credential isolation is table stakes. Agents should not inherit ambient secrets from shells, dotfiles, SSH agents, cloud CLIs, package managers, or browser/session stores unless deliberately granted.

- Output quality should be measured by accepted, reviewed patches that pass tests, builds, linting, and post-merge scrutiny, not by agent-reported completion.

- Reviewability is central: changes should arrive as normal diffs with clear rationale, reproducible verification steps, honest disclosure of blocked actions, and no hidden side effects.

- Sandboxed agents should be tested under realistic constraints, including denied network access, read-only filesystems, missing inputs, protected user changes, and risky dependency execution paths.

- Adoption should start narrowly with low-risk maintenance, documentation, tests, refactors with strong coverage, and isolated prototypes before product-critical work.

## Disagreements Or Tensions

- Strong network restrictions reduce exfiltration risk but may slow common workflows such as dependency installation, builds, and test execution.

- Speed can conflict with review cost: a fast agent that produces broad or hard-to-maintain patches may be less valuable than a slower agent with smaller, auditable changes.

- “Sandboxed,” “restricted,” and “read-only” labels are insufficient without practical validation of actual enforcement behavior.

- Missing context remains around minimum acceptable sandbox guarantees and how to benchmark multi-step tasks where code compiles but design or business behavior is wrong.

## Recommended Next Steps

- Run controlled sandbox tests using canary secrets, network probes, dependency scripts, local socket checks, and write attempts to verify enforcement claims.

- Measure agent work against human baselines using reviewer time, requested changes, test pass rate, reverted commits, reopened bugs, and post-merge defects.

- Define an adoption policy that specifies allowed task categories, approval granularity, logging and redaction rules, CI requirements, rollback expectations, and escalation procedures.
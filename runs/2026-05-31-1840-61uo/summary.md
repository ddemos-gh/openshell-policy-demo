# Multi-Agent Summary

## Executive Summary

Teams should evaluate sandboxed coding agents on safety, reviewability, and verified engineering value, not prompt completion alone. The strongest evaluation programs combine least-privilege sandbox controls, clear audit trails, executable verification, and measurements of downstream code quality. Adoption should start with constrained pilots on low-risk repositories before expanding autonomy.

## Strongest Findings

- Sandboxes should default to least privilege across filesystem access, network egress, secrets, environment variables, command execution, and dependency installation.

- Secret isolation and deny-by-default or allowlisted network access are central controls, especially because agents may execute repository code, tests, build scripts, or generated commands.

- Reviewability is a primary success criterion: teams need scoped diffs, rationale, command logs, dependency changes, approvals, test results, and clear summaries.

- Existing engineering controls should remain the approval layer: branches, pull requests, CI, code owners, audit logs, and policy checks.

- Productivity metrics should be paired with safety and quality metrics, including review time, test pass rate, PR acceptance rate, revert rate, defect rate, policy violations, and incidents avoided or caused.

- Strong agents produce verifiable work: relevant tests, reproducible commands, traceable changes, and final reports that accurately match what was done.

## Disagreements Or Tensions

- More autonomy can improve speed, but increases the risk that human review happens too late, especially near privilege boundaries.

- Strict approvals and network restrictions improve safety, but poor approval UX may encourage teams to bypass controls.

- Human acceptance is useful but insufficient; teams still need post-merge quality signals to detect plausible but fragile changes.

- The notes do not settle the right default network policy: fully disabled, package-registry-only, domain allowlists, or finer protocol-level controls.

## Recommended Next Steps

- Run a small pilot on non-critical repositories and track acceptance rate, review burden, test failures, reverts, defects, blocked tasks, and policy violations.

- Audit the sandbox model for filesystem scope, secret handling, environment filtering, network policy, dependency installation behavior, approval prompts, and logs.

- Test adversarial repositories that attempt credential access, environment leakage, network exfiltration, malicious build scripts, install hooks, and hidden dependency changes.
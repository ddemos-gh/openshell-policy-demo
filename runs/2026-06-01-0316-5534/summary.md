# Multi-Agent Summary

## Executive Summary

Teams should evaluate sandboxed coding agents on boundedness, security, task outcomes, and traceability rather than raw productivity claims. The strongest adoption signal is whether agents can produce useful, reviewable changes while respecting filesystem, network, credential, and approval limits. Evaluation should include both success behavior and failure behavior.

## Strongest Findings

- Containment is foundational: teams need clear controls for filesystem access, network access, secrets exposure, destructive commands, and production-adjacent systems.

- Credential and network isolation should be tested directly, including access to `.env`, SSH keys, cloud configs, package tokens, internal services, metadata endpoints, and broad environment variables.

- Reviewable artifacts are essential: useful runs should leave behind diffs, command logs, test results, assumptions, skipped checks, and a concise rationale.

- Success should be measured by task outcomes: passing tests, fixed bugs, implemented behavior, accepted patches, low regression rate, and developer confidence.

- Human approval gates should focus on risk boundaries such as dependency installs, migrations, credential handling, CI/CD edits, production configuration, and external network access.

- Failure behavior matters: agents should stop on uncertainty, preserve unrelated work, avoid broad silent rewrites, explain blockers, and make rollback straightforward.

## Disagreements Or Tensions

- Network restrictions create a tradeoff: deny-by-default policies reduce exfiltration and supply-chain risk, but overly strict controls may block common development workflows.

- Approval policies need balance: highly granular approvals are safer and more auditable, but may become burdensome for routine work.

- Teams may differ on whether sandbox policy should be standardized across the organization or vary by repository sensitivity, production access, and compliance requirements.

- There is unresolved weighting between complete patches with weak explanations and partial patches with excellent diagnostics.

## Recommended Next Steps

- Run a controlled benchmark on real backlog tasks, measuring accepted diffs, test pass rate, regression rate, patch size, human corrections, and time-to-acceptance.

- Red-team sandbox boundaries with realistic credential, network, package installation, git, DNS, and internal-service access attempts.

- Define approval and evidence standards for each trust level, from local-only assistance through PR creation, auto-merge, and deployment-adjacent workflows.
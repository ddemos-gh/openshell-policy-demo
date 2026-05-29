# Multi-Agent Summary

## Executive Summary

Teams should evaluate sandboxed coding agents by combining adoption, security, and engineering-quality criteria. The strongest signal is not how much an agent does, but whether it produces correct, reviewable, low-risk changes while respecting sandbox boundaries. Evaluation should start with narrow tasks, explicit controls, and measurable outcomes.

## Strongest Findings

- Trust depends on containment: filesystem boundaries, network limits, approval gates, credential isolation, and audit logs make agent use bounded and reversible.

- Default-deny credential access is essential. Agents should not automatically inherit shell environments, SSH keys, cloud credentials, package tokens, browser cookies, `.env` files, or local credential stores.

- Network access should be deny-by-default or tightly allowlisted by destination, protocol, and purpose; broad outbound access creates exfiltration risk.

- Success should be measured by accepted outcomes: merged patches, passing tests, resolved issues, reviewer approval, and low rollback or defect rates.

- Reviewability is central. Agents should produce small coherent diffs, explain rationale, show command outputs, report test results, and clearly state what was not verified.

- Human ownership must remain intact through inspectable approvals, patch review before merge, stop controls, and clear rollback paths.

## Disagreements Or Tensions

- Productivity and security can conflict when agents need package installs, documentation access, or external APIs but network allowlists slow work down.

- Transparency is valuable, but excessive logs may create review noise; teams need enough traceability without overwhelming engineers.

- Speed is not sufficient if output creates maintenance debt; teams need to weigh fast working patches against long-term code quality.

- Minimum sandbox requirements may vary by context, especially for teams handling sensitive code, regulated data, or production credentials.

## Recommended Next Steps

- Run a constrained pilot on low-blast-radius tasks such as tests, documentation fixes, lint repairs, dependency cleanup, and isolated bugs.

- Define evaluation metrics before rollout: merge rate, review iterations, test pass rate, time-to-resolution, rollback rate, escaped defects, and sandbox policy violations.

- Audit the runtime directly: visible environment variables, mounted paths, credential helpers, SSH agents, network behavior, approval gates, and command execution policy.
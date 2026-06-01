# Agent 1 Note

## Angle

Adoption should start only when the workflow gives teams clear control over scope, visibility, reversibility, and measurable engineering value.

## Findings

- Trust starts with containment: agents should run in isolated sandboxes with explicit read/write boundaries, no ambient production credentials, and auditable network access.

- Teams need reviewable outputs, not opaque automation: every proposed change should be visible as a diff, tied to a task, and easy for a human to accept, modify, or reject.

- Adoption is safer for low-to-medium risk work first, such as test generation, refactors with narrow scope, documentation updates, dependency investigation, and bug reproduction.

- The workflow should preserve existing engineering controls: CI, code review, branch protection, security scanning, ownership rules, and release gates should remain the source of truth.

- A trustworthy pilot needs measurable criteria: time saved, defect rate, review burden, test pass rate, rollback frequency, and developer satisfaction should be tracked before broad rollout.

## Evidence To Gather Next

- Compare agent-generated pull requests against human-authored pull requests on review comments, CI failures, rework rate, and post-merge defects.

- Review sandbox and permission models from current coding-agent platforms, especially how they handle filesystem access, network access, secrets, dependency installation, and command approval.

## Open Questions

- What level of autonomy is acceptable before the review cost outweighs the productivity gain?

- How should teams evaluate risks from agent actions that are technically sandboxed but still consume expensive resources, leak metadata, or create noisy operational side effects?
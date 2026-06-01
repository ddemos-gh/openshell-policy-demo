# Agent 1 Note

## Angle

Adoption should depend on whether the sandboxed workflow can be tested, bounded, audited, and rolled back before it touches production paths.

## Findings

- Trust starts with containment: teams need clear guarantees about filesystem scope, network access, secrets exposure, and whether the agent can execute destructive commands.
- A trial is easier to justify when the agent produces inspectable artifacts: diffs, test output, command logs, cited assumptions, and a short rationale for changes.
- Human approval gates matter most at risk boundaries, such as dependency changes, migrations, credential handling, CI/CD edits, and production configuration.
- Evaluation should focus on repeatable engineering tasks first: test fixes, small refactors, documentation updates, issue triage, and isolated feature work.
- Adoption criteria should include failure behavior, not just success rate: the agent should stop on uncertainty, preserve unrelated work, avoid silent broad rewrites, and make rollback straightforward.

## Evidence To Gather Next

- Compare audit logs from several sandboxed agent runs against the team’s existing code review and compliance requirements.
- Run a controlled benchmark on real backlog tasks, measuring accepted diffs, required human corrections, test pass rate, time saved, and incidents avoided by sandbox limits.

## Open Questions

- What level of command/network restriction is strict enough for security without making the agent ineffective?
- Who owns approval policy design: platform engineering, security, individual teams, or a shared governance group?
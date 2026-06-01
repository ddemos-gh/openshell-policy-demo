# Agent 3 Note

## Angle

Measure sandboxed coding agents by whether their changes improve the target task while preserving repo health, traceability, and developer confidence.

## Findings

- Useful work should be measured against task outcomes, not activity volume: passing tests, fixed failing cases, implemented requested behavior, and reproducible verification matter more than number of files edited or lines changed.

- High-signal evaluation combines automated checks with human review: tests, linting, type checks, build success, and runtime smoke tests catch mechanical regressions, while code review catches maintainability, scope creep, and misunderstood intent.

- Sandboxed agents need explicit measurement of constraint handling: good agents should work within read/write/network limits, surface blockers clearly, avoid destructive actions, and provide usable next steps when they cannot complete a task.

- Traceability is a core quality signal: the final answer should connect changes to files, commands run, test results, skipped checks, and remaining risk so a human can quickly decide whether to trust or continue the work.

- Longitudinal metrics are important: merge rate, revert rate, review comments per change, escaped defects, and time-to-acceptance reveal whether agent output stays useful beyond a single demo task.

## Evidence To Gather Next

- Compare agent patches against a benchmark suite of real repository issues with hidden tests, measuring pass rate, regression rate, patch size, and human acceptance.

- Review production PRs assisted by sandboxed agents and track downstream outcomes such as reviewer intervention, follow-up fixes, reverts, and incidents.

## Open Questions

- How should teams weight a partially correct patch with excellent diagnostics versus a complete patch with weak explanation?

- What minimum evidence should be required before allowing sandboxed agent output into higher-trust workflows such as auto-merge or deployment?
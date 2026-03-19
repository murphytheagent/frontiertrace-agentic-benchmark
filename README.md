# FrontierTrace Agentic Benchmark

Last updated: 2026-03-19 22:20 UTC

Start here:
1. Read `roadmap.md` for active milestone and gate criteria.
2. Read `docs/README.md` for detailed design and implementation docs.

This repository evaluates agentic proof-generation capability on frontier math/ML-theory tasks that require extensive literature search and synthesis under open-web conditions.

Current status:
- Milestone 1 is still carried by PR #1 (`feat/m1-schema-freeze`), which remains `OPEN` / `CLEAN` at published head `9a80847`.
- The local checkout is still one docs-only commit ahead at `87d8c36`, so the working branch and the GitHub PR are separate review surfaces.
- Direct repo inspection still reproduces the same three integrity blockers: packaged `statement_spans` overrun `statement_text`, the instance schema does not enforce `task_variant=solved_hidden_solver => status_by_cutoff.label=solved`, and `ft_m1_008` still marks `partial` with no supporting papers.
- GitHub still shows 2 unresolved non-outdated review threads, and the latest bounded local review again timed out before a terminal verdict, so the branch is not locally review-cleared.

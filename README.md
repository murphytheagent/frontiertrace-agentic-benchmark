# FrontierTrace Agentic Benchmark

Last updated: 2026-03-20 19:47 UTC

Start here:
1. Read `roadmap.md` for active milestone and gate criteria.
2. Read `docs/README.md` for detailed design and implementation docs.

This repository evaluates agentic proof-generation capability on frontier math/ML-theory tasks that require extensive literature search and synthesis under open-web conditions.

Current status:
- Milestone 1 is still carried by PR #1 (`feat/m1-schema-freeze`), which remains `OPEN` / `CLEAN` at published head `ba1783f`.
- The working branch and the GitHub PR surface currently match on that published head again.
- Direct repo inspection still reproduces the same three integrity blockers: packaged `statement_spans` overrun `statement_text`, the instance schema does not enforce `task_variant=solved_hidden_solver => status_by_cutoff.label=solved`, and `ft_m1_008` still marks `partial` with no supporting papers.
- GitHub now shows 3 unresolved non-outdated review threads, and the latest bounded local review again timed out before a terminal verdict, so the branch is not locally review-cleared.

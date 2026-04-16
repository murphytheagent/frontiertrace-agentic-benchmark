# FrontierTrace Agentic Benchmark

Last updated: 2026-04-16 11:59 UTC

Start here:
1. Read `roadmap.md` for active milestone and gate criteria.
2. Read `docs/README.md` for detailed design and implementation docs.

This repository evaluates agentic proof-generation capability on frontier math/ML-theory tasks that require extensive literature search and synthesis under open-web conditions.

Current status:
- Milestone 1 is still carried by PR `#1` (`feat/m1-schema-freeze`), which remains `OPEN` / `CLEAN` on published head `c08b28e`.
- The latest clean-clone local review returned a terminal verdict and re-confirmed three integrity blockers on that head: packaged `statement_spans` overrun `statement_text`, the instance schema does not enforce `task_variant=solved_hidden_solver => status_by_cutoff.label=solved`, and `ft_m1_008` still marks `partial` with no supporting papers.
- GitHub now shows `15` unresolved non-outdated review threads. Refresh the live GitHub review state before using this README as merge evidence, because the thread count is inherently time-varying.
- This checkout may carry local maintenance doc refreshes beyond the published PR head; treat the blocker list above as the state-of-record, not as proof that the local worktree exactly matches GitHub.

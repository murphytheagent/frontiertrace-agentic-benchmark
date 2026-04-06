# FrontierTrace Agentic Benchmark Backlog

## Review Blockers (Milestone 1)

These must be resolved before Milestone 1 can pass review:

- `source_statement.statement_spans` still overrun the packaged `statement_text` in rows such as `ft_m1_001` and `ft_m1_008`.
- `schema/frontiertrace-instance-v1.schema.json` still does not encode the documented `solved_hidden_solver => solved` invariant.
- `ft_m1_008` still has `supporting_paper_ids=[]`.
- The independent relabel gate has not been revisited.

## Open Review Surface

- PR `#1` (`feat/m1-schema-freeze` -> `main`) is still `OPEN` / `CLEAN` on published head `31bea68` with `15` unresolved non-outdated review threads; refresh GitHub before using this note as merge evidence because the thread count is volatile.
- The 2026-04-06 bounded `review_project.sh --base main --timeout 240` pass returned a terminal review and re-confirmed the same packaged blocker set, so the branch is still not locally review-cleared.

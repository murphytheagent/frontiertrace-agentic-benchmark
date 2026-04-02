# FrontierTrace Agentic Benchmark Backlog

## Review Blockers (Milestone 1)

These must be resolved before Milestone 1 can pass review:

- `source_statement.statement_spans` still overrun the packaged `statement_text` in rows such as `ft_m1_001` and `ft_m1_008`.
- `schema/frontiertrace-instance-v1.schema.json` still does not encode the documented `solved_hidden_solver => solved` invariant.
- `ft_m1_008` still has `supporting_paper_ids=[]`.
- The independent relabel gate has not been revisited.

## Open Review Surface

- PR #1 (`feat/m1-schema-freeze` -> `main`) is still `OPEN` / `CLEAN` on published head `2116381` with `11` unresolved non-outdated review threads.
- The 2026-04-02 bounded `review_project.sh --base main --timeout 240` pass timed out again before a terminal verdict, though the partial review still re-confirmed the same packaged blocker set, so the branch is still not locally review-cleared.

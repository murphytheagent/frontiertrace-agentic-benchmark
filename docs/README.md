# FrontierTrace Docs Index

Last updated: 2026-04-01 11:18 UTC

This folder holds detailed project knowledge and reference materials. The root `roadmap.md` is the execution-gated source of truth for delivery sequencing.

## Core docs
- `project-init-workflow.md`: one-time project bootstrap procedure.
- `project-resume-workflow.md`: milestone-scoped continuation procedure.
- `project-init-resume-workflow.md`: compatibility pointer to the split workflow docs.
- `source-deliverables.md`: consolidated summary of the three design PDFs.
- `canonical-schema.md`: canonical problem representation contract.
- `assumption-normalization-guidelines.md`: annotator rules for building the assumption ledger consistently.
- `evaluator-interface.md`: evaluator input/output contract and scoring hooks.
- `lineage-tracing.md`: lineage graph + solver-candidate tracing design.
- `solver-validation-and-audit.md`: solver verification and selective audit policy.
- `open-web-runtime-policy.md`: internet-enabled runtime and anti-cheat controls.
- `references.md`: source bibliography and adjacent benchmark landscape.

## Data + schemas
- `schema/frontiertrace-instance-v1.schema.json`: frozen Milestone 1 canonical instance schema.
- `schema/frontiertrace-prediction-v1.schema.json`: prediction payload contract for evaluator integration.
- `data/seeds/m1_seed_set_v1.jsonl`: first 10 canonicalized seed problems for Milestone 1 validation.

## Current status note
- PR #1 (`feat/m1-schema-freeze`) is still the active Milestone 1 review surface on published head `5fd89cf`, with `9` unresolved non-outdated review threads.
- The local checkout and the published PR head now match again.
- The blocker set is unchanged: the packaged seed `statement_spans` still overrun `statement_text`, the instance schema still omits the documented `solved_hidden_solver => solved` invariant, and `ft_m1_008` still lacks supporting papers for its `partial` label.
- The latest bounded local review timed out again before a terminal verdict, but the partial review did not change the blocker set above.

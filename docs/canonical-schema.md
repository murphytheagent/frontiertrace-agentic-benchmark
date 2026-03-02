# Canonical Schema (Frozen v1)

Last updated: 2026-03-02 01:47 UTC

## Scope
Milestone 1 freezes the canonicalization contract for FrontierTrace instance packaging.

Normative schema files:
- `schema/frontiertrace-instance-v1.schema.json`
- `schema/frontiertrace-prediction-v1.schema.json`

Seed dataset for gate checks:
- `data/seeds/m1_seed_set_v1.jsonl`

## Canonicalization model
Each instance must include two aligned layers:
1. `source_statement`: faithful, citation-linked problem text.
2. `canonical_problem`: normalized representation used by lineage tracing and solver validation.

## Required instance fields
- `instance_id`: stable id (`ft_m1_###` in seed set).
- `problem_id`: semantic problem id that can survive split/version changes.
- `task_variant`: `solved_hidden_solver` or `still_open_by_cutoff`.
- `cutoff_date`: ISO date used for temporal integrity.
- `source_statement`: source title/url/text + source span anchors.
- `canonical_problem`: canonical statement, domain objects, assumptions, acceptance criteria, allowed equivalences.
- `status_by_cutoff`: gold label (`solved|partial|open|refuted|unclear`) + rationale + supporting papers.
- `annotator_metadata`: primary/secondary annotator ids, agreement score, review status.

## Invariants
1. Every canonical claim must be source-grounded.
2. Every acceptance criterion must be testable from solver evidence.
3. Assumption entries must include both `kind` and `status`.
4. `task_variant=solved_hidden_solver` requires `status_by_cutoff.label=solved`.
5. `agreement_score` must be in `[0,1]`; Milestone 1 gate expects aggregate >= 0.85.

## Label contract
- `solved`: acceptance criteria fully met under aligned assumptions.
- `partial`: at least one core criterion unmet, but meaningful progress established.
- `open`: no known solver satisfies core criteria by cutoff.
- `refuted`: statement is disproven by valid counterexample/theorem.
- `unclear`: evidence is conflicting or insufficient for reliable adjudication.

## Milestone 1 gate hooks
- Schema completeness check: all required fields must be non-null for 10/10 seeds.
- Consistency check: aggregate annotator agreement from `annotator_metadata.agreement_score`.
- Reproducibility check: independent relabeling pass compares `status_by_cutoff.label` and assumption alignment.

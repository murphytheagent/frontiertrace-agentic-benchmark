# Canonical Schema (Draft v0)

Last updated: 2026-03-02 00:33 UTC

## Design intent
Represent each open problem in two aligned layers:
1. Faithful human-readable statement.
2. Machine-checkable normalized form for equivalence and assumption matching.

## Required fields
- `problem_id`
- `source_statement_text`
- `canonical_statement`
- `objects_and_domains`
- `assumption_ledger`
- `solution_acceptance_criteria`
- `allowed_equivalences`
- `status_by_cutoff`
- `status_rationale`

## Validation checks
- Every canonical field must map to one or more source spans.
- Assumption ledger must enumerate all explicit and implicit preconditions required for solver matching.
- Acceptance criteria must specify what constitutes full solve vs partial solve.

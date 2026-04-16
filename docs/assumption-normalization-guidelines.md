# Assumption Normalization Guidelines (M1)

Last updated: 2026-03-02 01:47 UTC

## Purpose
Standardize how annotators extract and normalize assumptions into `canonical_problem.assumption_ledger`.

## Rule set
1. Keep one atomic claim per assumption row.
2. Preserve mathematical meaning; normalize wording only.
3. Tag each assumption with `kind`:
- `domain`: object set or geometry constraints.
- `regularity`: smoothness, convexity, boundedness, margin, or Lipschitz assumptions.
- `oracle`: gradient/subgradient/stochastic oracle access assumptions.
- `algorithmic`: step-size, initialization, or update-rule assumptions.
- `evaluation`: cutoff/time/version assumptions.
4. Tag each assumption with `status`:
- `required`: must hold for a full-solve claim.
- `relaxed`: optional or weaker variant accepted by equivalence policy.
- `unknown`: unresolved in source; cannot be asserted as required.

## Normalization procedure
1. Copy source statement text that encodes assumptions.
2. Split compound clauses into atomic rows.
3. Resolve symbol aliases (`g-convex` vs `geodesically convex`) using `allowed_equivalences`.
4. Mark mismatch-sensitive assumptions as `required`.
5. Add clarifying note only when source wording is ambiguous.

## Conflict policy
- If two papers use incompatible assumptions, keep both rows and mark incompatible mapping in evaluator notes.
- Do not collapse strict vs non-strict variants into one row.
- If assumption meaning is uncertain, use `status=unknown` and route to audit.

## Quality checklist
- No assumption row contains conjunctions joined by `and/or`.
- Every required assumption is referenced by at least one acceptance criterion.
- Assumption ids are stable and unique within each instance.

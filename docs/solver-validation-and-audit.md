# Solver Validation and Selective Audit (Draft v0)

Last updated: 2026-03-02 00:33 UTC

## Validation flow
1. Extract solver theorem claims and matching assumptions.
2. Check entailment against canonical acceptance criteria.
3. Assign confidence score and audit tier.

## Audit tiers
- Auto-accept: high confidence and no assumption mismatch flags.
- Light audit: moderate confidence or minor ambiguity.
- Heavy audit: low confidence, conflicting claims, or major assumption drift.

## Human audit requirement
Human audit remains required, but selectively applied by confidence tier. Final release labels should always have auditable evidence trails.

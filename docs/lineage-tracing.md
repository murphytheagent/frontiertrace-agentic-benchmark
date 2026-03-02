# Lineage Tracing (Draft v0)

Last updated: 2026-03-02 00:33 UTC

## Pipeline
1. Seed from canonicalized open-problem source papers.
2. Expand typed graph with citation edges, semantic-neighbor edges, and lexical-paraphrase edges.
3. Apply temporal filter by benchmark cutoff.
4. Rank candidate solver papers using theorem-match and assumption-alignment first.
5. Produce candidate lineage chains and confidence scores.

## Candidate ranking signals
- Theorem overlap with acceptance criteria.
- Assumption compatibility with canonical ledger.
- Explicit claim strength (full solve vs partial progress).
- Citation support from independent follow-up papers.

## Guardrails
- Do not assign solved status from metadata-only signals.
- Treat weak-citation/no-citation cases as valid if theorem-level evidence is explicit.

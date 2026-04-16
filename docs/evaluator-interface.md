# Evaluator Interface (Draft v1 for M1)

Last updated: 2026-03-02 01:47 UTC

## Scope
Defines the minimum evaluator contract between FrontierTrace instances and model predictions.

## Input contracts
- Instance schema: `schema/frontiertrace-instance-v1.schema.json`
- Prediction schema: `schema/frontiertrace-prediction-v1.schema.json`

## Evaluator API
```text
score(instance: FrontierTraceInstanceV1, prediction: FrontierTracePredictionV1) -> ScoreResult
```

## ScoreResult fields
- `instance_id`
- `schema_valid` (bool): both payloads validate against schemas.
- `label_correct` (bool): predicted label equals `status_by_cutoff.label`.
- `assumption_alignment_score` (0-1): fraction of required assumptions correctly handled.
- `criterion_coverage_score` (0-1): fraction of required acceptance criteria explicitly addressed.
- `provenance_score` (0-1): evidence span quality and theorem citation coverage.
- `final_score` (0-1): weighted aggregate after provenance gating.
- `failure_reasons` (string array)

## Provenance gating
- If zero theorem-level evidence spans are supplied, cap `final_score` at `0.20`.
- If predicted `solved` without meeting all required criteria, force `label_correct=false`.

## Default weights (pilot)
- `label_correct`: 0.40
- `assumption_alignment_score`: 0.25
- `criterion_coverage_score`: 0.20
- `provenance_score`: 0.15

## Batch evaluation outputs
- `aggregate_metrics.json`: macro averages and per-label performance.
- `instance_scores.jsonl`: one `ScoreResult` record per instance.
- `audit_queue.jsonl`: instances with low confidence or schema violations.

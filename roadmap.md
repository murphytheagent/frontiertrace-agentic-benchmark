# FrontierTrace Agentic Benchmark Roadmap

Last updated: 2026-03-02 01:14 UTC
Project slug: `frontiertrace-agentic-benchmark`

This roadmap consolidates three prior design deliverables into one execution-gated plan:
1. `frontiertrace_benchmark_proposal.pdf` (initial benchmark blueprint)
2. `frontiertrace_hidden_solver_blueprint.pdf` (hidden-solver redesign)
3. `frontiertrace_hidden_solver_qna_athena_deep.pdf` (canonical form, lineage, audit, open-web runtime policy)

## Delivery Boundary Rules

- Work advances only when the current milestone gate metrics are validated and recorded.
- If any gate metric fails, the milestone remains open; downstream implementation is blocked.
- Milestone evidence must be written to project `docs/` before gate sign-off.

## Milestone 0: Project Foundation

### Sections
- Repository scaffold and document structure
- Canonical roadmap and docs index
- Task lifecycle conventions for future sessions

### Deliverables
- Root `roadmap.md`
- `docs/README.md`
- `docs/project-init-workflow.md`
- `docs/project-resume-workflow.md`

### Success Metrics (must pass)
- `docs/` exists and contains references, workflow, and implementation notes.
- The roadmap defines milestone gates with objective pass/fail criteria.
- A new session can start by reading roadmap + docs without external chat context.
- Project remote strategy decision is documented (`remote-enabled` or deferred with trigger condition).

## Milestone 1: Problem Canonicalization Spec Freeze

### Sections
- Faithful statement layer and machine-checkable layer
- Assumption ledger and equivalence policy
- Acceptance criteria contract for solved/partial/open labels

### Deliverables
- Frozen canonical instance schema (`docs/canonical-schema.md`)
- Annotator guidance for assumption normalization
- 10 seed problems converted into canonical form

### Success Metrics (must pass)
- Schema completeness: 100% required fields populated on 10/10 seeds.
- Canonicalization consistency: >= 0.85 agreement on assumption extraction across two annotators.
- Label reproducibility: independent reviewer reproduces canonical labels on >= 9/10 seeds.

## Milestone 2: Lineage Tracing Pipeline

### Sections
- Typed graph construction (citation + semantic + lexical edges)
- Candidate solver ranking and theorem-match scoring
- Temporal cutoff enforcement and leak controls

### Deliverables
- Lineage extraction pipeline spec (`docs/lineage-tracing.md`)
- Candidate scoring/ranking policy
- Gold lineage annotations for first 20 cases

### Success Metrics (must pass)
- Solver candidate recall@5: >= 0.90 on solved cases in the 20-case set.
- Assumption-alignment precision (top-1 candidate): >= 0.85.
- Temporal integrity: 0 post-cutoff solver leaks in evaluation packaging.

## Milestone 3: Solver Validation and Selective Audit

### Sections
- Solver-proof verification contract
- Auto-accept vs light-audit vs heavy-audit triage
- Dispute protocol for ambiguous or partial resolutions

### Deliverables
- Validation rubric (`docs/solver-validation-and-audit.md`)
- Audit queue policy with confidence thresholds
- Adjudication templates for disputed cases

### Success Metrics (must pass)
- Auto-accept precision: >= 0.98 on audited sample.
- Ambiguous-case capture: >= 0.95 of ambiguous cases routed to light/heavy audit.
- Inter-auditor final-label agreement: >= 0.80 Cohen's kappa on sampled reviews.

## Milestone 4: Open-Web Runtime and Anti-Cheat Controls

### Sections
- Internet-enabled execution policy (no closed RAG dependency)
- Hidden-solver leak prevention and plagiarism checks
- Post-solution understanding checks to prevent copy-only wins

### Deliverables
- Runtime policy (`docs/open-web-runtime-policy.md`)
- Anti-cheat acceptance-test suite
- Logging and provenance requirements

### Success Metrics (must pass)
- Hidden-solver direct-copy attacks: <= 5% success on red-team suite.
- Metadata-only / citation-centrality baselines: near-floor performance (< 20% of full-agent score).
- Provenance compliance: 100% of accepted outputs include required theorem-span citations.

## Milestone 5: Pilot Build and Baseline Evaluation (30-50 Instances)

### Sections
- Pilot corpus assembly across solved-hidden-solver and still-open-by-cutoff tasks
- Baseline agent runs and robustness slices
- Error taxonomy and benchmark documentation

### Deliverables
- Pilot release bundle under `outputs/pilot-v1/`
- Baseline scorecard and stress-test report
- Annotator and evaluator documentation

### Success Metrics (must pass)
- Pilot size: 30-50 validated instances with documented provenance.
- Variant coverage: at least 40% solved-hidden-solver and 40% still-open-by-cutoff.
- Evaluation reliability: rerun variance <= 5% on primary aggregate metrics.
- Published error taxonomy covers >= 90% of observed failures in baseline runs.

## Milestone 6: Public Benchmark v1 Readiness

### Sections
- Release governance and split policy
- Submission/evaluation contract
- Maintenance plan for rolling updates

### Deliverables
- Public docs package (`docs/release/`)
- Private test policy and leaderboard contract
- Governance policy for disputed labels and post-release corrections

### Success Metrics (must pass)
- Reproducibility check: independent rerun reproduces baseline within tolerance.
- Governance coverage: all dispute/update paths documented with owners and SLAs.
- Launch checklist sign-off completed across data, evaluation, and policy.

## Blocking Criteria

- Any unresolved ambiguity in canonical problem equivalence blocks Milestone 2+.
- Any unresolved solver-validation disagreement above threshold blocks Milestone 4+.
- Any anti-cheat acceptance failure blocks Milestone 5+.

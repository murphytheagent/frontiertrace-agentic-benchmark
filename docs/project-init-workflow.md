# Project Init Workflow

Last updated: 2026-03-02 01:14 UTC

## Purpose
Define one-time setup steps for creating a new FrontierTrace project workspace.

## Required Steps
1. Create or verify project repository at `projects/frontiertrace-agentic-benchmark/`.
2. Create root `roadmap.md` with milestone gates and pass/fail success metrics.
3. Create `docs/` structure and core reference files.
4. Record remote strategy explicitly:
   - `remote-enabled`: remote bootstrap started now, or
   - `local-only (temporary)`: defer reason and trigger for enabling remote.
5. Write initialization checkpoint in `projects/frontiertrace-agentic-benchmark.md`.

## Completion Rule
- This workflow runs once per project bootstrap.
- Do not rerun initialization during normal milestone continuation.

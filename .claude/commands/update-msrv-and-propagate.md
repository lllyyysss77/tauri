---
name: update-msrv-and-propagate
description: Workflow command scaffold for update-msrv-and-propagate in tauri.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-msrv-and-propagate

Use this workflow when working on **update-msrv-and-propagate** in `tauri`.

## Goal

Updates the Minimum Supported Rust Version (MSRV) and propagates the change across all relevant configuration, manifest, and CI files.

## Common Files

- `.changes/msrv-*.md`
- `.github/workflows/test-*.yml`
- `Cargo.toml`
- `bench/**/Cargo.toml`
- `crates/**/Cargo.toml`
- `examples/**/Cargo.toml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update MSRV version in documentation or change log (e.g., .changes/msrv-*.md).
- Update MSRV in all Cargo.toml files across the workspace, including examples and templates.
- Update MSRV in CI workflow files (e.g., .github/workflows/test-*.yml) to ensure tests run on the new MSRV.
- Commit all changes together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.
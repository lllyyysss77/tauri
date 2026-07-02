---
name: address-msrv-todos-and-security
description: Workflow command scaffold for address-msrv-todos-and-security in tauri.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /address-msrv-todos-and-security

Use this workflow when working on **address-msrv-todos-and-security** in `tauri`.

## Goal

Refactors code to address MSRV-related TODOs, updates dependencies, and suppresses or documents security advisories.

## Common Files

- `.cargo/audit.toml`
- `Cargo.lock`
- `crates/**/src/**/*.rs`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update dependency lockfile (Cargo.lock) and audit configuration (.cargo/audit.toml).
- Refactor code in various Rust source files to address MSRV TODO comments and clippy warnings.
- Suppress or document security advisories as needed.
- Commit all changes together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.
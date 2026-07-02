---
name: bugfix-with-example-and-test-updates
description: Workflow command scaffold for bugfix-with-example-and-test-updates in tauri.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /bugfix-with-example-and-test-updates

Use this workflow when working on **bugfix-with-example-and-test-updates** in `tauri`.

## Goal

Fixes a bug in core code, updates related example code, and modifies or adds tests to ensure the fix works.

## Common Files

- `.changes/*.md`
- `crates/**/src/**/*.rs`
- `examples/**/src-tauri/src/*.rs`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Fix bug in main Rust source file(s).
- Update example code in examples/**/src-tauri/src/*.rs as needed.
- Update or add test code to verify the fix.
- Add a change log entry in .changes/.
- Commit all changes together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.
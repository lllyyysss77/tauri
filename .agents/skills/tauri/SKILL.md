```markdown
# tauri Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, coding conventions, and key workflows used in the `tauri` Rust codebase. You will learn how to structure code, follow commit conventions, and execute common maintenance and bugfix tasks efficiently. This guide is especially useful for contributors aiming to make high-quality, consistent contributions to the project.

## Coding Conventions

- **File Naming:**  
  Use PascalCase for file names.  
  _Example_:  
  ```
  MyModule.rs
  ```

- **Import Style:**  
  Use relative imports within the crate.  
  _Example_:  
  ```rust
  use super::MyModule;
  use crate::utils::Helper;
  ```

- **Export Style:**  
  Use named exports for modules and functions.  
  _Example_:  
  ```rust
  pub mod MyModule;
  pub fn do_something() { /* ... */ }
  ```

- **Commit Messages:**  
  Follow [Conventional Commits](https://www.conventionalcommits.org/) with the following prefixes:
    - `feat`: New features
    - `fix`: Bug fixes
    - `refactor`: Code refactoring
  _Example_:  
  ```
  feat(core): add window event handler
  fix(cli): correct argument parsing
  refactor(api): simplify permission checks
  ```

## Workflows

### Update MSRV and Propagate
**Trigger:** When you want to bump the Minimum Supported Rust Version (MSRV) for the project.  
**Command:** `/bump-msrv`

1. Update the MSRV version in documentation or changelog (e.g., `.changes/msrv-*.md`).
2. Update the MSRV in all `Cargo.toml` files across the workspace, including examples and templates:
    ```toml
    [package]
    rust-version = "1.70"
    ```
3. Update the MSRV in CI workflow files (e.g., `.github/workflows/test-*.yml`) to ensure tests run on the new MSRV.
4. Commit all changes together with a conventional commit message.

**Files Involved:**
- `.changes/msrv-*.md`
- `.github/workflows/test-*.yml`
- `Cargo.toml`
- `bench/**/Cargo.toml`
- `crates/**/Cargo.toml`
- `examples/**/Cargo.toml`

---

### Address MSRV TODOs and Security
**Trigger:** When you want to clean up code for a new MSRV, resolve clippy lints, and handle security advisories.  
**Command:** `/address-msrv-todos`

1. Update the dependency lockfile (`Cargo.lock`) and audit configuration (`.cargo/audit.toml`).
2. Refactor code in Rust source files to address MSRV TODO comments and clippy warnings.
    ```rust
    // TODO(MSRV): Remove this workaround once MSRV >= 1.70
    ```
3. Suppress or document security advisories as needed in `.cargo/audit.toml`.
4. Commit all changes together with a conventional commit message.

**Files Involved:**
- `.cargo/audit.toml`
- `Cargo.lock`
- `crates/**/src/**/*.rs`

---

### Bugfix with Example and Test Updates
**Trigger:** When you need to fix a bug that affects both the main codebase and example projects, ensuring coverage with tests.  
**Command:** `/fix-bug-with-examples`

1. Fix the bug in the main Rust source file(s).
    ```rust
    // Before
    if value = 0 { ... }

    // After
    if value == 0 { ... }
    ```
2. Update example code in `examples/**/src-tauri/src/*.rs` as needed.
3. Update or add test code to verify the fix.
4. Add a changelog entry in `.changes/`.
5. Commit all changes together with a conventional commit message.

**Files Involved:**
- `.changes/*.md`
- `crates/**/src/**/*.rs`
- `examples/**/src-tauri/src/*.rs`

## Testing Patterns

- **Test File Pattern:**  
  Test files use the `*.test.ts` pattern (TypeScript), though the primary codebase is Rust.  
- **Testing Framework:**  
  The specific testing framework is unknown from this analysis, but tests are likely run via Rust's built-in test harness and possibly with additional TypeScript tests for JS bindings or integrations.

- **Example Rust Test:**
  ```rust
  #[cfg(test)]
  mod tests {
      use super::*;

      #[test]
      fn test_feature() {
          assert_eq!(my_function(), expected_value);
      }
  }
  ```

## Commands

| Command                  | Purpose                                                                 |
|--------------------------|-------------------------------------------------------------------------|
| /bump-msrv               | Update the MSRV and propagate changes across manifests and CI workflows. |
| /address-msrv-todos      | Refactor for new MSRV, resolve lints, and handle security advisories.    |
| /fix-bug-with-examples   | Fix a bug, update examples, and add or update tests.                    |
```

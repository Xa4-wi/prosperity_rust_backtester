# Workspace Changelog

This file tracks local changes made to the upstream `prosperity_rust_backtester` source after cloning it into the Prosperity workspace.

## 2026-04-05

### Workspace Integration

- Added workspace-aware root detection in [src/runner.rs](/Users/xavierwinkelmann/Prosperity/ProsperityRustBacktester/src/runner.rs).
- The backtester now prefers the parent Prosperity repo root when it finds directories such as `Data/`, `Bots/`, or `Analysis/`.
- This makes Python trader imports work more naturally for bots stored outside the Rust backtester directory.

### Trader Discovery

- Updated [src/cli.rs](/Users/xavierwinkelmann/Prosperity/ProsperityRustBacktester/src/cli.rs) so automatic trader discovery checks:
  - `../Bots/`
  - `../Bots/archive/`
  - then the original local `scripts/`, `traders/submissions/`, and `traders/`

### Dataset Discovery

- Updated [src/cli.rs](/Users/xavierwinkelmann/Prosperity/ProsperityRustBacktester/src/cli.rs) so the default dataset source prefers the parent workspace `../Data/` directory when present.
- Added workspace dataset aliases:
  - `workspace`
  - `prosperity`
  - `repo`
- Mapped tutorial-style day aliases like `tutorial-1` and `tutorial-2` to the workspace `Data/` directory when that integration is active.
- Added clear error messages for submission aliases when only raw workspace CSV data is available.

### Documentation

- Updated [README.md](/Users/xavierwinkelmann/Prosperity/ProsperityRustBacktester/README.md) with workspace-specific behavior and example commands.

### Notes

- No Rust compilation was run locally during this integration because `cargo` and `rustc` are not installed in the current environment.

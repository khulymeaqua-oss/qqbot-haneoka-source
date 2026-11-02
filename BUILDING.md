# Building the QQBot Haneoka session executable

The engine source is pinned to `1c76b078cf7cb411771aaeee0c3a6cde24c265cc`. The accepted Windows
toolchain is `rustc 1.99.1 (58cf8f9c3 2026-10-13)` / `cargo 1.99.1 (5f94df478 2026-08-27)` with
the `x86_64-pc-windows-gnu` target. The upstream tree does not contain a `rust-toolchain.toml`, so use
these recorded versions (or document and requalify any replacement).

From the Corresponding Source bundle, run:

```powershell
powershell -NoProfile -File qqbot-integration/scripts/haneoka-rust/build-session.ps1 `
  -Upstream upstream/ournotes-team-builder `
  -Cargo E:/isolated-rust/cargo/bin/cargo.exe `
  -CargoHome E:/isolated-rust/cargo `
  -RustupHome E:/isolated-rust/rustup `
  -TargetDir E:/isolated-rust/target `
  -Output E:/isolated-rust/qqbot_session.exe
```

The script uses `cargo build --locked --release`, verifies `UPSTREAM_COMMIT` (or a Git checkout), and
prints the output SHA-256. Absolute source/target paths can affect Rust binary bytes; compare the
deployment binary to `SOURCE_MANIFEST.json`, and use the same paths/toolchain when byte identity is
required. Protocol/SHA/capability verification is available through `verify-release.ps1`.

`qqbot-integration` conservatively contains the complete Team Builder plugin source plus the Haneoka
core/client/engine workspaces and root dependency/build manifests used by that integration. It does
not contain private runtime configuration or user data. Rebuilding the entire private QQBot is not a
condition for rebuilding the Rust session executable.

Before a maintenance window, install the already verified executable into a versioned runtime path.
The installer refuses to replace an existing file unless `-Replace` is explicit; preserve that old
file as the rollback binary first:

```powershell
powershell -NoProfile -File scripts/haneoka-rust/install-session.ps1 `
  -CandidateBinary E:/staging/qqbot_session.exe `
  -ExpectedSha256 d3656ae68102c2a1694ced0985a0adafe58f7dd7e616da33d529b98cb867a0cd `
  -Destination E:/Code/QQrobot/runtime/haneoka/qqbot_session-1c76b078.exe
```

Production enablement requires `HANEOKA_RUST_ENGINE_BINARY`, `QQBOT_RUST_ARENA_ENGINE=1`, and an
unauthenticated HTTPS `QQBOT_HANEOKA_SOURCE_URL` serving this exact versioned bundle. Validate the URL
from a separate unauthenticated client before enabling the flag.

The upstream LICENSE and NOTICE are included. Computed results must display:
`Team-building algorithm from Haneoka — https://haneoka.org`.

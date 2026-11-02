# Third-party source inventory

- `upstream/ournotes-team-builder`: Haneoka `ournotes-team-builder` at
  `1c76b078cf7cb411771aaeee0c3a6cde24c265cc`, licensed AGPL-3.0-only. Its original `LICENSE`,
  `NOTICE`, Cargo manifests and lock file are included unchanged.
- Rust crate dependencies are pinned by the included upstream `Cargo.lock`; their package metadata
  and licence declarations can be reproduced with `cargo metadata --locked`.
- `qqbot-integration`: the source actually used by QQBot to build, invoke and present the Haneoka
  session executable. The repository's declared licence is recorded in its included `package.json`.

The required visible notice is: `Team-building algorithm from Haneoka — https://haneoka.org`.

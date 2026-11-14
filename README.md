# QQBot Haneoka corresponding source

## Current release (from 2026-11-15)

The bot now runs one Haneoka engine build for every team-building feature:

- Release: `haneoka-271d022-linux-26b239f` (GitHub Release of this repository)
- Engine: `ournotes-team-builder` @ `271d02287100136b0024a1969c736c06d2337eb4` (unmodified)
- Executable: `qqbot_session`, Linux x86_64, SHA-256 `26b239f68b55be2cdc96a43515fe4c04d8848f65c945fc07d96e64c0910bdb82`
- Archive: `qqbot-haneoka-source-271d022-linux-26b239f.zip`, SHA-256 `c35f1153427bfd29e261de009ff621f1ad314ed2650bb84bf03ab5b8e10127c8`;
  rebuilding from it reproduces the executable byte for byte (see the archive's `BUILDING.md`).

Earlier releases (`haneoka-7f80fa3-qqbot-f5ccb59`, `haneoka-1c76b078-qqbot-4d819eb`) remain available; those builds stay in the
bot image for rollback. The text below describes the first release.


This repository publishes the corresponding source for the Haneoka-powered Arena and shared-team
multi-song feature used by a personal QQBot deployment.

The versioned source archive is attached to the matching GitHub Release. It contains:

- the unmodified upstream `ournotes-team-builder` source pinned to
  `1c76b078cf7cb411771aaeee0c3a6cde24c265cc`;
- the Rust JSON session wrapper and lockfile used to build the deployed executable;
- the QQBot integration source needed to invoke and present this feature;
- build instructions, `LICENSE`, `NOTICE`, third-party inventory, and a source/binary manifest.

Deployed binary SHA-256:
`d3656ae68102c2a1694ced0985a0adafe58f7dd7e616da33d529b98cb867a0cd`

Session protocol: `haneoka-session/1`

The source archive intentionally excludes runtime configuration, credentials, databases, user data,
logs, Team Box data, and the private QQBot repository history.

Haneoka: <https://haneoka.org>

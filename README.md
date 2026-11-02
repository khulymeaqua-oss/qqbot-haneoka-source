# QQBot Haneoka corresponding source

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

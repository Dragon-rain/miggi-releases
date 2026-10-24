# Miggi Desktop downloads and alpha update metadata

Public distribution files only. No application source code, private signing keys,
personal memory, provider credentials or raw diagnostic logs belong here.

`channels/alpha/metadata/` contains signed TUF metadata. Clients bootstrap from
the public root embedded in their verified application package, not from this
README or the website's display catalog.

Hash-named immutable targets are stored as assets of the `update-alpha` technical
prerelease. Human-readable installers and SHA-256 sidecars use versioned releases.
Never replace an existing installer, versioned metadata file or hash-named asset.
Publish targets first, versioned metadata next and timestamp last (one Git commit).
Retain old metadata and targets needed by existing clients and root transitions.

Personal-alpha EXEs currently have no Windows Authenticode signature. TUF protects
updates but does not remove Windows UAC, SmartScreen or organizational policy.
Do not bypass OS protections. First installation is a separate bootstrap step.

The current personal-alpha candidate is `0.1.0-alpha.18`, built from clean source
`215f8949790553843903a0b535bc09a7fcbd6dad`. Its EXE is unsigned by Windows;
TUF metadata and immutable targets provide the alpha update-channel verification.
The exact supported update source is the published `alpha.12` package.
The earlier transition from exact `alpha.7` to `alpha.12` is MANUAL: its old updater
does not understand release format v2/internal protocol 0.14. It is not a direct
alpha.7-to-alpha.18 update. Never remove Home or guard state to bypass errors.
Publication/download checks do not claim installed upgrade acceptance.

The first configured baseline was `0.1.0-alpha.7`. Older `alpha.2` is an immutable
download-test artifact without an updater; it does not acquire one retroactively.
Real installed A-to-B, repair and clean-machine acceptance remain separate tests.

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

The first configured baseline is `0.1.0-alpha.7`. Older `alpha.2` is an immutable
download-test artifact without an updater; it does not acquire one retroactively.
Real installed A-to-B, repair and clean-machine acceptance remain separate tests.

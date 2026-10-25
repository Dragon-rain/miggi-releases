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

The current personal-alpha candidate is `0.1.0-alpha.19`, built from clean source
`bb466933040e8a14fcdd041d4d21b42512a596a4`. Its EXE is unsigned by Windows;
TUF metadata and immutable targets provide the alpha update-channel verification.
The exact supported in-app update source for alpha.19 is the published `alpha.18`
package. A manual alpha.19 installer can also safely recover an app-only-removed
alpha.12 installation when its protected receipt matches the verified alpha.12
package; it does not silently bypass unknown or altered installation state.
The earlier transition from exact `alpha.7` to `alpha.12` is MANUAL: its old updater
does not understand release format v2/internal protocol 0.14. Installed alpha.12
users need the separately verified alpha.18 installer before alpha.19; the new
channel descriptor does not promise a direct alpha.12-to-alpha.19 update.
Never remove Home or guard state to bypass errors.
Publication/download checks do not claim installed upgrade acceptance.

The first configured baseline was `0.1.0-alpha.7`. Older `alpha.2` is an immutable
download-test artifact without an updater; it does not acquire one retroactively.
Real installed A-to-B, repair and clean-machine acceptance remain separate tests.

# Release policy

This policy applies to every release published from a May Ethereal repository.

## Versioning

| Artifact kind | Scheme | Example |
| --- | --- | --- |
| Public libraries and tools | Semantic Versioning | `v0.3.0` |
| Internal product builds | `YYYYMMDD-<short-sha>` | `20261109-ec7e30a` |
| Console payloads | `YYYYMMDD-<target-firmware>` | `20261109-1400` |

A breaking change to a public API or artifact layout bumps the major version.
Internal product builds are immutable: a change to the same day's build is a
new build, never a re-tag.

## What a release must contain

1. **A green pipeline** for the exact commit being released, on a protected
   default branch.
2. **A signed artifact.** Every downloadable binary is signed with Sigstore
   keyless signing in CI (`cosign sign-blob --bundle`), producing a
   `<artifact>.sigstore.json` bundle next to the artifact. The bundle is part
   of the release and is verified by the deploy path before installation.
   `May-Ethereal/.github/.github/workflows/reusable-release-sign.yml` performs
   the signing and publishes the signed release manifest.
3. **A digest.** `<artifact>.sha256` next to the artifact.
4. **An SBOM** (CycloneDX) for anything with dependencies, also signed.
5. **A release manifest** listing, per artifact: digest, bundle, signer
   identity and source commit.
6. **Release notes** that name the source commit and the changes, including
   security fixes.

## Release process

1. Work on a branch; open a pull request; get one maintainer approval.
2. Merge to the default branch. The pipeline builds, scans and signs.
3. Tag the release on the merge commit (`vX.Y.Z`).
4. Publish the artifacts, digests, bundles, SBOMs and manifest from the CI
   artifacts for that commit — never from a local build.

Releases are cut by members of the `@May-Ethereal/maintainers` team. Only
someone who can approve the pull request should tag the release.

## What must never happen

- Committing release binaries, keys, certificates or dumps to a repository.
- Publishing an artifact whose signature was produced outside CI.
- Shipping a release whose pipeline is failing or was skipped.
- Re-using a version number for different content.
- Bypassing the signature verification in a deploy path. There is no opt-out
  flag; a missing or invalid signature stops the deployment.

## Security fixes

Security fixes are released as a new patch version on the affected line and on
the current line. Support for the previous minor line continues for at least
six months after a new minor release, and the support window is stated in the
release notes.

## Deprecation

A deprecation is announced in release notes before the removal happens, with
the replacement named and a removal version. Breaking changes to a public
artifact layout are announced for at least one minor release before the
layout changes.

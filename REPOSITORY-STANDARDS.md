# Repository standards

Every repository in the organization is expected to meet the standards below.
They exist so that a new checkout is immediately understandable, and so that a
release can be built and verified without tribal knowledge.

## Required files

| Path | Requirement |
| --- | --- |
| `README.md` | What it is, how to build it, how to run it, what it does *not* do |
| `LICENSE` | SPDX identifier, matching the license stated in the README |
| `SECURITY.md` | Optional — the org policy in this repository applies when absent |
| `CONTRIBUTING.md` | Optional — the org policy in this repository applies when absent |
| `CODEOWNERS` | Required for every repository with more than one maintainer |
| `.gitignore` | Build output, IDE state, local environment files |
| `.github/workflows/` | At least one CI workflow that runs on pull requests |

## Branch and review policy

- `main` is the default branch and is protected: pull request required, at
  least one approving review, no force pushes, no branch deletion, linear
  history, and required status checks.
- Administrators are subject to the same rules as everyone else.
- Commits are signed or verified where the repository enables it.
- Squash merges only, so the history stays linear and revertible.

> GitHub Free only allows branch protection on public repositories. Private
> repositories in this organization are unprotected until the plan is upgraded
> — that upgrade is a tracked prerequisite, not an accepted state.

## CI requirements

- Every action is pinned to a full commit SHA. Version tags are not accepted
  as a pin.
- `permissions:` is declared at the workflow level and narrowed per job.
- No workflow writes to the repository except from the default branch.
- Secrets are never passed to forked pull requests and never printed.
- The org-wide secret scan can be reused from any repository:
  ```yaml
  jobs:
    security:
      uses: May-Ethereal/.github/.github/workflows/reusable-security-scan.yml@main
  ```
  It scans for secrets, audits npm, Python and Rust dependencies, and fails on
  tracked credential files.

## Dependencies

- Lockfiles are committed and used by CI (`npm ci`, `uv sync --locked`).
- Automated dependency updates are reviewed, not auto-merged.
- Renamed or transferred dependencies are recorded in the README's attribution
  section.

## Never commit

- Private keys, certificates, `.pem`, `.key`, `.pfx`, `.p12`, `.env` files.
- Release binaries, disk or memory dumps, `.exe`, `.elf`, `.bin` payloads.
- Build output (`dist/`, `build/`, `target/`, `node_modules/`, `__pycache__/`).
- Anything from a customer environment.

If a credential was committed, removing it in a later commit is not enough:
rotate it, then remove it, and record the rotation.

## Visibility

- A repository is public only when every file in it may be published under its
  stated license. Internal product code, customer-facing payloads, licensing
  services and their keys stay private.
- Forks keep their upstream attribution and license. The README states the
  upstream project and what the fork changes.
- A repository that becomes public is reviewed before it is flipped, the same
  way a release is reviewed.

## Naming

| Thing | Convention | Example |
| --- | --- | --- |
| Repository | `Product-Component`, `Product-PS4` | `Injector-PS4` |
| Release artifact | `<app>-<version>.<ext>` | `aetherauth-20261109.tar.gz` |
| Release digest | `<artifact>.sha256` | `aetherauth-20261109.tar.gz.sha256` |
| Signature bundle | `<artifact>.sigstore.json` | `aetherauth-20261109.tar.gz.sigstore.json` |
| Branch | `feat/…`, `fix/…`, `chore/…` | `fix/loader-bootstrap-encoding` |

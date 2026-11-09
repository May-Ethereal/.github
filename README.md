# .github

Organization-wide community health files, policies and defaults for
[**May Ethereal**](https://github.com/May-Ethereal).

GitHub automatically applies the files in this repository to **every** repo in
the org that does not define its own equivalent.

## Contents

| Path | Purpose |
| --- | --- |
| `profile/README.md` | Renders on the org profile page (`github.com/May-Ethereal`) |
| `CODE_OF_CONDUCT.md` | Org-wide Code of Conduct (Contributor Covenant 2.1) |
| `CONTRIBUTING.md` | Default contribution guidelines |
| `SECURITY.md` | Vulnerability reporting policy (org-level security policy) |
| `SUPPORT.md` | Where to get help |
| `GOVERNANCE.md` | Roles, owners, teams, decision making |
| `RELEASES.md` | Versioning, signing and release policy |
| `REPOSITORY-STANDARDS.md` | Required files, CI rules, visibility and naming rules |
| `CODEOWNERS` | Default reviewers for this repo |
| `.github/ISSUE_TEMPLATE/` | Bug report + feature request forms, chooser config |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default PR template |
| `.github/FUNDING.yml` | Sponsor button config (disabled until filled) |
| `.github/workflows/reusable-security-scan.yml` | Reusable org-wide secret and dependency scan |
| `.github/workflows/reusable-release-sign.yml` | Reusable Sigstore keyless signing and release manifest |

## Repository template

New repositories should be created from
[`May-Ethereal/repo-template`](https://github.com/May-Ethereal/repo-template),
which already contains the license, the security and contribution pointers,
`CODEOWNERS`, a `.gitignore` and a CI workflow that runs the organization
security scan.

## Using the reusable workflows

Any repository can call them:

```yaml
jobs:
  security:
    uses: May-Ethereal/.github/.github/workflows/reusable-security-scan.yml@main

  release:
    needs: [build]
    permissions:
      contents: read
      id-token: write
    steps:
      - uses: actions/checkout@<full-commit-sha>
      - run: ./scripts/build-release.sh
      - uses: May-Ethereal/.github/.github/workflows/reusable-release-sign.yml@main
        with:
          artifacts: 'dist/*.tar.gz'
          upload-path: 'dist'
          release-name: 'my-app-release-${{ github.sha }}'
```

Pin the calling workflow to a commit SHA when you want it to be immutable, and
remember that a reusable workflow inherits the caller's `permissions` unless it
declares its own.

## Settings not covered by files

These are Settings-page toggles (no file can set them).

Applied:

- [x] Dependabot alerts and security updates enabled on every repository
- [x] `vulnerability-alerts` enabled on every repository, automated security fixes on
- [x] Teams created with least privilege: `@May-Ethereal/maintainers` (write) and
      `@May-Ethereal/org-admins` (admin)
- [x] Branch protection on the public repositories: required pull request,
      required code-owner review, conversation resolution, linear history, no
      force pushes, no branch deletion, administrators included
- [x] Default repository permission set to read

Still open, and why:

- [ ] **Require two-factor authentication for all members.** The members are
      the two org owners; this is a click on Org → Settings → Authentication.
- [ ] **Verify the `ethereal.tokyo` domain.** Blocked until the domain
      publishes working DNS and a mail domain; the domain does not currently
      resolve.
- [ ] **Enable secret scanning and push protection.** These are GitHub Advanced
      Security features and are not available on the current plan.
- [ ] **Branch protection on the private repositories.** GitHub Free only
      offers branch protection for public repositories; the private repositories
      need a plan upgrade.
- [ ] **Enable private vulnerability reporting** on repositories where it is
      not on by default.
- [ ] **Add a default repository ruleset** for the org once private-repository
      rulesets are available on the plan.

## External prerequisites

These cannot be completed from this repository:

| Prerequisite | Why it is external |
| --- | --- |
| DNS records and a monitored mailbox for `ethereal.tokyo` | Needed by `SECURITY.md`, `CODE_OF_CONDUCT.md` and the website's `security.txt` |
| GitHub plan upgrade (Team or Enterprise) | Unlocks secret scanning, push protection, private-repository branch protection and org rulesets |
| Two-factor authentication for both owners | Org authentication settings |

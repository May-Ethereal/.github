# .github

Organization-wide community health files and defaults for
[**May Ethereal**](https://github.com/May-Ethereal).

GitHub automatically applies the files in this repository to **every** repo in
the org that does not define its own equivalent.

## Contents

| Path | Purpose |
| --- | --- |
| `profile/README.md` | Renders on the org profile page (`github.com/May-Ethereal`) |
| `CODE_OF_CONDUCT.md` | Org-wide Code of Conduct (Contributor Covenant 2.1) |
| `CONTRIBUTING.md` | Default contribution guidelines |
| `SECURITY.md` | Vulnerability reporting policy |
| `SUPPORT.md` | Where to get help |
| `GOVERNANCE.md` | Roles, owners, teams, decision making |
| `CODEOWNERS` | Default reviewers for this repo |
| `.github/ISSUE_TEMPLATE/` | Bug report + feature request forms, chooser config |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default PR template |
| `.github/FUNDING.yml` | Sponsor button config (disabled until filled) |

## Fill-in fields

Search for `{{` and replace each org-specific field before publishing:

- `profile/README.md` — tagline and About section
- `SECURITY.md` — security contact address
- `CODE_OF_CONDUCT.md` — conduct contact address

## Publishing

Create the repo as **public** and named exactly `.github`, then push:

```bash
cd May-Ethereal-.github
git init -b main
git add .
git commit -m "chore: org community health files and profile"
git remote add origin git@github.com:May-Ethereal/.github.git
git push -u origin main
```

> The repo **must** be public and named `.github` for org-wide defaults and the
> profile page to take effect.

## Settings not covered by files

These are Settings-page toggles (no file can set them); do them in
**Org → Settings**:

- [ ] Require two-factor authentication for all members
- [ ] Verify domain `ethereal.tokyo` (requires working DNS — currently the
      domain does not resolve)
- [ ] Enable Dependabot alerts + security updates (org default)
- [ ] Enable secret scanning + push protection (org default)
- [ ] Enable private vulnerability reporting (org default)
- [ ] Add a default branch ruleset: require PR review + status checks on `main`
- [ ] Create teams (`owners`, `maintainers`, `contributors`) with least
      privilege
- [ ] Set the org description

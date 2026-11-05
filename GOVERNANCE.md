# Governance

This document describes how the May Ethereal organization is run.

## Roles

| Role | Responsibility |
| --- | --- |
| **Owner** | Full administrative control of the org: billing, membership, security policy, repository creation. |
| **Maintainer** | Triage issues, review and merge pull requests, manage releases for assigned repositories. |
| **Contributor** | Anyone who submits issues or pull requests. |

## Owners

| Owner | GitHub |
| --- | --- |
| あつあげ (Atsuage) | [@AtsuageZ](https://github.com/AtsuageZ) |
| M.H (NetVar) | [@NetVar1337](https://github.com/NetVar1337) |

Owners are the final decision-makers and administer the organization's
settings, security policy, and team structure.

## Teams

Repository access is granted through **teams** with least-privilege roles, not
by adding individuals as org-wide admins. Recommended baseline:

| Team | Repo role | Purpose |
| --- | --- | --- |
| `@May-Ethereal/owners` | Admin | Org administration (Owners above) |
| `@May-Ethereal/maintainers` | Maintain | Day-to-day repo maintenance |
| `@May-Ethereal/contributors` | Write | Trusted recurring contributors |

## Decision making

- Routine changes proceed through normal pull-request review (one maintainer
  approval minimum).
- Changes to org-wide policy (this file, security policy, default rulesets)
  require agreement from the Owners.
- Disagreements that cannot be resolved by maintainers are escalated to Owners.

## Adding and removing members

- New maintainers are nominated by an existing maintainer or owner and confirmed
  by an owner.
- Members who are inactive for an extended period or who violate the
  [Code of Conduct](CODE_OF_CONDUCT.md) may have access revoked by an owner.

## Repository standards

Every repository should include, or inherit from this `.github` repo:

- `README`, `LICENSE`, and a description
- Branch protection / ruleset on the default branch (require PR review + CI)
- Dependabot alerts, secret scanning, and push protection enabled

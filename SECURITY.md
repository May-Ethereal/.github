# Security Policy

This is the organization-wide policy for every May Ethereal repository. It is
the policy GitHub shows on the organization's Security tab.

## Reporting a vulnerability

**Do not open a public issue for security vulnerabilities.**

Preferred channel — GitHub private vulnerability reporting:

1. Go to the affected repository's **Security** tab.
2. Click **Report a vulnerability**.
3. Provide a description, reproduction steps, affected versions, and impact.

Fallback channel — email **security@ethereal.tokyo**.

> Operational prerequisite: `security@ethereal.tokyo` only works once the domain
> publishes MX records and a monitored mailbox is configured behind it. Until
> that is in place, use GitHub private vulnerability reporting, and say so
> explicitly in the report if the address bounces.

## What to expect

| Stage | Target |
| --- | --- |
| Acknowledgement of report | within 3 business days |
| Initial assessment / severity | within 7 business days |
| Fix or mitigation plan | communicated after assessment |
| Public disclosure | coordinated with the reporter after a fix ships |

## Scope

- **In scope:** source code in May Ethereal repositories and released artifacts.
- **Out of scope:** third-party dependencies (report upstream), social
  engineering, and physical attacks.

## Reporting on the website

The public site reports through the same channels. RFC 9116 `security.txt` is
published at <https://ethereal.tokyo/.well-known/security.txt>.

## Safe harbor

We will not pursue legal action for good-faith security research that respects
this policy, avoids privacy violations and service disruption, and gives us a
reasonable window to remediate before any disclosure.

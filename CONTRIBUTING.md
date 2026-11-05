# Contributing to May Ethereal

Thanks for your interest in contributing. These guidelines apply across all
May Ethereal repositories unless a repository overrides them with its own
`CONTRIBUTING.md`.

## Before you start

- Read our [Code of Conduct](CODE_OF_CONDUCT.md).
- Search existing [issues](https://github.com/orgs/May-Ethereal/repositories)
  and pull requests to avoid duplicates.
- For anything non-trivial, open an issue to discuss the approach before
  investing in a large change.

## Reporting bugs

Open an issue using the **Bug report** template. Include:

- What you expected vs. what happened
- Exact reproduction steps
- Version / commit, OS, and relevant environment details
- Logs or stack traces (redact secrets)

## Proposing features

Open an issue using the **Feature request** template. Describe the problem
first, then the proposed solution and any alternatives considered.

## Pull requests

1. **Fork** and create a topic branch: `feat/short-description` or
   `fix/short-description`.
2. Keep changes **focused** — one logical change per PR.
3. Follow the existing code style of the repository you are editing.
4. Add or update **tests** for behavior changes.
5. Update **documentation** affected by your change.
6. Ensure the build, linters, and tests pass locally.
7. Fill out the pull request template completely and link related issues
   (`Closes #123`).

### Commit messages

Use clear, imperative-mood subjects. [Conventional Commits][cc] are preferred:

```
feat(parser): support nested blocks
fix(api): handle empty payloads
docs: clarify setup steps
```

[cc]: https://www.conventionalcommits.org/

### Review

- At least one maintainer approval is required before merge.
- Address review feedback by pushing additional commits; maintainers squash on
  merge unless noted otherwise.
- CI must be green.

## Security issues

**Never** report security vulnerabilities through public issues or pull
requests. Follow the [Security Policy](SECURITY.md).

## License

By contributing, you agree that your contributions are licensed under the same
license as the repository you are contributing to.

# Contributing to Tele-Care Connect

Thank you for your interest in contributing! This document explains how to propose changes to the project. By participating, you agree to follow our [Code of Conduct](./CODE_OF_CONDUCT.md).

## 1. Ways to contribute

You can help in many ways — not only with code:

- **Report a bug** through GitHub Issues using the "Bug report" template.
- **Suggest a feature** through GitHub Issues using the "Feature request" template.
- **Improve documentation** — fix a typo in the README, clarify a section, translate a page.
- **Submit code** — bug fixes, new features, performance improvements.
- **Review pull requests** opened by other contributors.

## 2. Quick start for code contributions

```bash
# 1. Fork the repository on GitHub, then clone your fork:
git clone https://github.com/<your-username>/tele-care-connect.git
cd tele-care-connect

# 2. Create a branch
git checkout -b feature/short-description

# 3. Make your changes and commit using Conventional Commits
git commit -m "feat(frontend): add language switcher"

# 4. Push and open a pull request against the main branch of arman300s/tele-care-connect
git push origin feature/short-description
```

## 3. Branch naming

- `feature/<description>` for new features.
- `fix/<description>` for bug fixes.
- `docs/<description>` for documentation changes.
- `chore/<description>` for tooling, dependencies, configuration.

## 4. Commit messages

We use [Conventional Commits](https://www.conventionalcommits.org/). Examples:

- `feat(frontend): add doctor filter by specialty`
- `fix(backend): correct timezone handling in bookings`
- `docs(readme): clarify installation steps for backend`
- `chore: bump dependencies via Dependabot`

## 5. Pull request checklist

Before requesting a review, please make sure:

- [ ] The branch is up to date with `main`.
- [ ] Your changes build and run locally.
- [ ] You added or updated documentation if user-visible behaviour changed.
- [ ] You added a screenshot for UI changes.
- [ ] You did not add secrets, API keys, or personal data.
- [ ] You agree to the MIT License of the project.

## 6. Review process

- At least one maintainer reviews each PR.
- Reviewers may request changes; please respond to comments within a week.
- Once approved, a maintainer will squash-merge your branch into `main`.

## 7. Reporting security issues

Please **do not** open a public issue for security vulnerabilities. Email the maintainers privately (see `SECURITY.md`). We aim to acknowledge reports within 72 hours.

## 8. Recognition

All accepted contributions are credited in the project history. Thank you for helping make telemedicine more accessible!

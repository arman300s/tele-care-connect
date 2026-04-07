# Contributing to TeleCare Connect

Thank you for your interest in contributing to TeleCare Connect! This project is open source and welcomes contributions from developers, healthcare professionals, designers, translators, and anyone passionate about improving global health access.

---

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Features](#suggesting-features)
  - [Submitting Pull Requests](#submitting-pull-requests)
- [Development Setup](#development-setup)
- [Coding Standards](#coding-standards)
- [Commit Message Guidelines](#commit-message-guidelines)
- [Branching Strategy](#branching-strategy)

---

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). Please read it before contributing.

---

## How Can I Contribute?

### Reporting Bugs

If you find a bug, please open an issue on [GitHub Issues](https://github.com/arman300s/tele-care-connect/issues) and include:

- A clear, descriptive title
- Steps to reproduce the problem
- Expected vs. actual behaviour
- Screenshots or logs (if applicable)
- Your environment (OS, browser, Node version)

### Suggesting Features

Feature requests are welcome! Open an issue with the label `enhancement` and describe:

- The problem you are trying to solve
- Your proposed solution
- Any alternatives you have considered
- How this aligns with the project's goal of improving healthcare access

### Submitting Pull Requests

1. **Fork** the repository and create your branch from `main`.
2. **Follow** the [Development Setup](#development-setup) instructions.
3. **Make your changes** with clear, focused commits.
4. **Write or update tests** relevant to your change.
5. **Ensure all tests pass** before opening a PR.
6. **Open a Pull Request** against the `main` branch with:
   - A clear description of the change and its purpose
   - A reference to the related issue (e.g., `Closes #42`)
   - Screenshots for UI changes

A maintainer will review your PR and may request changes or clarification.

---

## Development Setup

```bash
# 1. Fork and clone the repository
git clone https://github.com/<your-username>/tele-care-connect.git
cd tele-care-connect

# 2. Install dependencies
npm install

# 3. Copy the example environment file
cp .env.example .env
# Edit .env with your local configuration

# 4. Start the development server
npm run dev
```

See [docs/DOCUMENTATION.md](docs/DOCUMENTATION.md) for a full description of configuration options.

---

## Coding Standards

- Use **clear, descriptive variable and function names**.
- Keep functions small and single-purpose.
- Add comments only where the intent is not obvious from the code.
- Follow the existing code style for the file you are editing.
- Do not commit secrets, API keys, or personal data.

---

## Commit Message Guidelines

Use the following format for commit messages:

```
<type>: <short summary>
```

Common types:

| Type       | When to use                               |
|------------|-------------------------------------------|
| `feat`     | A new feature                             |
| `fix`      | A bug fix                                 |
| `docs`     | Documentation changes only                |
| `refactor` | Code change that is not a fix or feature  |
| `test`     | Adding or updating tests                  |
| `chore`    | Maintenance tasks (deps, config, etc.)    |

Example: `feat: add video consultation scheduling`

---

## Branching Strategy

| Branch   | Purpose                                     |
|----------|---------------------------------------------|
| `main`   | Stable, production-ready code               |
| `dev`    | Integration branch for in-progress features |
| `feat/*` | Individual feature branches                 |
| `fix/*`  | Bug fix branches                            |

Always branch off `main` for fixes and `dev` for new features unless instructed otherwise.

---

## Questions?

If you have any questions, feel free to open a [Discussion](https://github.com/arman300s/tele-care-connect/discussions) or reach out to the maintainers via the repository's Issues page.

Thank you for helping make healthcare more accessible! 🌍

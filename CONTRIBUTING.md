# Contributing to CampusExplore

Thank you for contributing to CampusExplore. This document describes the collaboration workflow, branch and commit conventions, and pull request expectations that all contributors are expected to follow.

---

## Table of Contents

1. [Before You Start](#1-before-you-start)
2. [Collaboration Workflow](#2-collaboration-workflow)
3. [Branch Naming Conventions](#3-branch-naming-conventions)
4. [Commit Message Conventions](#4-commit-message-conventions)
5. [Pull Request Guidelines](#5-pull-request-guidelines)
6. [Pull Request Checklist](#6-pull-request-checklist)
7. [Code Review Process](#7-code-review-process)
8. [What Not to Do](#8-what-not-to-do)

---

## 1. Before You Start

- Read the root [`README.md`](./README.md) to understand the project purpose, planned architecture, and current status.
- Work only against a tracked GitHub Issue. If no issue exists for your task, create one and confirm the scope with your team before writing any code.
- Ask questions in the Issue thread or team channel if any requirement is unclear. Do not make assumptions about scope or architecture.

---

## 2. Collaboration Workflow

Follow these steps for every piece of work — features, fixes, documentation updates, and research tasks.

### Step 1 — Review the assigned GitHub Issue

Read the issue title, description, acceptance criteria, and any linked dependencies before starting. Confirm your understanding with the team if anything is ambiguous.

### Step 2 — Synchronize your local `main` branch

Always start from the latest state of `main`.

```bash
git switch main
git pull origin main
```

### Step 3 — Create a feature branch

Create a branch from `main` using the naming conventions in [Section 3](#3-branch-naming-conventions).

```bash
git switch -c feature/short-description
```

### Step 4 — Implement the agreed scope

Work only on what is described in the issue. If you discover that additional work is needed, create a separate issue for it rather than expanding the scope of the current branch.

### Step 5 — Test your changes

Verify your changes against the acceptance criteria. Ensure existing tests continue to pass. Add new tests where applicable.

### Step 6 — Commit with a meaningful message

Follow the commit conventions in [Section 4](#4-commit-message-conventions).

```bash
git status
git add <relevant-files>
git commit -m "feat: describe the change"
```

### Step 7 — Push the feature branch

```bash
git push -u origin feature/short-description
```

### Step 8 — Open a pull request

Open a pull request on GitHub targeting the `main` branch. Write a clear description that explains what changed and how it was tested.

### Step 9 — Link the related Issue

Reference the issue in the pull request description so that it closes automatically when the pull request is merged:

```
Closes #<issue-number>
```

### Step 10 — Address review feedback and merge

Respond to all reviewer comments. Once approved, merge according to the repository's branch protection rules. Do not merge your own pull request without a review unless explicitly authorized.

---

## 3. Branch Naming Conventions

Use one of the following prefixes followed by a short, hyphenated description in lowercase:

| Prefix | When to Use |
|---|---|
| `feature/` | Adding new functionality |
| `fix/` | Correcting a bug or broken behavior |
| `docs/` | Documentation-only changes |
| `test/` | Adding or updating tests without changing application logic |
| `refactor/` | Code restructuring without behavior change |

**Examples:**

```
feature/place-listing-api
feature/ai-chatbot-ui
fix/review-submission-validation
docs/update-development-setup
test/recommendation-service-unit-tests
refactor/venue-service-cleanup
```

Keep branch names short and descriptive. Avoid generic names such as `my-branch` or `changes`.

---

## 4. Commit Message Conventions

Follow the [Conventional Commits](https://www.conventionalcommits.org/) format:

```
<type>: <short imperative description>
```

| Type | When to Use |
|---|---|
| `feat` | A new feature or capability |
| `fix` | A bug fix |
| `docs` | Documentation changes only |
| `test` | Adding or updating tests |
| `refactor` | Code change that is neither a bug fix nor a new feature |
| `chore` | Maintenance tasks, dependency updates, tooling changes |
| `style` | Formatting changes that do not affect logic |

**Examples:**

```
feat: add place listing API endpoint
feat: implement category filter on venue search
fix: validate review submission form inputs
docs: update development setup instructions
test: add unit tests for recommendation service
refactor: extract venue scoring into separate helper
chore: add .editorconfig and .gitignore
```

Write commit messages in the **imperative mood** ("add", not "added" or "adding"). Keep the subject line under 72 characters. Add a blank line and a longer explanation in the commit body if the change requires additional context.

---

## 5. Pull Request Guidelines

- **One pull request per issue.** Do not combine multiple unrelated issues in a single pull request.
- **Write a clear description.** Explain what was changed, why, and how it was tested.
- **Reference the issue.** Include `Closes #<issue-number>` in the description.
- **Keep changes minimal and focused.** Do not include reformatting, unrelated refactoring, or experimental code in a functional pull request.
- **Resolve merge conflicts yourself.** Rebase or merge `main` into your branch and resolve conflicts before requesting a review.
- **Do not push unfinished changes directly to `main`.** All work must go through a feature branch and a reviewed pull request.

---

## 6. Pull Request Checklist

Before marking a pull request as ready for review, confirm each of the following:

- [ ] The pull request addresses exactly one GitHub Issue.
- [ ] The pull request is linked to the issue with `Closes #<issue-number>`.
- [ ] The branch is up to date with `main` and all conflicts are resolved.
- [ ] All existing tests pass.
- [ ] New tests have been added where appropriate.
- [ ] The pull request description explains what changed and how it was tested.
- [ ] No secrets, credentials, API keys, or environment-specific values are included.
- [ ] No unrelated files, formatting changes, or debug code are included.
- [ ] Relevant documentation has been updated to reflect the change.

---

## 7. Code Review Process

- Reviewers will check for correctness, readability, security, test coverage, and integration compatibility.
- Authors must respond to all review comments before the pull request can be merged.
- Mark a comment as resolved only after the concern has been addressed — not simply acknowledged.
- Reviewers should provide constructive feedback. Nit-level suggestions should be clearly labelled as optional.
- Merge permissions and required approvals are governed by the repository's branch protection settings.

---

## 8. What Not to Do

- **Do not push directly to `main`.** All changes must go through a reviewed pull request.
- **Do not commit secrets.** See the [Configuration and Secrets](./README.md#14-configuration-and-secrets) section of the main README.
- **Do not start work without a GitHub Issue.** Untracked changes are difficult to review and may be discarded.
- **Do not expand scope mid-branch.** If you discover additional work is needed, open a new issue.
- **Do not leave debug code, commented-out blocks, or placeholder TODOs** in code submitted for review unless they correspond to a tracked issue.

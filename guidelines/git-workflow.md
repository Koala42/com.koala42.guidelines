# Git Workflow Guidelines

This document defines the workflow for working with branches and commits in our projects. The goal is to improve history readability and facilitate collaboration.

## 1. Branches

### 1.1 Branch Naming Convention

Use prefixes based on the type of work:

- `feature/` – new features
- `bugfix/` – bug fixes
- `hotfix/` – urgent fixes
- `chore/` – technical debt, refactoring, maintenance

Branch names must include the task identifier (Jira ID):

```
feature/PROJ-123-login-form
bugfix/PROJ-456-fix-navigation
hotfix/PROJ-789-critical-security-patch
```

### 1.2 Multiple Branches per Task

Multiple branches for a single task are allowed when:

- Work is logically separated (e.g., backend / frontend)
- Work is extesive and needs to be separated into multiple PRs to satisfy optimal PR size
- Work requires experimental branches for different approaches

Each branch must have a clear purpose and be tracable to the Jira task.

## 2. Commit Structure

### 2.1 Basic Rules

- **One commit = one logical change**
- Separate formatting changes from functional changes
- Every commit should be traceable to a Jira task

```
feat: add login validation
Relates: https://koala42.atlassian.net/browse/PROJ-123
```

### 2.2 Commit Message Format

Each project must choose **one consistent style** and stick to it.

#### Option A: Conventional Commits

> 🔗 [https://www.conventionalcommits.org/en/v1.0.0/](https://www.conventionalcommits.org/en/v1.0.0/)

**Format:**

```
feat: add login validation
fix!: handle null token
refactor(auth): simplify auth flow
chore(deps): update dependencies
```

**Structure:**

- Type: `feat`, `fix`, `refactor`, `chore`, `docs`, `test`, etc.
- Scope (optional): component or module affected
- Description: brief summary of the change
- Body (optional): detailed explanation
- Footer (optional): breaking changes, issue references

#### Option B: Gitmoji

> 🔗 [Gitmoji Extension](https://marketplace.visualstudio.com/items?itemName=harastaivan.gitmoji-linked-commits)

**Format:**

```
✨ add login validation
🐛 handle null token
♻️ simplify auth flow
📝 update documentation
```

**Common emojis:**

- ✨ New feature
- 🐛 Bug fix
- ♻️ Refactoring
- 📝 Documentation
- 🎨 Code formatting
- ⚡ Performance improvement
- 🔒 Security fix

## 3. CI Pipeline

Every PR must pass automated checks before merge.

### Required Checks

✅ **Formatting check** – code follows style guidelines
✅ **Type check** – `tsc` or equivalent (TypeScript/typed languages)
✅ **Build** – project compiles successfully
✅ **Lint** – no linting errors
✅ **Tests** – all tests pass (if tests exist)
✅ **Dependency audit** – security vulnerabilities check (can skip if no fix available)

### Important

🚫 **PRs with failing pipeline cannot be merged.**



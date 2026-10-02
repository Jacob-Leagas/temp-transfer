# Git Workflow Guide

version: 1.0

## Purpose

This guide defines how commits, branches, and pull requests are structured. It keeps history consistent and reviewable across projects.

## Branch Naming

Use this format:

```
<type>/<short-description>
```

Examples:

```
feature/add-user-auth
fix/backup-permissions
refactor/extract-backup-functions
docs/update-readme
```

Types: `feature`, `fix`, `refactor`, `docs`, `chore`, `test`.

## Commit Messages

Use this format:

```
<type>: <short summary>
```

Examples:

```
feat: add user authentication
fix: correct backup permission check
refactor: extract database backup into function
docs: update deployment readme
```

Rules:

- Keep the summary under 72 characters.
- Use imperative mood (add, fix, refactor, not added, fixed, refactored).
- Do not reference issue numbers unless the project uses them.
- One logical change per commit.

## Breaking Up Changes

- Commit related changes together.
- Do not mix refactors with feature work in the same commit.
- Do not commit generated files, secrets, or local config.
- Commit early and often, but only when the change is complete enough to stand alone.

## Pull Requests

Title format:

```
<type>: <short summary>
```

Description structure:

- What changed.
- Why it changed.
- How to test it.
- Any follow-up work or known limitations.

## When to Commit vs Ask First

- Commit freely for small, scoped changes.
- Ask before committing when the change is large, destructive, or affects shared infrastructure.
- Ask before pushing, merging, or running migrations.

## Rules

- Follow the tone rules in DOCUMENTATION_TONE_GUIDE.md.
- Do not rewrite history on shared branches.
- Keep the working tree clean before switching tasks.
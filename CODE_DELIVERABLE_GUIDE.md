# Code Deliverable Guide

version: 1.1

## Purpose

This guide defines how to produce a code deliverable when asked. A code deliverable is a compact log file that records what changed, why it changed, and what you learned. It is not a full summary. It is a reference we can return to without re-asking the AI.

## Trigger

Produce a deliverable only when explicitly asked. Never produce one automatically after every change. The user will ask for one when they want it.

## Workflow

When asked to produce a code deliverable, ask clarifying questions first. At minimum, ask:

- Which project folder?
- What changed? (update, refactor, feature added, feature removed)
- What version number?
- Any specific files or areas to focus on?

Use the answers to place the file and fill in the details. If the user does not answer, infer reasonable defaults and state them in the file.

## File Naming

Use this format:

```
deliverable_notes_YYYY-MM-DD_vX.Y.md
```

Example:

```
deliverable_notes_2026-12-08_v1.0.md
```

- The date is the day the log was created.
- The version is the project or feature version the user specifies.

The user may refer to this file by different names. Map those terms to the standard filename:

| User says | File produced |
| --- | --- |
| "dnmd" / "dnmd file" | `deliverable_notes_...` |
| "deliverable notes" | `deliverable_notes_...` |
| "notes file" | `deliverable_notes_...` |
| "code deliverable" / "CD" | `deliverable_notes_...` |

## Location

Create a `logs/` folder inside the project being worked on, then place the file there:

```
my-project/
  logs/
    deliverable_notes_2026-12-08_v1.0.md
```

This keeps the log history with the project. It travels with the code and gets removed when the devkit is stripped for production.

## Length Limit

Hard limit of 60 lines per file. Do not exceed this. Keep sections short and purposeful.

## Format

Use this structure:

```markdown
# Deliverable Notes: [Title]

Date: YYYY-MM-DD
Version: vX.Y
Project: [Project Name]

## Change Type
[update, refactor, feature added, feature removed]

## What Changed
- `path/to/file` (lines X-Y): Description of the change.
- `path/to/file` (lines X-Y): Description of the change.

## Reasoning
- One or two sentences explaining why this approach was chosen.
- State the tradeoff or constraint that drove the decision.

## Use Cases
- When to use this code or feature.
- What problem it solves.

## Key Concepts
- One or two learning notes about the underlying concept.
- Keep this short. It is for learning, not documentation.
```

## Rules

- Reference file paths and line ranges for every change.
- Keep reasoning to one or two sentences per point.
- Include one or two use cases.
- Include one or two key concept notes.
- Do not include code blocks unless they are essential.
- Do not include future facing notes.
- Do not speculate about behavior.
- Follow the tone rules in DOCUMENTATION_TONE_GUIDE.md.

## Worked Example

Based on the Gitea backup script:

```markdown
# Deliverable Notes: Backup Script Refactor

Date: 2026-12-08
Version: v1.0
Project: Jbox - Gitea

## Change Type
Refactor

## What Changed
- `backups/backup.sh` (lines 45-61): Added backup type determination logic.
- `backups/backup.sh` (lines 66-87): Extracted database backup into `backup_database()`.
- `backups/backup.sh` (lines 92-128): Extracted data backup into `backup_data()`.

## Reasoning
- Split the monolithic main flow into functions so each backup step can fail independently.
- Used `set -euo pipefail` to fail fast on errors.

## Use Cases
- Run `./backup.sh --db-only` to back up PostgreSQL without touching Gitea data.
- Run `./backup.sh --data-only` to back up repositories and config only.

## Key Concepts
- `set -euo pipefail` makes scripts exit on unset variables and failed pipes.
- Function extraction keeps each responsibility testable and readable.
```

## Reference

The AI should reference this guide when asked to produce a code deliverable. The LLM_REFERENCE_GUIDE.md points to this file.
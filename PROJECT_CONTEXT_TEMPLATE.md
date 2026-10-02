# Project Context Template

version: 1.0

## Purpose

This template defines the project context an AI agent needs before working on a project. Copy this file into a project, fill it out once, and keep it updated as the project evolves. The agent reads this to understand the project without reverse-engineering it.

## How to Use

- Copy this file into the project root as `PROJECT_CONTEXT.md`.
- Fill out every section. Leave unknown sections blank rather than guessing.
- Update the file when the project changes in a way that affects the answers.
- Keep it under 60 lines.

## Template

```markdown
# Project Context: [Project Name]

version: 1.0

## Overview
- What this project does:
- Who uses it:
- Current state (active, maintenance, prototype):

## Tech Stack
- Languages and versions:
- Frameworks and libraries:
- Databases and services:
- Build and package tools:

## Architecture
- High level structure:
- Key directories and their purpose:
- Entry points:
- Data flow (if relevant):

## Local Development
- How to install dependencies:
- How to run locally:
- How to run tests:
- How to build for production:

## Constraints and Decisions
- Known limitations:
- Decisions that affect maintainability:
- Things to avoid changing without discussion:

## Deployment
- Target environments:
- How deployment works:
- Environment variables or config needed:
```

## Rules

- Keep answers short and factual.
- Do not include secrets, API keys, or credentials.
- Reference other docs instead of duplicating them.
- Update the version number when the context changes.
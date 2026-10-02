# Code Review Guide

version: 1.0

## Purpose

This guide defines how to review code. It applies to reviewing your own changes, reviewing another developer's changes, or reviewing AI generated code. Reviews should be consistent, focused, and useful.

## Review Order

Check in this order:

1. Correctness. Does the code do what it claims?
2. Security. Does it expose secrets, allow injection, or mishandle input?
3. Scope. Does it do more than the task requires?
4. Readability. Can a future reader understand it without the author?
5. Tests. Do tests cover the behavior, not just the happy path?

## Prioritizing Findings

- Blocking: breaks functionality, introduces a security risk, or contradicts the project context.
- Non-blocking: style, naming, or structure that can be improved later.
- Do not block on personal preference.

## Phrasing Feedback

- State the problem, not the person.
- Reference the specific line or behavior.
- Suggest a fix or ask a question, not both at once.
- Keep feedback short and actionable.

## What to Ignore

- Style nits that do not affect readability.
- Formatting that matches the project's existing style.
- Code that works and is clear, even if you would write it differently.

## Per-Language Checklist

### Python

- Type hints on function signatures.
- Docstrings on public functions and classes.
- No unused imports or variables.
- Exceptions are caught and handled, not swallowed.

### JavaScript

- const over let unless reassignment is needed.
- Async logic is readable and error paths are handled.
- No unnecessary abstractions or sprawling utility files.

### CSS and HTML

- Markup is semantic and accessible.
- No inline styles unless necessary.
- CSS is organized with clear section comments.

### Java

- Meaningful class and method names.
- Javadoc on public APIs.
- Methods are small and focused.

## Rules

- Follow the tone rules in DOCUMENTATION_TONE_GUIDE.md.
- Do not speculate about behavior. State what the code does.
- Do not invent issues. If something is uncertain, ask.
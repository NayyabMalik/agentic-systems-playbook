---
name: python
description: Use for Python implementation, debugging, project structure, testing, and dependency management.
---

# Python Skill Reference

## Scope

Use this context for Python questions involving implementation, debugging, project structure, testing, or dependency management. Prefer the conventions and tools already present in the user's project.

## Core Practices

- Favor readable, small functions with clear names and explicit inputs and outputs.
- Use the standard library when it is sufficient; add dependencies only when they provide meaningful value.
- Use `pathlib` for filesystem paths and context managers for files and other managed resources.
- Add type hints where they clarify interfaces. Keep types aligned with the project's Python version.
- Handle expected errors deliberately. Avoid broad exception handling that hides failures.
- Keep configuration outside source code. Load secrets from environment variables or an approved secret manager; never print them.
- Use a virtual environment and record project dependencies using the project's existing tool, such as `requirements.txt`, `pyproject.toml`, or a lockfile.
- Write focused tests for behavior and edge cases. Do not claim tests passed unless they were run.

## When Debugging

1. Reproduce the issue and capture the full traceback.
2. Identify the failing function and the smallest input that demonstrates the problem.
3. Fix the underlying behavior rather than suppressing the error.
4. Run the narrowest relevant test, then any required broader checks.

## Compatibility

Do not assume a Python version, operating system, framework, or package manager. Check project configuration first. If it is unspecified, state the assumption before relying on version-specific features.
# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Status

This repository is currently uninitialized beyond `README.md`. There is no source code, build system, dependency manifest, or test suite yet. The project's stated purpose (from `README.md`) is a **Conference Per Diem Meal Tracker**.

When asked to implement features, first establish the stack (language, framework, package manager) with the user before scaffolding — no conventions have been set.

## Git Workflow

- `main` is the default branch.
- Active development branch for Claude-authored work: `claude/add-claude-documentation-9G0jy`. Commit and push there unless the user specifies otherwise.
- Push with `git push -u origin <branch>`. Do not open a PR unless explicitly requested.

## Notes for Future Sessions

Once a stack is chosen and code is added, update this file with:
- Build / lint / test commands (including how to run a single test).
- The domain model for per-diem tracking (trips, days, meals, rates) — this is the core of the app and will likely span multiple files.
- Any external integrations (GSA per-diem rates, expense systems) once added.

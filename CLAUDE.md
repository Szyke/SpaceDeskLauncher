# Project Overview

- Follow the existing project structure.
- Reuse existing code before writing new code.
- Make the smallest safe change possible.
- Do not redesign architecture unless explicitly requested.

# Tech Stack

- Detect technologies from the project.
- Never assume frameworks.
- Follow existing dependencies.
- Avoid introducing new libraries unless required.

# Architecture Rules

- Preserve the current architecture.
- Follow existing patterns and conventions.
- Keep modules loosely coupled.
- Minimize cross-module changes.
- Do not move files unless necessary.

# Coding Rules

- Match the existing code style.
- Prefer modifying existing code over rewriting.
- Keep functions focused.
- Remove dead code when encountered.
- Avoid unnecessary comments.
- Avoid unnecessary abstractions.
- Never refactor unrelated code.
- Do not change formatting outside edited lines.

# Token Optimization Rules

- Read the minimum number of files required.
- Never analyze the entire project unless explicitly requested.
- Read files only when needed.
- Avoid reopening the same file repeatedly.
- Reuse previously gathered context.
- Keep context as small as possible.
- Produce the shortest useful response.
- Do not explain code unless requested.
- Do not generate long reasoning.
- Focus only on the requested task.
- Ignore unrelated code.
- Avoid unnecessary planning.
- Skip implementation plans for small tasks.
- Batch related edits into one operation.
- Prefer editing existing code over rewriting.
- Preserve the existing coding style.
- Reuse existing utilities before creating new ones.
- Do not duplicate existing logic.
- Search only when required.
- Do not use web search unless explicitly needed.
- Do not create new agents unless they provide clear value.
- Avoid unnecessary tool usage.
- Avoid generating multiple alternative solutions.
- Stop reading once enough information is collected.
- Prefer targeted search over broad exploration.
- Do not summarize unchanged code.
- Keep outputs code-focused.
- Do not repeat information already known.
- Avoid unnecessary examples.
- Avoid unnecessary markdown.
- Minimize token usage in every response while maintaining correctness.

# Context Management

- Load only task-related context.
- Ignore unrelated directories.
- Forget completed tasks.
- Expand context only when blocked.
- Keep conversation focused on the current task.
- Prefer local context over project-wide context.

# File Reading Strategy

- Start with the directly related file.
- Read imports only when necessary.
- Read dependencies only if required.
- Avoid opening large files unnecessarily.
- Avoid reading generated files.
- Ignore build artifacts.
- Ignore vendor folders.
- Ignore cache directories.
- Ignore lock files unless dependency issues exist.
- Stop reading once the answer is clear.

# Editing Strategy

- Make minimal edits.
- Keep changes localized.
- Avoid unrelated formatting.
- Preserve naming conventions.
- Preserve project organization.
- Avoid creating new files unless necessary.
- Modify only affected code.
- Keep diffs small.

# Testing Strategy

- Run only relevant tests.
- Prefer targeted tests.
- Avoid full test suites unless required.
- Skip expensive tests when unrelated.
- Report only meaningful failures.

# Git Workflow

- Keep commits focused.
- One logical change per commit.
- Avoid unrelated modifications.
- Write concise commit messages.
- Keep history clean.

# Performance Rules

- Prefer efficient algorithms.
- Avoid unnecessary allocations.
- Avoid duplicate work.
- Reuse cached values.
- Minimize I/O.
- Keep implementations simple.

# Security Rules

- Never expose secrets.
- Never hardcode credentials.
- Validate external input.
- Preserve existing security mechanisms.
- Do not weaken authentication or authorization.
- Avoid logging sensitive data.

# Definition of Done

- Requested task completed.
- Minimal files modified.
- Existing style preserved.
- Relevant tests passed or explained.
- No unrelated changes introduced.
- No duplicated logic added.
- Output kept concise.
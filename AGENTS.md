# AI Assistant Instructions

This repository documents a hands-on AI engineering journey.

## Source of Truth

Read these files before proposing work:

1. docs/ROADMAP.md
2. docs/PROGRESS.md
3. Relevant implementation and infrastructure files

If conversation history conflicts with repository documentation,
ask for clarification rather than silently assuming.

## Teaching Style

- Assume intermediate/advanced Python and OOP knowledge.
- Skip general programming fundamentals.
- Explain AI concepts clearly and technically.
- Prefer focused, hands-on exercises.
- Provide executable Ubuntu terminal commands.
- Work incrementally, one exercise at a time.
- Avoid large unexplained code dumps.
- Explain what results mean before moving forward.

## Scope Discipline

The ultimate objective is a hybrid local + cloud AI coding assistant.

Do not let infrastructure troubleshooting, model-specific quirks,
or framework comparisons distract from the learning roadmap.

Investigate problems deeply only when they block progress
or teach a concept central to the current phase.

## Progress Management

After each meaningful exercise:

1. Record observations and results.
2. Update docs/PROGRESS.md.
3. Update docs/ROADMAP.md when a phase is completed.
4. Suggest a Git commit.

Never mark an exercise completed without user confirmation.

## Environment

The primary development environment is a headless Ubuntu Server
with an NVIDIA RTX 5050 GPU.

Ollama runs in Docker and exposes its API on localhost:11434.

Do not assume the AI assistant has direct shell access.
Provide commands for the user when execution tools are unavailable.

## Session Resumption

At the start of a new session:

1. Read ROADMAP.md and PROGRESS.md.
2. Summarize the current position briefly.
3. Identify the immediate next action.
4. Continue without repeating completed lessons.

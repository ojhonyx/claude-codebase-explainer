# Claude Codebase Explainer

A Claude Code skill that instantly explains any codebase.

## Usage

In any project where this skill is installed, type:

```
/explain
```

Claude will inspect the repository and produce a structured overview.

## Features

- Automatically detects the stack
- Finds the application entry point
- Maps important folders
- Identifies authentication, database, API, payment, queue, and storage providers
- Lists important files
- Generates a concise developer guide

## Output

```markdown
# Project Overview
# Folder Overview
# Authentication Flow
# API Overview
# Important Files
# Developer Guide
```

See `.claude/skills/codebase-explainer/` for the skill definition and `examples/` for sample outputs.

## Compatibility

The skill is built for **Claude Code** first, but the same structure can be adapted to other agents and editors:

- Claude Code
- Antigravity
- Codex App
- Codex CLI
- Cursor
- Factory Droid
- Gemini CLI
- GitHub Copilot CLI
- Kimi Code
- OpenCode
- Pi

## Register on Claude Code

1. Copy `.claude/skills/codebase-explainer/` into your project at `.claude/skills/`.
2. Open Claude Code inside the project.
3. Type `/explain` to trigger the skill.

Plugin page: https://claude.com/plugins/Explainer

## Installation

Copy `.claude/skills/codebase-explainer/` into `.claude/skills/` in your target repository.

## License

MIT

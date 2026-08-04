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

## Installation

Copy `.claude/skills/codebase-explainer/` into `.claude/skills/` in your target repository.

## License

MIT

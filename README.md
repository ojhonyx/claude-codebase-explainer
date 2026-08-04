# Claude Codebase Explainer

A Claude Code skill that explains the architecture, stack, and important flows of any codebase in seconds.

## Quickstart

Install the skill in any project and type:

```
/explain
```

Claude will inspect the repository and respond with a structured overview.

## What it does

- Detects the technology stack by reading manifests and configuration files.
- Finds the application entry point.
- Maps the most important folders.
- Identifies authentication, database, payment, queue, and storage providers.
- Lists API routes and important files.
- Generates a concise developer guide.

## Output

The skill always returns the same sections in the same order:

```markdown
# Project Overview
# Folder Overview
# Authentication Flow
# API Overview
# Important Files
# Developer Guide
```

## Plugin registration

For Claude Code:

1. Copy `skills/codebase-explainer/` into your project at `.claude/skills/`.
2. Open Claude Code inside the project.
3. Type `/explain` to trigger the skill.

Plugin manifest: `.claude-plugin/plugin.json`

Plugin page: https://claude.com/plugins/Explainer

## Other agents

This skill is written for **Claude Code** using the `.claude/skills/` format. It is not automatically compatible with other assistants or editors. To port it to another platform you would need to rewrite the manifest and instructions to match that platform's own skill/plugin format.

## Repository structure

```
claude-codebase-explainer/
├── .claude-plugin/
│   └── plugin.json
├── skills/
│   └── codebase-explainer/
│       └── SKILL.md
├── README.md
└── LICENSE
```

## License

MIT

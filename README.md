# Claude Codebase Explainer

A focused Claude Code skill that explains the architecture, stack, and important flows of any codebase in seconds.

![Demo](images/demo.gif)

Replace the file above with your own demo GIF before submitting to the Claude plugin store.

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

## Future compatibility

The skill is built for **Claude Code** first. The same structure can be adapted for other agents and editors such as Antigravity, Codex App, Codex CLI, Cursor, Factory Droid, Gemini CLI, GitHub Copilot CLI, Kimi Code, OpenCode, and Pi.

## Examples

See the `examples/` directory for sample outputs:

- `examples/nextjs.md`
- `examples/fastify.md`
- `examples/laravel.md`
- `examples/react.md`

## Repository structure

```
claude-codebase-explainer/
├── .claude-plugin/
│   └── plugin.json
├── skills/
│   └── codebase-explainer/
│       ├── SKILL.md
│       └── examples.md
├── examples/
│   ├── nextjs.md
│   ├── fastify.md
│   ├── laravel.md
│   └── react.md
├── images/
├── README.md
└── LICENSE
```

## License

MIT

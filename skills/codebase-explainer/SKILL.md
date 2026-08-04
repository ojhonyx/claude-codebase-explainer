# codebase-explainer

## Name

Codebase Explainer

## Description

Explains the architecture, stack, structure, and important flows of any codebase in seconds when the user types `/explain`. It inspects the repository before answering, never hallucinates, and produces a deterministic, senior-engineer-quality overview.

## Triggers

- `/explain`
- `explain this codebase`
- `what does this project do?`
- `give me an overview of this repo`

## Capabilities

- Discovers the technology stack by reading configuration and manifest files.
- Identifies the entry point of the application.
- Maps the folder structure and highlights the most relevant directories.
- Detects authentication strategy, login flow, and protected-route middleware.
- Identifies the database, ORM, schema, and storage systems.
- Lists API routes and major HTTP/background-job entry points.
- Finds middlewares, services, and shared utilities.
- Detects payment, queue, and background-job providers.
- Surfaces environment variables and important configuration files.
- Generates a concise but actionable project summary.

## Instructions

1. Before producing any answer, inspect the repository:
   - Read `package.json`, `pyproject.toml`, `composer.json`, `Cargo.toml`, `go.mod`, `Gemfile`, `pom.xml`, or equivalent root manifests.
   - Read framework-specific config files (e.g., `next.config.*`, `vite.config.*`, `tsconfig.*`, `tailwind.config.*`, `docker-compose.*`, `.env.example`).
   - Read README files and top-level documentation.
2. Map the directory tree up to a reasonable depth. Identify the entry point (e.g., `src/server.ts`, `app/layout.tsx`, `main.py`, `index.php`, `cmd/app/main.go`).
3. Categorize findings into:
   - Framework
   - Backend
   - Database
   - Authentication
   - Payments
   - Queue / Background jobs
   - Storage
   - Deployment
   - Folder overview
   - Important files
4. If any category is missing, explicitly write `Not found` or `Not configured` instead of guessing.
5. Avoid long prose. Use short, grouped bullet points and tables where appropriate.
6. Do not invent files, routes, or technologies. Every claim must be supported by a file read or pattern match.
7. Optimize for large repositories by sampling only the top-level structure, key manifests, and a handful of representative files. Avoid reading every source file.

## Workflow

1. Parse root manifests and configuration files.
2. Build a shallow tree of the repository (depth 3 or 4).
3. Find the application entry point.
4. Search for authentication, database, payment, queue, and storage keywords.
5. Map folder roles based on naming conventions and file contents.
6. Compile the final report in the exact output format below.

## Rules

- Always inspect before explaining. No answer is produced from memory.
- Use deterministic language. State what is present, not what might be.
- Keep context usage low. Do not dump full file contents unless necessary.
- If the repo is empty or has no recognizable structure, say so and stop.
- Use `Unknown` only when a category cannot be determined after reasonable inspection.
- Preserve the order of sections in the output format.
- Avoid emojis unless the user explicitly requested them.

## Edge cases

- Empty repository: respond with `No files detected. Add source code and run /explain again.`
- Monorepo: produce a separate mini-section for each workspace/package and a unified summary.
- No framework: list language/runtime and plain file structure.
- No backend (static site): report `No backend detected` and describe the build/deployment setup.
- Missing important files: state `Not found in expected locations` for the affected category.
- Multiple auth or payment providers: list all detected providers.

## Output format

```markdown
# Project Overview

| Area           | Value                     |
| ---------------| --------------------------|
| Framework      | <value or Not found>      |
| Backend        | <value or Not found>      |
| Database       | <value or Not found>      |
| Authentication | <value or Not found>      |
| Payments       | <value or Not found>      |
| Queue          | <value or Not found>      |
| Storage        | <value or Not found>      |
| Deployment     | <value or Not found>      |

# Folder Overview

<root>
├── <dir>/         <- <role>
├── <dir>/         <- <role>
└── <file>         <- <role>

# Authentication Flow

1. <step>
2. <step>
3. <step>

# API Overview

| Method | Route / Handler | Purpose |
|--------|-----------------|---------|
| ...    | ...             | ...     |

# Important Files

- `<file>` - <one-line purpose>

# Developer Guide

1. <step>
2. <step>
3. <step>
```



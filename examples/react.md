# Example output: React project

```markdown
# Project Overview

| Area           | Value              |
| ---------------| -------------------|
| Framework      | React 18           |
| Backend        | Not detected       |
| Database       | Not detected       |
| Authentication | Not detected       |
| Payments       | Not detected       |
| Queue          | Not detected       |
| Storage        | Not detected       |
| Deployment     | Vite build         |

# Folder Overview

src/
├── components/    <- React components
├── pages/         <- Page components
├── hooks/         <- Custom hooks
├── context/       <- React context
├── services/      <- API clients
└── main.tsx       <- Entry point

public/            <- Static assets
index.html         <- HTML entry

# Authentication Flow

Not detected in this client-side project.

# API Overview

Client calls assumed external endpoints from `src/services/`:

| File             | Purpose            |
|------------------|--------------------|
| `src/services/api.ts` | Generic API client |
| `src/services/auth.ts` | Auth endpoints     |

# Important Files

- `src/main.tsx`
- `src/App.tsx`
- `src/services/api.ts`
- `vite.config.ts`

# Developer Guide

1. Run `npm install`.
2. Start dev server with `npm run dev`.
3. Add components in `src/components/`.
4. Add pages in `src/pages/`.
```

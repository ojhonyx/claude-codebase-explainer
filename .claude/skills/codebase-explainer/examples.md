# Examples

## Example 1 — Next.js + Fastify monorepo

### User input

```
/explain
```

### Skill output

```markdown
# Project Overview

| Area           | Value              |
| ---------------| -------------------|
| Framework      | Next.js 15         |
| Backend        | Fastify            |
| Database       | Prisma + PostgreSQL|
| Authentication | Better Auth        |
| Payments       | Stripe             |
| Queue          | Inngest            |
| Storage        | S3                 |
| Deployment     | Vercel             |

# Folder Overview

```
app/
├── (routes)/       <- Next.js page routes and layouts
├── components/     <- Shared React components
├── api/            <- Route handlers
└── layout.tsx      <- Root layout

backend/
├── src/
│   ├── server.ts   <- Fastify entry point
│   ├── routes/     <- API routes
│   ├── services/   <- Business logic
│   ├── database/   <- Prisma client and migrations
│   └── middleware/ <- Auth and validation middleware
├── prisma/
│   └── schema.prisma
└── .env.example

packages/
└── shared/         <- Shared types and utilities
```

# Authentication Flow

1. Middleware validates the session/cookie on protected requests.
2. `POST /api/auth/login` or `POST /api/auth/register` hits Better Auth.
3. JWT is issued and stored in a secure, HTTP-only cookie.
4. Protected routes read the cookie/session via middleware.

# API Overview

| Method | Route            | Purpose                   |
|--------|------------------|---------------------------|
| POST   | /api/login       | Authenticate a user       |
| POST   | /api/register    | Register a new user       |
| GET    | /api/profile     | Fetch current user        |
| POST   | /api/checkout    | Create a payment session  |
| POST   | /api/webhook     | Receive Stripe/Inngest events |

# Important Files

- `app/layout.tsx` — Root Next.js layout and providers.
- `backend/src/server.ts` — Fastify server bootstrap.
- `backend/src/auth.ts` — Authentication configuration.
- `backend/src/middleware.ts` — Request middleware.
- `backend/prisma/schema.prisma` — Database models.
- `backend/src/routes.ts` — Route registration.
- `backend/src/env.ts` — Environment validation.

# Developer Guide

1. Add your database URL and secrets to `backend/.env`.
2. Run `prisma migrate dev` in the `backend` workspace.
3. Add new business logic inside `backend/src/services/` and expose it via `backend/src/routes/`.
4. For new frontend pages, add route files under `app/`.
```

### Key observations

- The skill did not invent routes. They were discovered from `backend/src/routes/*.ts` and `app/api/**/route.ts`.
- `Better Auth` was detected from `package.json` and an `auth.ts` file.
- `Inngest` was detected from imports in `server.ts` and `routes/webhooks.ts`.
- `Deployment` was inferred from `vercel.json` and `package.json` scripts.

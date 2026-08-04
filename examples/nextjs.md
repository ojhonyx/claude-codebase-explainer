# Example output: Next.js project

```markdown
# Project Overview

| Area           | Value              |
| ---------------| -------------------|
| Framework      | Next.js 15         |
| Backend        | Next.js API routes |
| Database       | Prisma + PostgreSQL|
| Authentication | Better Auth        |
| Payments       | Stripe             |
| Queue          | Inngest            |
| Storage        | S3                 |
| Deployment     | Vercel             |

# Folder Overview

app/
├── (routes)/       <- Page routes
├── api/            <- API routes
├── components/     <- React components
└── layout.tsx      <- Root layout

lib/
└── db.ts           <- Prisma client

prisma/
└── schema.prisma   <- Database schema

# Authentication Flow

1. Middleware validates session/cookie.
2. `POST /api/auth/login` or `POST /api/auth/register`.
3. JWT stored in HTTP-only cookie.
4. Protected routes check cookie.

# API Overview

| Method | Route            | Purpose            |
|--------|------------------|--------------------|
| POST   | /api/login       | Login              |
| POST   | /api/register    | Register           |
| GET    | /api/profile     | User profile       |
| POST   | /api/checkout    | Stripe checkout    |

# Important Files

- `app/layout.tsx`
- `app/api/auth/[...all]/route.ts`
- `lib/db.ts`
- `prisma/schema.prisma`
- `.env.local`

# Developer Guide

1. Configure `.env.local`.
2. Run `prisma migrate dev`.
3. Add routes in `app/api/`.
4. Add pages in `app/`.
```

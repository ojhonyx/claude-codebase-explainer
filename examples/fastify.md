# Example output: Fastify project

```markdown
# Project Overview

| Area           | Value              |
| ---------------| -------------------|
| Framework      | Fastify            |
| Backend        | Fastify            |
| Database       | Prisma + PostgreSQL|
| Authentication | Better Auth        |
| Payments       | Stripe             |
| Queue          | Inngest            |
| Storage        | S3                 |
| Deployment     | Docker             |

# Folder Overview

src/
├── server.ts       <- Entry point
├── routes/         <- API routes
├── services/       <- Business logic
├── middleware/     <- Auth and validation
└── database/       <- Prisma client

prisma/
└── schema.prisma   <- Database models

# Authentication Flow

1. Request passes through auth middleware.
2. `POST /login` or `POST /register` hits auth routes.
3. JWT is issued and stored in cookie.
4. Protected routes use middleware to verify JWT.

# API Overview

| Method | Route            | Purpose            |
|--------|------------------|--------------------|
| POST   | /login           | Login              |
| POST   | /register        | Register           |
| GET    | /profile         | User profile       |
| POST   | /checkout        | Stripe checkout    |
| POST   | /webhook         | Stripe/Inngest     |

# Important Files

- `src/server.ts`
- `src/auth.ts`
- `src/middleware.ts`
- `src/routes.ts`
- `prisma/schema.prisma`
- `src/env.ts`

# Developer Guide

1. Configure `.env`.
2. Run `prisma migrate dev`.
3. Add business logic in `src/services/`.
4. Expose logic in `src/routes/`.
```

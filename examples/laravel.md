# Example output: Laravel project

```markdown
# Project Overview

| Area           | Value              |
| ---------------| -------------------|
| Framework      | Laravel 11         |
| Backend        | Laravel            |
| Database       | Eloquent + MySQL   |
| Authentication | Laravel Breeze / Sanctum |
| Payments       | Cashier (Stripe)   |
| Queue          | Laravel Queue      |
| Storage        | S3                 |
| Deployment     | Laravel Forge      |

# Folder Overview

app/
├── Http/
│   ├── Controllers/ <- Request handlers
│   └── Middleware/  <- Auth, throttle, etc.
├── Models/          <- Eloquent models
├── Providers/       <- Service providers
└── Services/        <- Business logic

routes/
├── web.php          <- Web routes
└── api.php          <- API routes

database/
├── migrations/      <- Schema migrations
└── seeders/         <- Seed data

# Authentication Flow

1. `POST /login` uses `AuthController`.
2. Laravel session or Sanctum token is created.
3. Middleware `auth` or `auth:sanctum` protects routes.

# API Overview

| Method | Route                 | Purpose            |
|--------|-----------------------|--------------------|
| POST   | /login                | Login              |
| POST   | /register             | Register           |
| GET    | /api/profile          | User profile       |
| POST   | /api/checkout         | Payment            |

# Important Files

- `app/Models/User.php`
- `routes/web.php`
- `routes/api.php`
- `config/auth.php`
- `config/database.php`
- `.env.example`

# Developer Guide

1. Copy `.env.example` to `.env`.
2. Run `php artisan migrate`.
3. Add routes in `routes/`.
4. Add controllers in `app/Http/Controllers/`.
```

# Laravel Livewire v3 Starter Kit

A Laravel 12 starter kit featuring **Livewire v3** (pinned), Flux UI, Tailwind CSS v4, Fortify authentication with 2FA, and Docker Sail with PostgreSQL.

## Stack

- **Laravel 12** — PHP framework
- **Livewire v3** — Full-stack reactive components (pinned to v3)
- **Flux UI** — Component library for Livewire (paid license required)
- **Tailwind CSS v4** — Utility-first CSS framework
- **Laravel Fortify** — Authentication backend (login, register, password reset, 2FA)
- **Laravel Sail** — Docker-based development environment (PostgreSQL)
- **Pest** — Testing framework

## Features

- Login / Register / Forgot Password / Email Verification
- Two-factor authentication (2FA)
- Dashboard
- Profile settings (name, email)
- Password change
- Appearance preferences (dark mode)
- Account deletion

---

## Prerequisites

> **Flux UI requires a paid license.** Without valid Flux credentials, `composer create-project` will fail.

1. PHP 8.2+
2. Composer
3. Node.js 20+ and npm
4. **A valid Flux UI license** — purchase at https://fluxui.dev

### Configure Flux credentials

Before installing, add your Flux credentials to your global Composer auth:

```bash
composer config --global http-basic.composer.fluxui.dev your@email.com your-license-key
```

---

## Quick Start

```bash
laravel new my-app --using=seito-developer/laravel-livewire-v3-starterkit
```

This will:
1. Download the template
2. Copy `.env.example` to `.env`
3. Generate an app key
4. Create a SQLite database and run migrations

Your app is ready at `http://localhost:8000` after running:

```bash
cd my-app
composer dev
```

---

## Switching to PostgreSQL with Sail

The default installation uses SQLite. To switch to Docker Sail with PostgreSQL:

1. Install Docker Desktop
2. Install Sail:
   ```bash
   php artisan sail:install
   ```
3. Update `.env` — uncomment and set the PostgreSQL values:
   ```
   DB_CONNECTION=pgsql
   DB_HOST=pgsql
   DB_PORT=5432
   DB_DATABASE=laravel
   DB_USERNAME=sail
   DB_PASSWORD=password
   ```
4. Start Sail and run migrations:
   ```bash
   ./vendor/bin/sail up -d
   ./vendor/bin/sail artisan migrate
   ```

---

## Development

```bash
composer dev
```

This runs concurrently:
- `php artisan serve` — HTTP server
- `php artisan queue:listen` — Queue worker
- `php artisan pail` — Log viewer
- `npm run dev` — Vite asset bundler

---

## Testing

```bash
composer test
```

---

## License

MIT

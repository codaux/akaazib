# Akaazib

Laravel 8 website for akaazib.ir.

## Requirements

- PHP 8.0
- Composer
- MySQL or MariaDB
- Node.js and npm, only when rebuilding front-end assets

This project is pinned to PHP 8.0 because the current Laravel/vendor versions emit PHP 8.1+ deprecation warnings.

## Security Status

This repository is prepared for public GitHub publishing: real environment files, dependencies, logs, sessions, cache files, and runtime artifacts are ignored.

Laravel 8 is end-of-life and no longer receives official security fixes. Treat the current setup as a compatibility release for the existing shared hosting environment. A Laravel upgrade should be planned before adding new features or handling higher-risk user data.

## Local Setup

```bash
composer install
npm install
cp .env.example .env
php artisan key:generate
php artisan migrate
npm run dev
php artisan serve
```

Set the real database values in `.env` before running migrations or opening database-backed pages.

## Production Notes

- Never commit `.env` or real credentials.
- Set `APP_ENV=production` and `APP_DEBUG=false`.
- Point the web server document root to `public/` when possible.
- If using cPanel, set this domain to PHP 8.0 separately from any WordPress domains.
- If the whole Laravel project is placed above `public_html`, copy only the contents of `public/` into `public_html` and adjust `public_html/index.php` paths to the project directory.

## GitHub Safety

The repository intentionally ignores:

- `.env` and environment-specific files
- `vendor/`
- `node_modules/`
- Laravel logs, sessions, cached views, and cache data
- generated local runtime files

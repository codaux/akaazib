# Security Policy

## Supported Runtime

This project currently targets PHP 8.0 because its Laravel 8 dependency set is not clean on newer PHP versions.

## Public Repository Rules

Do not commit:

- `.env` or any environment-specific `.env.*` file
- database credentials
- API keys or service tokens
- `vendor/`
- `node_modules/`
- Laravel logs, sessions, cached views, or cache data

Use `.env.example` for placeholders only.

## Known Risk

Laravel 8 is end-of-life. For long-term production security, upgrade Laravel and its dependencies before expanding the application.

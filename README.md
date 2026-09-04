# Akaazib

Laravel 12 website for akaazib.ir.

## Requirements

- PHP 8.4.1 or newer
- Composer
- MySQL or MariaDB
- Node.js and npm, only when rebuilding front-end assets

## Security Status

This repository is prepared for public GitHub publishing: real environment files, dependencies, logs, sessions, cache files, and runtime artifacts are ignored.

Laravel has been upgraded for modern PHP compatibility. Keep production on PHP 8.4.1+ and leave `APP_DEBUG=false`.

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

## VS Code Preview

This repository includes a VS Code task named `Laravel Preview Server`.

Start the local server from VS Code's integrated terminal:

```powershell
php artisan serve --host=127.0.0.1 --port=8012
```

Alternatively, press `Ctrl+Shift+B` to run the same command as the default build task. When the folder opens, VS Code may also ask whether automatic tasks are allowed; allowing it starts the server automatically on future opens.

After the terminal reports that the server is running, open:

```text
http://127.0.0.1:8012
```

Inside VS Code, run `Simple Browser: Show` from the command palette and paste that URL.

## Production Notes

- Never commit `.env` or real credentials.
- Set `APP_ENV=production` and `APP_DEBUG=false`.
- Point the web server document root to `public/` when possible.
- If using cPanel, set this domain to PHP 8.4.1+ separately from any WordPress domains.
- If the whole Laravel project is placed above `public_html`, copy only the contents of `public/` into `public_html` and adjust `public_html/index.php` paths to the project directory.

## GitHub Safety

The repository intentionally ignores:

- `.env` and environment-specific files
- `vendor/`
- `node_modules/`
- Laravel logs, sessions, cached views, and cache data
- generated local runtime files

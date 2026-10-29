# AGENTS.md

## Project
Laravel 12 landing page. Single-page app using Vite + Tailwind CSS 4 for frontend, Laravel for routing/rendering.

## Stack
- PHP 8.2+, Composer
- Node 18+ (Vite, Tailwind)
- SQLite (default DB)
- PHPUnit, Laravel Pint

## First Run
```bash
composer run setup
```
Installs PHP/Node deps, generates `.env`, creates DB, migrates, builds assets.

## Local Dev
```bash
composer run dev
```
Starts 4 concurrent processes: `php artisan serve` (port 8000), queue listener, Pail logs, `npm run dev` (Vite HMR). Kills all on exit. Uses concurrently CLI.

Single process alternative:
- Backend: `php artisan serve`
- Frontend: `npm run dev`

## Test
```bash
composer run test
```
Clears config cache, runs PHPUnit. Tests in `tests/Unit/` and `tests/Feature/`. Config uses in-memory SQLite + sync queue.

## Format
```bash
composer exec pint
```
Code formatter (Laravel standard).

## Asset Pipeline
Vite entry points: `resources/css/app.css`, `resources/js/app.js`. Tailwind v4 via `@tailwindcss/vite` plugin. Dev server watches all except `storage/framework/views/`.

## Routes
Single route in `routes/web.php`: `GET /` renders `welcome` view.

## DB
SQLite by default. Migrations in `database/migrations/`. Run manually with `php artisan migrate`.

## Build
```bash
npm run build
```
Compiles to `public/build/`. View checks for `build/manifest.json` or `hot` file (dev mode) to load assets.

## Notes
- `.env` created from `.env.example` on first setup
- `artisan key:generate` required (app key for encryption)
- Queue/session/cache all use database in local setup
- No custom instruction files exist; add to `opencode.json` `instructions` if reusing this session

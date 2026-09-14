# Foyer

Private photo and video web app for family and friends.

This repository is set up for **local-first** development. The Next.js app runs on your machine; Postgres and MinIO run in Docker.

## Stack

- **App:** Next.js (App Router) + TypeScript + Tailwind CSS
- **Package manager:** pnpm
- **Database:** Postgres 17
- **Object storage:** MinIO (S3-compatible)

## Prerequisites

- Node.js 22+
- [pnpm](https://pnpm.io/)
- Docker with Compose v2 (`docker compose`)

## Getting started

```bash
# 1. Environment
cp .env.example .env

# 2. Postgres + MinIO (data persists in named volumes)
docker compose up -d

# 3. Install and run the app
pnpm install
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000). MinIO console (optional): [http://localhost:9001](http://localhost:9001) — sign in with the keys from `.env.example`. Create the `foyer` bucket there when you start using storage.

## Scripts

| Command | Description |
| --- | --- |
| `pnpm dev` | Next.js dev server |
| `pnpm build` | Production build (includes typecheck) |
| `pnpm start` | Serve the production build |
| `pnpm lint` | ESLint |

Stop services with `docker compose down`. Volumes are kept unless you pass `-v`.

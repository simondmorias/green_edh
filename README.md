# Entity Data Hub (EDH)

The **Entity Data Hub (EDH)** is a modern MDM-style tool. It provides a central repository of entities (products, customers, geographies, markets, etc.), de-duplicates input data, manages hierarchies, and allows mapping of source records to canonical EDH keys.

This repository is a **monorepo** containing:

- **apps/web** – Next.js App Router app for both the **web UI** and **API routes**.  
- **services/worker** – BullMQ worker for long-running and scheduled EDH jobs (dedupe, harmonisation, hierarchy building).  
- **packages/db** – Prisma schema, migrations, and database access layer.  
- **packages/contracts** – Shared Zod schemas for API inputs/outputs, queue payloads, and domain events.  
- **packages/telemetry** – Logging, tracing, and metrics utilities.  
- **packages/ui** – Shared React components.  

---

## Quick start

You need **Node 20+**, **pnpm**, and **Docker**.

```bash
# 1. Install dependencies
pnpm install

# 2. Start local infra (Postgres + Redis)
pnpm dev:infra

# 3. Apply migrations and seed data
pnpm dev:db:migrate
pnpm dev:db:seed

# 4. Start Next.js web + API
pnpm dev:web

# 5. Start worker (in a second terminal)
pnpm dev:worker

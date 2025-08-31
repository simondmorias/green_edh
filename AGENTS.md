# Entity Data Hub - Agent Guidelines

## Repo Layout
- Follow the repository file/folder layout described here: ./docs/components/edh/repo_layout.md

## Build/Test Commands
- Install: `pnpm install`
- Dev: `pnpm dev:web` (Next.js), `pnpm dev:worker` (BullMQ worker)
- Infrastructure: `pnpm dev:infra` (Postgres + Redis via Docker)
- Database: `pnpm dev:db:migrate`, `pnpm dev:db:seed`
- Build: `pnpm build`
- Test: `pnpm test`, `pnpm test:watch`, `pnpm test -- path/to/test.spec.ts` (single test)
- Lint: `pnpm lint`, `pnpm lint:fix`
- Type check: `pnpm typecheck`

## Code Style
- TypeScript strict mode, prefer const assertions and type inference
- Imports: absolute imports from package roots (e.g., `@edh/db`, `@edh/contracts`)
- React: functional components with hooks, server components in app/, client components marked with "use client"
- Async/await over promises, handle errors with try/catch or Result types
- Naming: camelCase for variables/functions, PascalCase for types/components, UPPER_SNAKE for constants
- Prisma models in packages/db, Zod schemas in packages/contracts for validation
- BullMQ jobs in services/worker with proper error handling and retries
- Use pnpm workspaces for monorepo dependencies

## Documentation
- All documents related to the repo are in ./docs/components/edh/ - the other folders in ./docs are READ ONLY

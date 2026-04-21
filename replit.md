# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Each package manages its own dependencies.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)
- **AI**: OpenAI via Replit AI Integrations (gpt-5.2)

## Artifacts

### Website Adiwiyata Sekolah (`artifacts/adiwiyata`)
React + Vite frontend. A rich single-page educational website about the Indonesian school Adiwiyata environmental program. Features:
- Hero section with school garden background image
- "Apa itu Adiwiyata" section
- 4 Pillars of Adiwiyata
- Implementation tips (tumbler, etc.)
- Camera check feature to detect if a light is off (uses getUserMedia + Canvas brightness analysis)
- AI Chatbot powered by OpenAI GPT-5.2 for Adiwiyata Q&A
- Floating chatbot button

### API Server (`artifacts/api-server`)
Express 5 backend. Handles:
- `/api/healthz` - health check
- `/api/openai/conversations` - CRUD for chat conversations
- `/api/openai/conversations/:id/messages` - SSE streaming chat with system prompt focused on Adiwiyata

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.

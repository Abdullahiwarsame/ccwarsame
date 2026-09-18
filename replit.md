# CCWARSAME Growth Advisor

A premium personal-brand website for CCWARSAME, a Growth Advisor helping business owners and teams build practical skills and systems for sustainable growth.

## Run & Operate

- `pnpm --filter @workspace/ccwarsame-website run dev` — run the website preview
- `pnpm --filter @workspace/api-server run dev` — run the shared API server (not currently needed by the website)
- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from the OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- The website is frontend-only for now; no database or API environment variables are required.

## Stack

- pnpm workspaces, Node.js 24, TypeScript 5.9
- API: Express 5
- DB: PostgreSQL + Drizzle ORM
- Validation: Zod (`zod/v4`), `drizzle-zod`
- API codegen: Orval (from OpenAPI spec)
- Build: esbuild (CJS bundle)

## Where things live

- `artifacts/ccwarsame-website/src/App.tsx` — page routes, shared navigation/footer, service and resource content, and the contact form
- `artifacts/ccwarsame-website/src/index.css` — CCWARSAME theme, typography, responsive utilities, and motion
- `attached_assets/` — supplied CC Warsame logo and portrait

## Architecture decisions

- Keep the initial site frontend-only so content and conversion flows can ship without a CMS dependency.
- Use a shared shell with route-aware navigation across Home, About, Services, Resources, and Contact.
- Keep resource content local and filterable so it can later be replaced by a content API without changing the page structure.

## Product

- Introduces CCWARSAME as a Growth Advisor for business owners, entrepreneurs, and sales, marketing, and customer-support teams.
- Explains Business Growth and Team Development services.
- Provides a filterable resource shelf with detail dialogs.
- Captures work inquiries through a validated contact form with a success state.

## User preferences

_Populate as you build — explicit user instructions worth remembering across sessions._

## Gotchas

_Populate as you build — sharp edges, "always run X before Y" rules._

## Pointers

- See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details

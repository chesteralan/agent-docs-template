# CODEBASE MAP

High-level map of folders, ownership, and responsibilities.

## Repository Layout

```txt
nextjs-saas/
  src/
  tests/
  docs/
  scripts/
```

## Directory Responsibilities

- src/: Next.js app routes, components, API clients, shared types
- tests/: Jest and Playwright tests
- docs/: Architecture, onboarding, API
- scripts/: DB migrations, seeding, local dev

## Entry Points

- App entry point: src/app/layout.tsx
- Server entry point: src/app/api/*/route.ts
- Worker entry points: src/worker/index.ts

## Core Domains

- Project Management
  - Folder: src/domain/project
  - Main entities: Project, Task, User, Team
  - External dependencies: Stripe, SendGrid

## Shared Utilities

- Utility module: src/utils/date.ts
  - Purpose: Date formatting and parsing
  - Usage constraints: Use only for UI, not persistence

## Configuration

- Environment files: .env, .env.example
- Runtime config location: src/config/
- Feature flag definitions: src/config/featureFlags.ts

## Ownership

- Team or owner by area: @frontend, @backend, @devops
- Review requirements by area: 1 FE, 1 BE, 1 QA for major changes

## Navigation Tips For Agents

- Read these files first for most tasks: README.md, docs/ARCHITECTURE.md
- Files that are auto-generated and should not be hand-edited: src/generated/

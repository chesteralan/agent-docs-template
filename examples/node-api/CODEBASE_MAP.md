# CODEBASE MAP

High-level map of folders, ownership, and responsibilities.

## Repository Layout

```txt
node-api/
  src/
  tests/
  docs/
  scripts/
```

## Directory Responsibilities

- src/: Express API, domain services, shared types
- tests/: Unit and integration tests
- docs/: Architecture, onboarding, API
- scripts/: DB migrations, seeding, local dev

## Entry Points

- App entry point: src/app.ts
- Server entry point: src/server/index.ts
- Worker entry points: src/workers/index.ts

## Core Domains

- Project Management
  - Folder: src/domain/project
  - Main entities: Project, Task, User, Team
  - External dependencies: Stripe, SendGrid

## Shared Utilities

- Utility module: src/utils/date.ts
  - Purpose: Date formatting and parsing
  - Usage constraints: Use for request/response shaping only, not persistence defaults

## Configuration

- Environment files: .env, .env.example
- Runtime config location: src/config/
- Feature flag definitions: src/config/featureFlags.ts

## Ownership

- Team or owner by area: @api, @platform, @devops
- Review requirements by area: 1 API reviewer, 1 platform reviewer for major changes

## Navigation Tips For Agents

- Read these files first for most tasks: README.md, docs/ARCHITECTURE.md
- Files that are auto-generated and should not be hand-edited: src/generated/

# CODEBASE MAP

High-level map of folders, ownership, and responsibilities.

## Repository Layout

```txt
firebase/
  web/
  functions/
  firebase/
  tests/
  docs/
  scripts/
```

## Directory Responsibilities

- web/: frontend app and Firebase client integration
- functions/: Cloud Functions endpoints and background handlers
- firebase/: Firestore rules, indexes, and emulator config
- tests/: unit, integration, emulator, and e2e tests
- docs/: architecture, onboarding, API contracts
- scripts/: emulator helpers, data seeding, local automation

## Entry Points

- App entry point: web/src/main.tsx
- Server entry point: functions/src/index.ts
- Worker entry points: functions/src/triggers/*.ts

## Core Domains

- Project Management
  - Folder: src/domain/project
  - Main entities: Project, Task, User, Team
  - External dependencies: Stripe, SendGrid

## Shared Utilities

- Utility module: shared/utils/date.ts
  - Purpose: Date formatting and parsing
  - Usage constraints: Use for display and event serialization consistency

## Configuration

- Environment files: .env, .env.example, .firebaserc
- Runtime config location: functions/src/config/
- Feature flag definitions: web/src/config/featureFlags.ts

## Ownership

- Team or owner by area: @frontend, @firebase-platform, @devops
- Review requirements by area: 1 frontend reviewer and 1 firebase-platform reviewer for major changes

## Navigation Tips For Agents

- Read these files first for most tasks: README.md, docs/ARCHITECTURE.md
- Files that are auto-generated and should not be hand-edited: firebase-export/, functions/lib/

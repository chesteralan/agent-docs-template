# ARCHITECTURE

System design and technical structure overview.

## System Context

- Product domain: SaaS for team project management
- Core user journeys: Sign up, create project, invite team, manage tasks, track progress
- External systems and integrations: Email (SendGrid), Payments (Stripe), SSO (Google OAuth)

## High-Level Components

- Client applications: React SPA (Vite)
- Backend services: Node.js REST API (Express)
- Data stores: PostgreSQL, Redis (caching)
- Asynchronous workers and queues: BullMQ for background jobs

## Data Flow

1. User action enters via: React UI
2. Request is validated in: Express middleware
3. Domain logic runs in: Service layer (Node.js)
4. Persistence happens in: PostgreSQL via Prisma ORM
5. Response and events are emitted by: API and WebSocket server

## Module Boundaries

- Presentation layer: src/components, src/pages
- Application layer: src/services, src/hooks
- Domain layer: src/domain, src/models
- Infrastructure layer: src/db, src/infra

## Key Technical Decisions

- Decision: Use Vite for frontend build
  - Context: Fast dev, modern tooling
  - Choice: Vite over CRA
  - Tradeoffs: Less legacy support
  - Alternatives rejected: Create React App

## Reliability And Scalability

- Expected traffic profile: 1000 DAU, bursty during work hours
- Scaling strategy: Horizontal scaling on Vercel/Render
- Caching strategy: Redis for session and hot data
- Failure handling and retries: Retry jobs in BullMQ, circuit breakers on API

## Security Model

- Authentication: JWT, Google OAuth
- Authorization: Role-based (admin, member, guest)
- Sensitive data handling: .env secrets, encrypted at rest
- Audit and observability requirements: Winston logging, Sentry, audit tables

## Architecture Risks

- Known bottlenecks: N+1 queries in reporting
- Operational risks: Email deliverability, Stripe webhook failures
- Mitigations and owners: Add query batching, monitor webhooks, assign SRE

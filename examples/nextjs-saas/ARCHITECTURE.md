# ARCHITECTURE

System design and technical structure overview.

## System Context

- Product domain: SaaS for team project management
- Core user journeys: Sign up, create project, invite team, manage tasks, track progress
- External systems and integrations: Email (SendGrid), Payments (Stripe), SSO (Google OAuth)

## High-Level Components

- Client applications: Next.js web app (App Router)
- Backend services: Node.js REST API (Express)
- Data stores: PostgreSQL, Redis (caching)
- Asynchronous workers and queues: BullMQ for background jobs

## Data Flow

1. User action enters via: Next.js App Router page or server action
2. Request is validated in: Express middleware
3. Domain logic runs in: Service layer (Node.js)
4. Persistence happens in: PostgreSQL via Prisma ORM
5. Response and events are emitted by: API and WebSocket server

## Module Boundaries

- Presentation layer: src/app, src/components
- Application layer: src/services, src/actions
- Domain layer: src/domain, src/models
- Infrastructure layer: src/db, src/infra

## Key Technical Decisions

- Decision: Use Next.js App Router for frontend architecture
  - Context: Need first-class SSR, routing, and server components
  - Choice: Next.js over custom SSR setup
  - Tradeoffs: Tighter framework conventions and runtime constraints
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

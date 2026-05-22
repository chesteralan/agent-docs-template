# ARCHITECTURE

System design and technical structure overview.

## System Context

- Product domain: SaaS for team project management
- Core user journeys: Sign up, create project, invite team, manage tasks, track progress
- External systems and integrations: Email (SendGrid), Payments (Stripe), SSO (Google OAuth)

## High-Level Components

- Client applications: API consumers (web, mobile, internal tools)
- Backend services: Node.js REST API (Express)
- Data stores: PostgreSQL, Redis (caching)
- Asynchronous workers and queues: BullMQ for background jobs

## Data Flow

1. User action enters via: API client (web, mobile, or internal system)
2. Request is validated in: Express middleware
3. Domain logic runs in: Service layer (Node.js)
4. Persistence happens in: PostgreSQL via Prisma ORM
5. Response and events are emitted by: API and WebSocket server

## Module Boundaries

- API layer: src/routes, src/controllers
- Application layer: src/services
- Domain layer: src/domain, src/models
- Infrastructure layer: src/db, src/infra, src/queue

## Key Technical Decisions

- Decision: Use modular Express architecture for API
  - Context: API-focused service that needs maintainable route composition
  - Choice: Modular Express over monolithic route file
  - Tradeoffs: More files and explicit boundaries to maintain
  - Alternatives rejected: Single-file route/controller structure

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

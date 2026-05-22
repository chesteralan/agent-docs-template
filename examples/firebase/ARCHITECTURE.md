# ARCHITECTURE

System design and technical structure overview.

## System Context

- Product domain: SaaS for team project management
- Core user journeys: Sign up, create project, invite team, manage tasks, track progress
- External systems and integrations: Email (SendGrid), Payments (Stripe), SSO (Google OAuth)

## High-Level Components

- Client applications: Web app (Firebase SDK), optional mobile clients
- Backend services: Cloud Functions (HTTPS and background triggers)
- Data stores: Cloud Firestore, Firebase Storage
- Asynchronous workers and queues: Cloud Tasks and event-driven background functions

## Data Flow

1. User action enters via: Web app using Firebase SDK
2. Request is validated in: Cloud Functions handlers and Firestore Security Rules
3. Domain logic runs in: Cloud Functions service modules
4. Persistence happens in: Cloud Firestore rules and document operations
5. Response and events are emitted by: Cloud Functions responses and Firestore listeners

## Module Boundaries

- Presentation layer: web/src/components, web/src/app
- Application layer: web/src/services, functions/src/services
- Domain layer: functions/src/domain, shared/models
- Infrastructure layer: functions/src/infra, firebase/rules, firebase/indexes

## Key Technical Decisions

- Decision: Use Firebase managed backend services
  - Context: Need rapid iteration with managed auth, data, and hosting
  - Choice: Firestore + Functions + Hosting over self-managed API stack
  - Tradeoffs: Vendor lock-in and query/modeling constraints
  - Alternatives rejected: Custom Node.js API with relational database

## Reliability And Scalability

- Expected traffic profile: 1000 DAU, bursty during work hours
- Scaling strategy: Horizontal scaling on Firebase Hosting and Cloud Functions autoscaling
- Caching strategy: CDN edge caching via Hosting, selective in-memory caching in Functions
- Failure handling and retries: Function retry policies, dead-letter patterns, idempotent handlers

## Security Model

- Authentication: Firebase Auth (email/password, OAuth providers)
- Authorization: Role-based (admin, member, guest)
- Sensitive data handling: .env secrets, encrypted at rest
- Audit and observability requirements: Cloud Logging, Crashlytics, Firebase Audit Logs

## Architecture Risks

- Known bottlenecks: N+1 queries in reporting
- Operational risks: Email deliverability, Function trigger retries and idempotency handling
- Mitigations and owners: Model Firestore for read patterns, enforce idempotency keys, monitor error budgets

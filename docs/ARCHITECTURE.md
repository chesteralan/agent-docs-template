# ARCHITECTURE

System design and technical structure overview.

## System Context

- Product domain: {{PRODUCT_DOMAIN}}
- Core user journeys: {{CORE_USER_JOURNEYS}}
- External systems and integrations: {{EXTERNAL_INTEGRATIONS}}

## High-Level Components

- Client applications: {{CLIENT_COMPONENTS}}
- Backend services: {{BACKEND_COMPONENTS}}
- Data stores: {{DATA_STORES}}
- Asynchronous workers and queues: {{ASYNC_WORKERS}}

## Data Flow

1. User action enters via:
2. Request is validated in:
3. Domain logic runs in:
4. Persistence happens in:
5. Response and events are emitted by:
1. User action enters via: {{ENTRY_LAYER}}
2. Request is validated in: {{VALIDATION_LAYER}}
3. Domain logic runs in: {{DOMAIN_LAYER}}
4. Persistence happens in: {{PERSISTENCE_LAYER}}
5. Response and events are emitted by: {{RESPONSE_EVENT_LAYER}}

## Module Boundaries

- Presentation layer: {{PRESENTATION_MODULES}}
- Application layer: {{APPLICATION_MODULES}}
- Domain layer: {{DOMAIN_MODULES}}
- Infrastructure layer: {{INFRASTRUCTURE_MODULES}}

## Key Technical Decisions

- Decision:
  - Context: {{DECISION_CONTEXT}}
  - Choice: {{DECISION_CHOICE}}
  - Tradeoffs: {{DECISION_TRADEOFFS}}
  - Alternatives rejected: {{DECISION_ALTERNATIVES_REJECTED}}

## Reliability And Scalability

- Expected traffic profile: {{TRAFFIC_PROFILE}}
- Scaling strategy: {{SCALING_STRATEGY}}
- Caching strategy: {{CACHING_STRATEGY}}
- Failure handling and retries: {{FAILURE_HANDLING}}

## Security Model

- Authentication: {{AUTHENTICATION_MODEL}}
- Authorization: {{AUTHORIZATION_MODEL}}
- Sensitive data handling: {{SENSITIVE_DATA_POLICY}}
- Audit and observability requirements: {{AUDIT_OBSERVABILITY_REQUIREMENTS}}

## Architecture Risks

- Known bottlenecks: {{KNOWN_BOTTLENECKS}}
- Operational risks: {{OPERATIONAL_RISKS}}
- Mitigations and owners: {{MITIGATIONS_AND_OWNERS}}

# API CONTRACTS

Canonical API behavior and compatibility expectations.

## API Surface

- Protocols in use: {{API_PROTOCOLS}}
- Base URLs or service boundaries: {{API_BASE_BOUNDARIES}}
- Versioning strategy: {{API_VERSION_STRATEGY}}

## Endpoint Contract Template

- Endpoint: {{ENDPOINT_PATH}}
- Method: {{HTTP_METHOD}}
- Auth required: {{AUTH_REQUIRED}}
- Request schema: {{REQUEST_SCHEMA}}
- Response schema: {{RESPONSE_SCHEMA}}
- Error codes: {{ERROR_CODES}}
- Idempotency behavior: {{IDEMPOTENCY_BEHAVIOR}}

## Authentication And Authorization

- Auth mechanism: {{AUTH_MECHANISM}}
- Token or session requirements: {{TOKEN_OR_SESSION_REQUIREMENTS}}
- Scope and permission checks: {{AUTH_SCOPE_CHECKS}}

## Error Handling Standard

- Error envelope format: {{ERROR_ENVELOPE_FORMAT}}
- Stable machine-readable error codes: {{MACHINE_ERROR_CODES}}
- Retryable vs non-retryable classification: {{RETRYABLE_CLASSIFICATION}}

## Pagination And Filtering

- Pagination style: {{PAGINATION_STYLE}}
- Sort behavior: {{SORT_BEHAVIOR}}
- Filtering conventions: {{FILTERING_CONVENTIONS}}

## Backward Compatibility Rules

- What counts as a breaking change: {{BREAKING_CHANGE_DEFINITION}}
- Deprecation policy: {{DEPRECATION_POLICY}}
- Migration and sunset process: {{MIGRATION_SUNSET_PROCESS}}

## Webhook Or Event Contracts

- Event names: {{EVENT_NAMES}}
- Payload schema: {{EVENT_PAYLOAD_SCHEMA}}
- Delivery and retry policy: {{EVENT_DELIVERY_RETRY_POLICY}}

## Contract Testing

- Consumer-driven tests location: {{CONTRACT_TEST_LOCATION}}
- Schema validation approach: {{SCHEMA_VALIDATION_APPROACH}}
- Required checks in CI: {{CONTRACT_CI_CHECKS}}

# API CONTRACTS

Canonical API behavior and compatibility expectations.

## API Surface

- Protocols in use: HTTPS, REST, WebSocket
- Base URLs or service boundaries: /api/v1, /ws
- Versioning strategy: URL versioning (v1, v2)

## Endpoint Contract Template

- Endpoint: /api/v1/projects
- Method: POST
- Auth required: Yes (JWT)
- Request schema: { name: string, teamId: string }
- Response schema: { id: string, name: string, createdAt: string }
- Error codes: 400, 401, 403, 409
- Idempotency behavior: Idempotent for same name/teamId

## Authentication And Authorization

- Auth mechanism: JWT, Google OAuth
- Token or session requirements: Bearer token in Authorization header
- Scope and permission checks: Team membership, admin for write

## Error Handling Standard

- Error envelope format: { error: { code, message } }
- Stable machine-readable error codes: PROJECT_EXISTS, UNAUTHORIZED
- Retryable vs non-retryable classification: 5xx retryable, 4xx not

## Pagination And Filtering

- Pagination style: cursor-based
- Sort behavior: createdAt desc by default
- Filtering conventions: ?teamId=, ?status=

## Backward Compatibility Rules

- What counts as a breaking change: Removing fields, changing types
- Deprecation policy: 6 months notice, dual support
- Migration and sunset process: Announce, dual-run, remove

## Webhook Or Event Contracts

- Event names: project.created, task.completed
- Payload schema: { id, type, data }
- Delivery and retry policy: At least once, exponential backoff

## Contract Testing

- Consumer-driven tests location: tests/contract/
- Schema validation approach: zod, openapi
- Required checks in CI: Contract tests must pass

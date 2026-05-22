# REFACTOR RULES

Guidelines for safe, incremental refactoring.

## Objectives

- Improve maintainability without changing intended behavior.
- Reduce complexity and coupling.
- Preserve public contracts unless explicitly approved.

## Safe Refactor Workflow

1. Confirm current behavior with tests (pnpm test)
2. Make one small structural change at a time
3. Re-run tests after each meaningful step
4. Keep commits atomic and descriptive

## Non-Negotiable Constraints

- Do not mix feature work into refactor commits
- Do not change API contracts unintentionally
- Do not remove telemetry or observability hooks

## Risk Classification

- Low risk: Rename, extract, add types (with tests)
- Medium risk: Move files, change dependencies
- High risk: DB schema, API contract, auth logic

## Required Validation

- Unit tests for touched modules using pnpm test:unit
- Integration tests for cross-boundary behavior using pnpm test:integration
- Performance checks when changing hot paths using pnpm perf

## Documentation Updates

- Update docs/ARCHITECTURE.md for module boundary changes
- Update docs/API_CONTRACTS.md for public API changes
- Update docs/BUSINESS_RULES.md for domain logic changes

## Rollback Strategy

- Define rollback plan before high-risk refactors in docs/ROLLOUT.md
- Prefer feature flags for gradual rollout using src/config/featureFlags.ts
- Ensure database migrations are reversible when possible under db/migrations/

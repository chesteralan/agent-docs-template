# REFACTOR RULES

Guidelines for safe, incremental refactoring.

## Objectives

- Improve maintainability without changing intended behavior.
- Reduce complexity and coupling.
- Preserve public contracts unless explicitly approved.

## Safe Refactor Workflow

1. Confirm current behavior with tests.
2. Make one small structural change at a time.
3. Re-run tests after each meaningful step.
4. Keep commits atomic and descriptive.

## Non-Negotiable Constraints

- Do not mix feature work into refactor commits.
- Do not change API contracts unintentionally.
- Do not remove telemetry or observability hooks.

## Risk Classification

- Low risk: internal renames and extraction with full test coverage.
- Medium risk: cross-module dependency changes.
- High risk: data model and persistence behavior changes.

## Required Validation

- Unit tests for touched modules using {{UNIT_TEST_COMMAND}}.
- Integration tests for cross-boundary behavior using {{INTEGRATION_TEST_COMMAND}}.
- Performance checks when changing hot paths using {{PERF_CHECK_COMMAND}}.

## Documentation Updates

- Update architecture notes when module boundaries shift.
- Update API contracts when public behavior changes.
- Update business rules when domain behavior changes.

## Rollback Strategy

- Define rollback plan before high-risk refactors in {{ROLLOUT_RUNBOOK_PATH}}.
- Prefer feature flags for gradual rollout using {{FEATURE_FLAG_SYSTEM}}.
- Ensure database migrations are reversible when possible under {{MIGRATION_POLICY}}.

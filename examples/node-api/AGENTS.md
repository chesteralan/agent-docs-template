# AGENTS

Project-specific guidance for AI coding agents.

## Template Variables

- {{PROJECT_NAME}}: Node.js API Example
- {{PRIMARY_STACK}}: Node.js (Express) + PostgreSQL
- {{PACKAGE_MANAGER}}: pnpm
- {{TEST_COMMAND}}: pnpm test
- {{LINT_COMMAND}}: pnpm lint
- {{FORMAT_COMMAND}}: pnpm format
- {{CI_PIPELINE}}: .github/workflows/ci.yml

## Mission

- Help implement changes safely and quickly.
- Preserve behavior unless a requested change says otherwise.
- Keep architecture and docs consistent with implementation.

## Working Rules

- Read relevant files before editing.
- Prefer minimal, targeted changes.
- Avoid refactoring unrelated code.
- Keep naming and folder conventions consistent.
- Add tests for new behavior and bug fixes when possible.

## Coding Standards

- Follow Prettier and ESLint rules.
- Keep route handlers thin and push business logic into service modules.
- Use TypeScript for all new code.
- Keep comments focused on intent and constraints.

## Safety Constraints

- Do not remove auth, validation, or audit logic without explicit instruction.
- Do not change API contracts silently.
- Flag high-risk migrations and provide rollout steps.
- Preserve backward compatibility unless explicitly approved.

## Definition Of Done

- Feature or fix implemented.
- Tests updated and passing locally.
- Docs updated when behavior or conventions change.
- Known risks and assumptions documented.

## Pull Request Checklist

- Problem statement is clear.
- Scope is limited and justified.
- Breaking changes are called out.
- Validation steps are included.

## Project Overrides

- Runtime and framework: Node.js (Express)
- Primary package manager: pnpm
- Test commands: pnpm test
- Lint and format commands: pnpm lint, pnpm format
- CI pipeline expectations: .github/workflows/ci.yml

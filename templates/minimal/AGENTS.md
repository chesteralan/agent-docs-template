# AGENTS

Project-specific guidance for AI coding agents.

## Template Variables

- {{PROJECT_NAME}}: Human-readable project name.
- {{PRIMARY_STACK}}: Main stack summary, for example React + Node.js.
- {{PACKAGE_MANAGER}}: npm, pnpm, yarn, bun, pip, etc.
- {{TEST_COMMAND}}: Canonical test command.
- {{LINT_COMMAND}}: Canonical lint command.
- {{FORMAT_COMMAND}}: Canonical format command.
- {{CI_PIPELINE}}: CI workflow file or pipeline identifier.

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

- Follow existing code style and linting rules.
- Prefer pure functions and small modules where practical.
- Keep comments focused on intent and constraints.
- Avoid hidden side effects and global state coupling.

## Safety Constraints

- Do not remove auth, validation, or audit logic without explicit instruction.
- Do not change data contracts silently.
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

Fill in project-specific details:

- Runtime and framework: {{PRIMARY_STACK}}
- Primary package manager: {{PACKAGE_MANAGER}}
- Test commands: {{TEST_COMMAND}}
- Lint and format commands: {{LINT_COMMAND}} and {{FORMAT_COMMAND}}
- CI pipeline expectations: {{CI_PIPELINE}}

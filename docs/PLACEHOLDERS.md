# PLACEHOLDERS

Guide for placeholder variables used across documentation templates.

## Goals

- Keep template variables predictable and reusable
- Reduce ambiguity when customizing docs for a new project
- Improve AI agent context loading and consistency

## Placeholder Format

Use double curly braces with uppercase snake case:

```txt
{{PLACEHOLDER_NAME}}
```

Examples:

- {{PROJECT_NAME}}
- {{PRIMARY_STACK}}
- {{ARCHITECTURE_STYLE}}
- {{UNIT_TEST_COMMAND}}

## Naming Rules

- Use uppercase snake case only
- Prefer descriptive names over abbreviations
- Keep names stable across files once adopted
- Reuse existing placeholders before introducing new ones

## Common Placeholder Categories

- Project metadata: {{PROJECT_NAME}}, {{PROJECT_DESCRIPTION}}
- Stack and runtime: {{PRIMARY_STACK}}, {{RUNTIME_FRAMEWORK}}
- Paths and structure: {{APP_ENTRY_POINT}}, {{SERVER_ENTRY_POINT}}, {{ENV_FILES}}
- Quality and testing: {{UNIT_TEST_COMMAND}}, {{INTEGRATION_TEST_COMMAND}}, {{PERF_CHECK_COMMAND}}
- Ownership and process: {{AREA_OWNERSHIP}}, {{REVIEW_REQUIREMENTS}}, {{MIGRATION_POLICY}}

## Fill Strategy

1. Start with project identity placeholders first
2. Fill architecture and codebase map next
3. Fill business rules and API contracts
4. Finalize UI patterns, refactor rules, and glossary

## Linting And Validation Suggestions

- Ensure no unresolved placeholders remain before release
- Add CI checks for unresolved `{{...}}` markers in project-specific docs
- Prefer explicit values over vague wording

## Migration Notes

When renaming placeholders:

- Update all template files in one commit
- Document renamed placeholders in CHANGELOG
- Preserve backward compatibility if templates are versioned

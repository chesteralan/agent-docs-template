# BUSINESS RULES

Business logic constraints and policy rules that must be preserved.

## Domain Summary

- Primary business model: Subscription SaaS, per-seat billing
- Core entities: User, Team, Project, Task
- Critical workflows: Invite, assign, complete, archive tasks

## Invariants

- Invariant 1: A user must belong to at least one team
- Invariant 2: Only team admins can invite new members
- Invariant 3: Completed tasks cannot be edited

## Validation Rules

- Input validation: Email format, password strength
- Cross-field validation: Task due date after start date
- Lifecycle validation: Cannot delete a project with active tasks

## Permission Rules

- Who can perform each critical action: Only admins can delete projects
- Role and scope constraints: Guests can only view, not edit
- Exception paths: Support can override for recovery

## State Transitions

- Entity: Task
  - Allowed states: open, in_progress, completed, archived
  - Transition rules: open→in_progress→completed→archived
  - Forbidden transitions: completed→in_progress

## Financial Or Compliance Constraints

- Billing and pricing rules: Prorated on seat changes
- Tax or regional logic: VAT for EU customers
- Retention and regulatory requirements: 7-year data retention for invoices

## Edge Cases

- Known edge case: User removed from team with active tasks
  - Expected behavior: Tasks reassigned to admin
  - Rationale: Prevent orphaned work

## Change Management

- Rules that require product approval before edits: Billing logic, permission changes
- Rules that require legal or compliance review: Data retention, export features

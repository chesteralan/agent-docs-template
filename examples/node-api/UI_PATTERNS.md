# UI PATTERNS

API consumer and integration conventions for consistent client behavior.

## Design Principles

- Prioritize clarity over visual complexity.
- Optimize common workflows first.
- Keep interactions predictable.

## Component Guidelines

- Naming convention for API resources: plural nouns, kebab-case paths
- Composition strategy: Small route modules composed into versioned routers
- Reuse vs one-off rules: Reuse validation and serialization middleware across resources

## State And Data Loading

- Loading states: Skeletons for lists, spinners for actions
- Empty states: Friendly illustration and CTA
- Error states: Toast with retry, error boundary for fatal
- Optimistic update guidance: Use SWR mutate, rollback on error

## Forms And Validation

- Validation timing rules: On blur and submit
- Error message tone and placement: Friendly, below field
- Required field conventions: * for required, aria-required

## Accessibility Standards

- Keyboard navigation expectations: Tab order, skip links
- Focus management rules: Focus trap in dialogs
- Color contrast targets: WCAG AA
- Semantic HTML and ARIA constraints: Use native elements, aria-labels

## Responsive Behavior

- Breakpoint strategy: Tailwind breakpoints (sm, md, lg)
- Mobile-first or desktop-first approach: Mobile-first
- Content prioritization by viewport: Main actions top, nav bottom on mobile

## Visual Language

- Typography scale: Tailwind defaults
- Spacing system: 4/8/16/24px
- Color tokens: Tailwind config
- Motion and animation constraints: 150ms fade/slide, reduce motion for a11y

## Frontend Testing Expectations

- Component test strategy: Contract and integration tests for routes and middleware
- End-to-end coverage for critical flows: API smoke tests for auth, project CRUD, and webhooks

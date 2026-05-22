# UI PATTERNS

UI and UX conventions for consistent, accessible interfaces.

## Design Principles

- Prioritize clarity over visual complexity.
- Optimize common workflows first.
- Keep interactions predictable.

## Component Guidelines

- Naming convention for components: PascalCase, suffix with 'Dialog', 'List', etc.
- Composition strategy: Use composition over inheritance, prefer hooks
- Reuse vs one-off component rules: Reuse for all forms, one-off for modals

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

- Component test strategy: React Testing Library, 80% coverage
- End-to-end coverage for critical flows: Playwright, login/signup, project CRUD

# Template Stability Policy

This document defines the stability guarantees for all core templates and example packs in this repository.

## What Is Stable?

- The structure, section headings, and placeholder conventions of all files in `docs/`, `templates/`, and `examples/`.
- The meaning and usage of all documented placeholders in [PLACEHOLDERS.md](PLACEHOLDERS.md).
- The validation checklist format in [VALIDATION.md](VALIDATION.md).

## Stability Guarantees

- No breaking changes to template structure or placeholder names within a major version (e.g., 1.x.x).
- All changes to template structure or placeholders will be documented in [CHANGELOG.md](../CHANGELOG.md) and released as a new major version.
- Minor and patch releases may add new optional sections, clarify guidance, or fix typos without breaking compatibility.

## Deprecation Policy

- Deprecated sections or placeholders will be marked clearly in the template and [CHANGELOG.md](../CHANGELOG.md).
- Deprecated items will be removed only in the next major version.

## How To Propose Changes

- Open an issue describing the proposed change and its impact.
- Major changes require consensus from maintainers and a migration guide.

## Versioning

- This repository follows [Semantic Versioning](https://semver.org/).
- The current stable version is v1.0.0 (pending release).

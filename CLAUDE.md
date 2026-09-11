# Repository Directives: Legacy Re-Engineering

## Operational Rules
1. **Isolation**: Legacy code (`/legacy`, `/poc`, or existing messy code) is read-only. Never modify legacy code directly unless explicitly instructed.
2. **Spec-First Enforcement**: No new source code may be written in `/src` without an approved specification file in `/docs/specs/<module-name>.spec.md`.
3. **Diagram Standard**: Generate all visual representations using Mermaid syntax.

## Quality Gates
- **Type Safety**: Target implementations must feature strict typing and zero implicit `any`/`object` abstractions.
- **Test-Driven**: Code generation must produce unit tests covering edge cases identified in the specification before completing execution.
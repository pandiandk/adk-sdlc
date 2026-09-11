# Copilot Code Completion Rules

- **Source of Truth**: Always base completions on specification files in `docs/specs/*.spec.md`. Do not duplicate legacy code structures or anti-patterns found in `/legacy`.
- **Typing & Contracts**: Ensure all suggestions use explicit types, strict null checks, and match the schema specifications defined in the API contract section of specs.
- **Error Boundaries**: Wrap network, I/O, and data transformation operations in explicit error handling structures corresponding to the Error Matrix in the relevant spec.
- **Test Generation**: When generating tests, reference the edge case matrix and sequence flows from the corresponding `.spec.md` file.
---
name: spec-driven-build
description: Reads a specification file from docs/specs/ and constructs clean, modern, strongly-typed code along with comprehensive unit and integration tests. Use when generating target code from specifications.
---
# Spec-Driven Implementation Engine

Target Spec File: $ARGUMENTS

1. **Spec Parsing**: Read the targeted `.spec.md` file completely. Extract LLD, API contracts, data models, error handling, and volume/concurrency edge cases.
2. **Test Engineering**:
   - Write failing test suites covering happy paths, edge cases, race conditions, and validation matrices listed in Section 8 of the spec.
   - Store tests in `/tests/` reflecting target application layout.
3. **Target Code Synthesis**:
   - Implement clean source code under `/src/` matching the LLD and API definitions strictly.
   - Utilize standard design patterns to fix anti-patterns noted in the legacy code.
   - Ensure explicit types, validation layers, and structural boundary guards.
4. **Verification**: Run tests against the newly generated code to confirm full compliance with the specification.
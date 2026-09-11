---
name: legacy-reverse-engineer
description: Performs deep static and dynamic analysis on legacy/POC code to generate comprehensive markdown specifications covering C4 models, HLD, LLD, API contracts, dependencies, user journeys, data workflows, and data volume/edge issues. Use when asked to audit, analyze, or document existing code.
---
# Legacy Reverse Engineering & Specification Engine

Target File or Directory: $ARGUMENTS

Extract business logic, execution paths, hidden constraints, and architectural patterns from the target legacy code. Generate a detailed specification document saved to `docs/specs/<target_module_or_system>.spec.md` adhering strictly to the following structure:

# System Specification: [Module / System Name]

## 1. C4 Architecture Model
- **Context Diagram**: External actors, upstream systems, downstream targets, and boundary definitions (Mermaid).
- **Container Diagram**: High-level execution environments, web servers, queues, datastores, and RPC boundaries (Mermaid).
- **Component Diagram**: Internal module organization, services, controllers, and repositories (Mermaid).
- **Code Diagram**: Class/interface representations for critical domain models.

## 2. High-Level Design (HLD)
- **System Overview**: Core business function, primary responsibilities, and key design trade-offs in legacy code.
- **Architectural Patterns**: Currently used patterns (e.g., monolith, event-driven, pipeline) and structural deficiencies.
- **Security & Auth Boundaries**: Encryption, session management, token handling, and authorization rules.

## 3. Low-Level Design (LLD)
- **Module Hierarchy**: Concrete breakdowns of classes, interfaces, abstract definitions, and methods.
- **Design Patterns**: Inferred patterns (Factory, Strategy, Observer) and structural anti-patterns to refactor.
- **State Machines**: State transitions, valid mutations, and state management logic.

## 4. API Documentation
- **Endpoints & Schemas**: HTTP verbs, paths, gRPC methods, header requirements, request/response bodies (JSON/Protobuf).
- **Status Codes & Error Contract**: Matrix of success status codes, domain errors, payload errors, and custom exception definitions.
- **Authentication & Authorization**: Required scopes, security headers, and RBAC rules per endpoint.

## 5. Dependency Architecture
- **Third-Party Libraries**: Explicit list of imported frameworks, packages, version limits, and license constraints.
- **Internal Services**: External REST/RPC dependencies, message brokers, databases, and third-party SaaS integrations.
- **System Requirements**: OS dependencies, environment variables, binary runtimes, and compute constraints.

## 6. User Journeys & Interaction Sequences
- **Actor Matrix**: Primary users, system personas, cron tasks, and programmatic triggers.
- **Sequence Diagrams**: Step-by-step user interaction flow from trigger to final response (Mermaid sequence format).
- **Failure Journeys**: How the user path handles partial failures, timeouts, and form re-submissions.

## 7. Data Workflows & Pipelines
- **Ingestion & Transformation**: Data structures entering the system, validation logic, mutation steps, and persistence points.
- **Storage Mapping**: Tables, document schemas, indexes, cache layers (Redis/Memcached), and persistence lifecycles.
- **Data Flow Diagram**: Visual flow of data from ingress, through processing layers, to storage or output streams.

## 8. Volume, Scalability & Data Issue Matrix
- **Payload & Throughput Constraints**: Observed rate limits, payload size caps, memory bottlenecks, and memory leak risks.
- **Data Quality & Edge Cases**: Malformed input scenarios, null handling, type coercion issues, missing foreign keys, and dirty data quirks in legacy.
- **Concurrency & Race Conditions**: Unlocked shared state, database deadlock risks, out-of-order execution scenarios, and idempotency vulnerabilities.
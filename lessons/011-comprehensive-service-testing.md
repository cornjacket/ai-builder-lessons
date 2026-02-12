# Lesson 011: Comprehensive Testing for New Service Creation

## Context

When building new services, ensuring their correctness, reliability, and proper integration is paramount. A robust testing strategy, encompassing multiple tiers, is a critical part of the "Definition of Done" for any service. This lesson outlines a comprehensive approach to testing new service creation, guiding both human and AI developers on the expected test coverage.

## Insight

A new service is not complete until it has been verified across all relevant testing tiers: unit, integration, component, and end-to-end (E2E). Each tier serves a distinct purpose in validating different aspects of the service's functionality and integration. These requirements should be explicitly documented as part of the service creation guidelines.

## Testing Tiers for New Services

### 1. Unit Tests

*   **Purpose**: Verify individual functions, methods, or small units of code in isolation. All external dependencies are mocked.
*   **Focus**: Correctness of algorithms, business logic, and error paths within a single code unit.
*   **When to Apply**: Always required for any new code within the service.
*   **Execution**: Typically via `go test ./...` (using `make test`).

### 2. Integration Tests

*   **Purpose**: Verify interactions between the service's code and its immediate infrastructure adapters (e.g., database repositories, message bus producers/consumers). These tests run against real, but test-isolated, infrastructure instances (e.g., Postgres, Redpanda in `docker-compose`).
*   **Focus**: Correctness of database queries, message serialization/deserialization, and interaction with external systems.
*   **When to Apply**: Required when a service interacts with any external infrastructure component.
*   **Execution**: Requires the local skeleton `docker-compose` environment (`make skeleton-up`), run via `go test -tags=integration ./...` (using `make test-integration`).

### 3. Component Tests

*   **Purpose**: Validate the entire service's pipeline from its entry points (e.g., HTTP server `Start()` function) to its defined outputs, within its own boundary. These tests use real infrastructure for inputs (e.g., HTTP requests, Redpanda messages) and mock external outputs (e.g., downstream service calls, projection writers).
*   **Focus**: Verifying the service's internal wiring, configuration, event processing flow, and adherence to its defined contracts. They act as a "black box" test for the service as a whole.
*   **When to Apply**: Essential for any new service that has a `Start()` entry point and an internal event processing pipeline.
*   **Execution**: Requires the local skeleton `docker-compose` environment (`make skeleton-up`), run via `go test -tags=component ./internal/services/...` (using `make test-component`).

### 4. End-to-End (E2E) Tests

*   **Purpose**: Validate the overall system behavior, verifying that multiple services correctly integrate and fulfill user-facing or system-level requirements across the entire platform.
*   **Focus**: High-level functional flows, system-wide integration, and adherence to external API contracts.
*   **When to Apply**: Required when a new service introduces or significantly alters an end-to-end user journey or system flow.
*   **Execution**: Runs against either the skeleton (`make e2e-skeleton`) or fullstack (`make e2e-fullstack`) local environments.

## Importance

*   **Early Bug Detection**: Different tiers catch bugs at different levels, reducing the cost of fixing them.
*   **Confidence in Changes**: Passing tests provide confidence that new services function as intended and integrate correctly.
*   **Definition of Done**: Fulfilling these testing requirements is a non-negotiable part of declaring a service "complete," ensuring quality before deployment.
*   **AI Guidance**: Explicitly documenting these testing expectations guides AI agents in generating appropriate test suites and verifying their own implementations.

## Related Guidelines

*   [Service Creation Guidelines](../../../platform-services/DEVELOPMENT.md#service-creation-guidelines)
*   [Definition of Done for a Development Task](../../../platform-services/DEVELOPMENT.md#definition-of-done-for-a-development-task)
*   [Insight: Abstract Test Infrastructure for Local vs CI](../../lessons/005-abstract-test-infrastructure-for-local-vs-ci.md)

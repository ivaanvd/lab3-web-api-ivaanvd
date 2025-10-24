# Lab 3 Web API -- Project Report

## Description of Changes
### Tests
- Completed the missing mocks and verification logic in `ControllerTests` for `EmployeeController`.
- **POST /employees**: Mocked `save()` to return different IDs for multiple calls to test non-idempotency. Verified `save()` is called twice and no other repository methods are invoked.
- **GET /employees/{id}**: Mocked `findById()` for both existing and non-existing employees. Verified safe and idempotent behavior.
- **PUT /employees/{id}**: Mocked `findById()` and `save()` to simulate creation and update scenarios. Verified idempotent behavior with correct repository calls.
- **DELETE /employees/{id}**: Mocked `deleteById()` using `justRun` to simulate deletion. Verified idempotent behavior and that no other repository methods were called.
- Ensured all tests run successfully using `./gradlew test`.

## Technical Decisions
- **MockK + SpringMockK**: Chosen to isolate controller logic and simulate repository behavior.
- **Separation of Concerns**: Focused tests on controller behavior without depending on actual repository or database.
- **REST Principles**: Verified HTTP methods compliance with safe (GET) and idempotent (PUT, DELETE) semantics.
- **Repository Verification**: Carefully checked repository calls to ensure proper handling of safe and idempotent methods.

## Learning Outcomes
- Learned how to effectively mock repository responses with MockK in Spring Boot tests.
- Gained practical experience verifying safe and idempotent HTTP method behavior.
- Learned to simulate multiple repository states for different test scenarios.
- Strengthened understanding of POST (non-idempotent), GET (safe + idempotent), PUT (idempotent), DELETE (idempotent) semantics in REST APIs.
- Improved debugging skills for controller tests and verification of repository interactions.

## AI Disclosure
### AI Tools Used
- ChatGPT

### AI-Assisted Work
- REPORT.md is mostly AI Generated with some corrections

### Original Work
- Completed all mocks and verification logic manually.
- Ensured correct behavior for POST, GET, PUT, and DELETE endpoints.
- Ran and debugged all tests until they passed successfully.

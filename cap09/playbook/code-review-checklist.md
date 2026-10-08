# Code Review Checklist for Agent-Generated Output

## Pre-Review: Automated Quality Gates

Before human review begins, verify:
- [ ] All existing tests pass (no regressions)
- [ ] New tests are included and pass
- [ ] Static analysis / linting passes
- [ ] Security scanning passes (dependency checks, secret detection)
- [ ] Code coverage does not decrease
- [ ] PR description clearly states what was changed and why

If any automated gate fails, return to the specifying engineer. Do not begin human review.

---

## Layer 1: Correctness Review (5-10 minutes)

### Specification Compliance
- [ ] Does the code implement what the specification asked for?
- [ ] Are all acceptance criteria from the spec met?
- [ ] Are there any extra behaviors not in the specification?

### Edge Case Handling
- [ ] Null/nil input handling
- [ ] Empty collections (empty arrays, empty strings, empty maps)
- [ ] Boundary values (zero, negative numbers, max int)
- [ ] Missing or malformed data
- [ ] Network timeout / service unavailability
- [ ] Concurrent access / race conditions
- [ ] Large data sets (pagination, memory limits)

### Logic Correctness
- [ ] Conditional branches handle all cases correctly
- [ ] Loop termination conditions are correct
- [ ] Off-by-one errors checked
- [ ] Boolean logic is correct (especially negations and compound conditions)
- [ ] Return values are correct in all code paths
- [ ] Error handling follows team patterns

---

## Layer 2: Security Review (3-5 minutes, more for sensitive code)

### Input Validation
- [ ] All external inputs are validated and sanitized
- [ ] Input length limits are enforced
- [ ] Type checking is appropriate
- [ ] No SQL injection, command injection, or prompt injection risks

### Authorization and Authentication
- [ ] Access controls are properly implemented
- [ ] Authorization checks are in the right place (not byppassable)
- [ ] No privilege escalation paths
- [ ] Session/token handling is correct

### Data Protection
- [ ] Error messages do not leak sensitive information
- [ ] Logs do not contain PII, secrets, or tokens
- [ ] No hardcoded credentials, API keys, or secrets
- [ ] Sensitive data is encrypted at rest and in transit where required

### Configuration
- [ ] Defaults are secure (deny by default, least privilege)
- [ ] Configuration is externalized (not hardcoded)
- [ ] Feature flags are properly gated

---

## Layer 3: Architecture Review (3-5 minutes)

### Pattern Consistency
- [ ] Code follows the team's established error handling pattern
- [ ] Code uses existing abstractions (not reinventing utilities)
- [ ] Naming conventions match the codebase
- [ ] File structure follows team standards

### Dependencies
- [ ] No unnecessary new dependencies introduced
- [ ] New dependencies are from trusted sources
- [ ] No duplicate functionality with existing dependencies
- [ ] Dependency versions are appropriate

### Maintainability
- [ ] Code is readable and self-documenting
- [ ] Complexity is appropriate (not over-engineered or under-structured)
- [ ] Future modifications would be straightforward
- [ ] No premature optimization or premature abstraction

### Integration
- [ ] Changes integrate well with surrounding code
- [ ] API contracts are maintained (backward compatibility)
- [ ] Database interactions are efficient (no N+1 queries)
- [ ] Async/sync patterns are correct

---

## Layer 4: Test Review (3-5 minutes)

### Coverage
- [ ] Tests cover the happy path
- [ ] Tests cover the edge cases identified above
- [ ] Tests cover error/exception paths
- [ ] Tests cover boundary conditions

### Quality
- [ ] Tests test behavior, not implementation details
- [ ] Tests are independent (no order dependency)
- [ ] Tests would catch a regression if the code were modified
- [ ] Test names clearly describe what they verify

### Agent-Specific Test Concerns
- [ ] Tests are not just re-implementing the code logic
- [ ] Tests are not trivially passing (testing what was already true)
- [ ] Test data is realistic, not just minimal
- [ ] Mocking is appropriate (not over-mocked to the point of testing nothing)

---

## Escalation Criteria

This PR requires **additional architectural review** if:
- [ ] It creates or modifies a public API
- [ ] It changes a database schema
- [ ] It modifies authentication or authorization logic
- [ ] It changes cross-service communication patterns
- [ ] It touches payment, billing, or financial processing
- [ ] It modifies data retention or privacy-related behavior
- [ ] The reviewer is uncertain about any aspect

---

## Risk Classification

**High Risk** — Full checklist + architectural review:
- Payment/financial logic
- Authentication/authorization
- Data model changes
- Public API changes
- Compliance-relevant code

**Medium Risk** — Full checklist:
- Business logic
- Internal APIs
- Configuration changes
- New integrations

**Low Risk** — Abbreviated checklist (correctness + test review):
- Test additions
- Documentation
- Minor refactoring
- Style/formatting changes

---

## Review Quality Tracking

After each review, note:
- Time spent: ___ minutes
- Risk level: High / Medium / Low
- Issues found: ___
- Severity of issues: Critical / Major / Minor / None
- Confidence in review: High / Medium / Low

Track weekly: Escaped defect rate for reviewed code

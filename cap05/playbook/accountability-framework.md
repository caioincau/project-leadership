# AI Accountability Framework

## Purpose

This document defines who is responsible for what in AI-assisted development workflows. It ensures that every AI-influenced output has clear human ownership, that review processes are substantive, and that incidents are investigated systemically.

---

## RACI Matrix for AI-Assisted Development

| Activity | Specifying Engineer | Reviewing/Merging Engineer | Tech Lead / Architect | Engineering Manager |
|---|---|---|---|---|
| Task specification quality | **R** (Responsible) | C (Consulted) | C (Consulted) | I (Informed) |
| Agent output quality | I | **A** (Accountable) | C | I |
| Architectural fit | C | R | **A** | I |
| Security review | I | R | **A** | I |
| Production behavior | I | **A** | C | I |
| Review process effectiveness | I | R | R | **A** |

**Key principle:** The engineer who merges an agent-generated PR is accountable for its production behavior, with the same weight as if they had written the code themselves.

---

## Review Standards for Agent-Generated Code

### Mandatory Checks (All Agent PRs)

- [ ] **Architectural fit:** Does the code follow established team patterns?
- [ ] **Edge case handling:** Are null inputs, empty collections, timeouts, and service unavailability handled?
- [ ] **Naming and readability:** Are variables, functions, and classes named consistently with the codebase?
- [ ] **Test adequacy:** Do tests cover the meaningful scenarios, not just the happy path?
- [ ] **Dependency hygiene:** Does the code avoid unnecessary new dependencies?

### Security-Focused Checks (PRs touching external interfaces, auth, or data)

- [ ] **Input validation:** Are all external inputs validated and sanitized?
- [ ] **Authorization:** Are access controls properly implemented?
- [ ] **Data exposure:** Do error messages, logs, or responses avoid leaking sensitive information?
- [ ] **Secrets:** Are there any hardcoded credentials, tokens, or keys?
- [ ] **Injection risks:** Is the code safe from SQL injection, command injection, or prompt injection?

### Architecture-Focused Checks (PRs affecting APIs, schemas, or cross-team contracts)

- [ ] **API contract:** Does the change maintain backward compatibility?
- [ ] **Data model:** Are schema changes migratable and reversible?
- [ ] **Performance:** Does the change introduce potential performance bottlenecks?
- [ ] **Observability:** Does the change include appropriate logging, metrics, and tracing?

---

## Risk-Based Review Intensity

| Risk Level | Examples | Review Requirement |
|---|---|---|
| **High** | Payment logic, auth, data model changes, public APIs | Full structured review + architect sign-off |
| **Medium** | Business logic, internal APIs, configuration changes | Full structured review by senior engineer |
| **Low** | Tests, documentation, minor refactoring, style fixes | Standard review, checklist optional |

---

## Escalation Criteria

Agent-generated output requires escalated review when:

1. The change modifies a public API or cross-team contract
2. The change touches authentication, authorization, or encryption
3. The change modifies database schemas or data migration logic
4. The change is in a service with regulatory compliance requirements
5. The reviewer is uncertain about any aspect of the change (when in doubt, escalate)

---

## Incident Postmortem: Additional Questions for Agent-Caused Failures

Add these to your standard postmortem template when agent-generated code is involved:

1. **Was this code agent-generated?** Tag for AI accountability tracking.
2. **Specification quality:** Was the task well-defined with clear acceptance criteria?
3. **Review depth:** Who reviewed? How long? Were there substantive comments?
4. **Checklist adherence:** Was the review checklist used? Would it have caught this issue?
5. **Pattern analysis:** Have similar issues occurred in agent-generated code before?

### Root Cause Categories for Agent Failures

- [ ] Specification gap (ambiguous or incomplete task definition)
- [ ] Review gap (reviewer missed the issue)
- [ ] Checklist gap (existing checklist does not cover this failure mode)
- [ ] Tooling gap (agent consistently produces this type of error)
- [ ] Training gap (reviewer was not trained to catch this type of issue)

---

## Metrics for Accountability Effectiveness

| Metric | Frequency | Target | Alert Threshold |
|---|---|---|---|
| Escaped defect rate (agent PRs) | Weekly | Declining or stable | >2x increase WoW |
| Average review time (agent PRs) | Weekly | >10 min per PR | <5 min average |
| Agent PRs with substantive comments | Monthly | >70% | <50% |
| Agent-related incidents | Monthly | Declining | 3+ in one month |
| Time to identify agent-code as root cause | Per incident | <30 min | >2 hours |

---

## Adoption and Review Schedule

- [ ] Review this framework with tech leads (date: _______)
- [ ] Train all reviewers on agent output review (date: _______)
- [ ] Add postmortem questions to template (date: _______)
- [ ] Begin tracking accountability metrics (date: _______)
- [ ] First quarterly review of framework effectiveness (date: _______)

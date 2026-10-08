# AI Security and Compliance Policy for Engineering Teams

**Version:** 1.0
**Last Updated:** ___________
**Next Review Date:** ___________
**Owner:** ___________

---

## 1. Approved AI Tools

| Tool | Approved Use | Data Agreement | Configuration Requirements |
|---|---|---|---|
| | | Enterprise / Standard | |
| | | | |
| | | | |

**Prohibited tools:** ___________
**Exception process:** ___________

---

## 2. Data Handling Rules

### Data Classification for AI Tool Usage

| Data Type | Can Share with AI Tools? | Conditions |
|---|---|---|
| Open-source code | Yes | No restrictions |
| Internal code (non-sensitive) | Yes | Enterprise account only |
| Code with business logic | Yes | Enterprise account with data retention agreement |
| Configuration with secrets | **NO** | Must sanitize before sharing |
| Customer PII | **NO** | Never share with AI tools |
| Production credentials | **NO** | Never share with AI tools |
| Compliance-sensitive code | Conditional | Requires security team approval |
| Log data with PII | **NO** | Sanitize before sharing |

### Practical Guidelines for Engineers

- [ ] Use environment variable references, never actual values
- [ ] Sanitize log excerpts before including in prompts (remove customer IDs, emails, IPs)
- [ ] Do not paste production database query results into AI tools
- [ ] Use synthetic/test data when debugging with AI assistance
- [ ] Report accidental data exposure immediately (see Section 5)

---

## 3. Code Review Requirements for Security

### Security Review Triggers

All agent-generated PRs require security-focused review when they touch:
- [ ] External-facing endpoints or APIs
- [ ] Authentication or authorization logic
- [ ] Data access or database queries
- [ ] Payment, billing, or financial processing
- [ ] PII handling or data privacy logic
- [ ] Cryptographic operations
- [ ] Configuration or infrastructure changes
- [ ] Third-party integrations

### Security Review Checklist (Minimum)

- [ ] Input validation on all external inputs
- [ ] Authorization checks present and consistent
- [ ] Error messages do not leak sensitive information
- [ ] No hardcoded secrets or credentials
- [ ] Parameterized queries (no string concatenation for SQL)
- [ ] Secure defaults (deny by default, least privilege)
- [ ] Logging does not include PII or secrets

---

## 4. Code Provenance and Audit Trail

### Required Documentation

For each agent-generated code change, the audit trail must include:

| Element | Where Captured | How |
|---|---|---|
| Specification author | PR description | Engineer name + spec link |
| AI tool used | PR labels or metadata | Tool name + version |
| Reviewer(s) | PR review history | Git/platform review record |
| Review checklist used | PR comments | Checklist completion record |
| Merge approver | Git merge record | Platform merge history |

### Retention

Audit trail records are retained for: _____ years (align with regulatory requirements)

---

## 5. Incident Classification and Response

### AI-Related Security Incident Types

| Type | Description | Severity | Response Time |
|---|---|---|---|
| Data exposure | Sensitive data sent to AI tool | High | 4 hours |
| Code vulnerability | Agent-generated security flaw in production | Critical/High | Per existing SLA |
| Compliance violation | AI-generated code violates regulatory requirement | Critical | 2 hours |
| Policy violation | Engineer uses unapproved tool or shares prohibited data | Medium | 24 hours |

### Response Process

1. **Identify** — Classify the incident type and severity
2. **Contain** — Limit blast radius (revoke credentials, check for pattern spread)
3. **Investigate** — Trace the full chain: spec → agent → review → production
4. **Remediate** — Fix the immediate issue and update controls
5. **Report** — Document per existing incident reporting requirements
6. **Improve** — Update policy, training, or checklists based on findings

### Blast Radius Check for Agent-Generated Vulnerabilities

When a security issue is found in agent-generated code:
- [ ] Check other recent PRs from the same agent session/configuration
- [ ] Search for the same vulnerability pattern across the codebase
- [ ] Review other PRs by the same specifying engineer (specification pattern issue?)
- [ ] Update the review checklist if the issue was a known gap

---

## 6. Training Requirements

### Initial Training (Required before AI tool usage)

- [ ] AI tool data handling policies
- [ ] Common vulnerability patterns in agent-generated code
- [ ] Security review techniques for agent output
- [ ] Incident reporting process
- [ ] Approved tools and configurations

### Ongoing Training

- [ ] Annual security refresher for all AI tool users
- [ ] Quarterly "red team" review exercise results shared with team
- [ ] Training updated when significant tool changes occur

---

## 7. Quarterly Review Checklist

- [ ] Approved tool list reviewed and updated
- [ ] Data handling rules reviewed against current tool capabilities
- [ ] Red team exercise conducted on recent agent-generated PRs
- [ ] Incident log reviewed for patterns
- [ ] Training materials updated based on new findings
- [ ] Regulatory landscape reviewed for AI-related changes
- [ ] Policy version updated and re-approved

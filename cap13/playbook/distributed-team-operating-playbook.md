# Distributed Team Operating Playbook for AI-Native Engineering

## Team Distribution Map

| Geography | Teams | Engineers | Time Zone (UTC) | Overlap with HQ | Local Champion |
|---|---|---|---|---|---|
| | | | | hrs | |
| | | | | hrs | |
| | | | | hrs | |

---

## Follow-the-Sun Review Schedule

| Time Zone | Active Hours (Local) | Review Responsibility | Handoff To |
|---|---|---|---|
| | | PRs from [zone] waiting for review | [next zone] |
| | | | |
| | | | |

### Handoff Practice

At end of day, each engineer posts in team channel:
- PRs submitted and ready for review (priority order)
- PRs reviewed (with outcome: approved / changes requested)
- Decisions needing input from next time zone
- Blockers requiring synchronous discussion

---

## Asynchronous Review Standards

### PR Description Template for Agent-Generated Code

```
## Specification
[Link to specification/ticket]

## What this PR does
[One-paragraph summary]

## Design decisions
- Decision 1: [approach chosen] because [reasoning]
- Decision 2: [approach chosen] because [reasoning]

## Agent usage
- Tool used: [tool name]
- Specification method: [how the agent was directed]
- Areas of uncertainty: [where reviewer should look closely]

## Review requests
- [ ] Please check: [specific area 1]
- [ ] Please check: [specific area 2]

## Risk level
High / Medium / Low (per Chapter 9 risk classification)
```

### Review SLAs

| Priority | Turnaround Time | Escalation |
|---|---|---|
| Critical / Blocking | 4 hours | Escalate to next time zone if no reviewer available |
| Standard | 24 hours | Flag in standup if approaching deadline |
| Low priority | 48 hours | No escalation needed |

---

## Synchronous Time Allocation

### Precious synchronous overlap should be used for:
1. Design discussions for complex features
2. Review of contentious or high-risk PRs
3. Retrospectives and team health discussions
4. One-on-ones and performance conversations
5. Cross-geography calibration discussions

### Should NOT be used for:
- Status updates (use async)
- Routine PR reviews (use async)
- Tool demonstrations (use recordings)
- Documentation review (use async comments)

---

## Region-Specific Rollout Adaptation

### Region: _______________

| Factor | Headquarters | This Region | Adaptation Needed |
|---|---|---|---|
| Internet latency to AI tool | ms | ms | |
| AI tool availability | Full | Full / Partial / Restricted | |
| Local data regulations | | | |
| Language considerations | | | |
| Cultural feedback style | | | |
| Local champion identified | N/A | Yes / No | |
| Local pilot team identified | N/A | Yes / No | |

### Region-Specific Training Adjustments
- [ ] _________________________________
- [ ] _________________________________

### Regulatory Considerations
- [ ] _________________________________
- [ ] _________________________________

---

## Cross-Geography Governance

### Global (Same Everywhere)
- [ ] Code review checklist
- [ ] Accountability framework (RACI)
- [ ] Quality metrics and targets
- [ ] Career ladder and performance framework
- [ ] Tool configuration

### Local (May Vary by Region)
- [ ] Data handling rules (local privacy laws)
- [ ] Industry-specific compliance requirements
- [ ] Data residency requirements
- [ ] Local regulatory reporting
- [ ] Tool restrictions (if any)

---

## Communication Structure

### Daily Async Update Template

Each engineer posts at end of day:

```
**Specifications written today:**
- [spec name] — ready for review / in progress

**PRs ready for review:**
- [PR link] — [priority] — [specific review request]

**Decisions needing input:**
- [decision topic] — needed by [date]

**Blockers:**
- [blocker description] — who can help?
```

### Weekly Sync Meeting Agenda (30 min, all time zones)

1. Blockers and escalations (10 min)
2. Design discussion for upcoming complex work (15 min)
3. Adoption/quality metrics review (5 min)

### Monthly Cross-Geography Retrospective

- What is working well in each geography?
- What is each geography struggling with?
- What practices should be shared across geographies?
- What governance or process changes are needed?

---

## Knowledge Base Structure

Maintain a shared knowledge base (wiki/docs) with:

- [ ] **Specification patterns:** Effective specification templates by work type
- [ ] **Agent configuration:** Approved tool configurations and tips
- [ ] **Review techniques:** Common agent failure modes in our codebase
- [ ] **Retrospective learnings:** Consolidated findings from monthly retros
- [ ] **Regional guides:** Region-specific considerations and adaptations
- [ ] **FAQ:** Answers to common questions, updated monthly

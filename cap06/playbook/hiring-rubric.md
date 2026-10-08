# AI-Era Engineering Hiring Rubric

## Interview Scorecard

Score each dimension 1-4. A score below 2 on Code Review is a no-hire signal.

### Dimension 1: System Design with AI Constraints

| Score | Description |
|---|---|
| 4 | Produces a clear, well-reasoned architecture. Naturally identifies agent-suitable vs human-required components. Discusses specification quality, review strategy, and failure modes. Considers system-level implications of agent-generated code. |
| 3 | Solid architecture with minor gaps. Can identify agent delegation opportunities when prompted. Understands the tradeoffs of agent-assisted implementation. |
| 2 | Basic architecture that works but lacks depth. Limited ability to think about AI delegation. Treats agents as magic boxes or ignores the AI dimension. |
| 1 | Cannot produce a coherent system design. No understanding of how AI tools affect architecture decisions. |

**Score: ___** Notes: _________________________________

### Dimension 2: Code Review

| Score | Description |
|---|---|
| 4 | Catches significant issues including subtle ones (security, edge cases, architectural inconsistency). Prioritizes review time on high-risk changes. Provides specific, actionable feedback. Distinguishes between critical issues and preferences. |
| 3 | Catches most significant issues. Provides useful feedback. Good prioritization. May miss one subtle issue. |
| 2 | Catches obvious issues only. Feedback is vague or style-focused. Does not prioritize effectively. Misses subtle problems. |
| 1 | Cannot identify issues beyond formatting. Approves everything or rejects everything without substantive reasoning. |

**Score: ___** Notes: _________________________________

### Dimension 3: Specification and Decomposition

| Score | Description |
|---|---|
| 4 | Produces clear, implementable specifications from ambiguous requirements. Includes edge cases, security considerations, and testable acceptance criteria. Asks clarifying questions before specifying. Specifications are at the right level of abstraction for agent delegation. |
| 3 | Good specifications with most edge cases covered. Adequate acceptance criteria. May miss one or two considerations. |
| 2 | Basic specifications that cover the happy path. Missing edge cases and security considerations. Acceptance criteria are vague. |
| 1 | Cannot decompose an ambiguous requirement into clear tasks. Specifications are too vague for agent implementation or too detailed (pseudocode). |

**Score: ___** Notes: _________________________________

### Dimension 4: Debugging and Incident Response

| Score | Description |
|---|---|
| 4 | Methodically narrows problem space using available data. Identifies root cause in unfamiliar code. Proposes both a fix and a process improvement. Considers systemic causes (review, specification) beyond the code. |
| 3 | Good diagnostic approach. Identifies root cause with some guidance. Proposes a reasonable fix. Some consideration of process. |
| 2 | Can diagnose with significant guidance. Jumps to conclusions occasionally. Fix addresses symptom, not root cause. No process consideration. |
| 1 | Cannot reason about unfamiliar code. Random troubleshooting approach. No structured diagnostic methodology. |

**Score: ___** Notes: _________________________________

### Dimension 5: Behavioral and Culture Fit

| Score | Description |
|---|---|
| 4 | Demonstrates strong adaptability with specific examples. Shows sophisticated thinking about human-AI collaboration. Evidence of continuous learning and growth mindset. Strong communication and collaboration skills. |
| 3 | Good examples of adaptability. Reasonable approach to AI tools. Solid communication. |
| 2 | Limited adaptability examples. Surface-level engagement with AI tools. Communication is adequate but not strong. |
| 1 | Rigid approach to tools and processes. Resistant to change. Poor communication skills. |

**Score: ___** Notes: _________________________________

---

## Scoring Summary

| Dimension | Score | Weight | Weighted |
|---|---|---|---|
| System Design | /4 | 25% | |
| Code Review | /4 | 30% | |
| Specification | /4 | 20% | |
| Debugging | /4 | 15% | |
| Behavioral | /4 | 10% | |
| **Weighted Total** | | | **/4** |

### Decision Guide

| Weighted Score | Recommendation |
|---|---|
| 3.5 - 4.0 | Strong hire |
| 3.0 - 3.4 | Hire |
| 2.5 - 2.9 | Borderline — discuss as panel |
| Below 2.5 | No hire |

**Hard gate:** Code Review score below 2 = No hire regardless of total.

---

## Interviewer Calibration Notes

Before each hiring cycle, calibrate with your panel:
- Review sample PRs together and agree on scoring criteria
- Score the same candidate independently, then compare
- Discuss scoring disagreements to build shared understanding
- Update this rubric based on what you learn from new hires' actual performance

---

## AI Tool Fluency Assessment (Signal, Not Gate)

Rate the candidate's AI tool engagement:

- [ ] **Systematic user:** Has structured workflows for AI-assisted development, can articulate when and how to delegate to agents
- [ ] **Active user:** Uses AI tools regularly, has developed some personal practices
- [ ] **Occasional user:** Has tried AI tools but no systematic approach
- [ ] **Non-user but adaptable:** Has not used AI tools but demonstrates rapid learning and openness
- [ ] **Resistant:** Actively opposed to AI tools with no willingness to engage

Non-user but adaptable is acceptable. Resistant is a concern worth probing.

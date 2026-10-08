# Performance Calibration Guide for AI-Native Teams

## Five-Dimension Evaluation Framework

### Dimension 1: Decision Quality (Weight: 30%)

| Rating | Description |
|---|---|
| Excelling | Makes architectural decisions that prove sound over time. Identifies risks others miss. Specifications consistently produce correct agent output. Tradeoff reasoning is clear and well-communicated. |
| Performing | Makes sound technical decisions in their domain. Specifications usually produce correct agent output. Good at identifying common risks. |
| Developing | Decisions sometimes require correction. Specifications need refinement. Learning to identify risks and articulate tradeoffs. |

**Evidence to gather:**
- [ ] 3+ significant technical decisions and their outcomes
- [ ] Specification success rate (agent output accepted vs. rejected)
- [ ] Examples of risk identification before problems manifested
- [ ] Quality of tradeoff reasoning in design discussions

### Dimension 2: Review Effectiveness (Weight: 25%)

| Rating | Description |
|---|---|
| Excelling | Consistently catches issues others miss. Zero or near-zero escaped defects in reviewed code. Sets review standards for the team. Review comments are specific, actionable, and educational. |
| Performing | Catches most significant issues. Low escaped defect rate. Provides useful, specific review feedback. Good review turnaround time. |
| Developing | Catches obvious issues. Some escaped defects. Review comments sometimes vague. Building review skills and speed. |

**Evidence to gather:**
- [ ] Specific issues caught in review that others would have missed
- [ ] Escaped defect rate for code they reviewed
- [ ] Review comment quality (specific, actionable examples)
- [ ] Review turnaround time and consistency

### Dimension 3: Leverage and Productivity (Weight: 20%)

| Rating | Description |
|---|---|
| Excelling | Delivers significantly above team expectations given work complexity. Uses AI tools optimally for their work context. Unblocks others regularly. Time allocation well-balanced. |
| Performing | Delivers at the pace the team needs. Uses AI tools appropriately. Good time management between implementation, review, and design. |
| Developing | Delivery pace needs improvement. AI tool usage could be more effective. Time allocation sometimes unbalanced. |

**Evidence to gather:**
- [ ] Features delivered relative to scope and complexity (NOT absolute count)
- [ ] AI tool usage patterns (effective? appropriate?)
- [ ] Time allocation balance (implementation vs. review vs. design)
- [ ] Examples of unblocking teammates

**AI Leverage Correction:** Before rating, ask: "Given the TYPE of work this engineer does, is this delivery pace appropriate? Would this rating change if they were on a different workstream?"

### Dimension 4: Growth and Development (Weight: 15%)

| Rating | Description |
|---|---|
| Excelling | Clear trajectory toward next level. Acquiring new skills proactively. Taking on challenges beyond current scope. Mentoring others effectively. |
| Performing | Growing steadily in role. Learning new skills as needed. Handling increased complexity. |
| Developing | Growth pace needs acceleration. Staying in comfort zone. Not yet developing beyond current level requirements. |

**Evidence to gather:**
- [ ] New skills acquired in the review period
- [ ] Increased scope or complexity of work
- [ ] Mentoring contributions (for senior+ engineers)
- [ ] Self-directed learning and experimentation

### Dimension 5: Collaboration and Influence (Weight: 10%)

| Rating | Description |
|---|---|
| Excelling | Makes the team measurably better. Contributes to team practices and standards. Shares knowledge proactively. Recognized influence beyond the team. |
| Performing | Good teammate. Contributes to team health. Shares knowledge when asked. Collaborative in cross-team work. |
| Developing | Works effectively but mostly independently. Could contribute more to team practices and knowledge sharing. |

**Evidence to gather:**
- [ ] Contributions to team practices, standards, or tooling
- [ ] Knowledge sharing examples
- [ ] Cross-team collaboration evidence
- [ ] Impact on teammates' effectiveness

---

## Calibration Meeting Agenda

### Pre-Meeting (Each Manager Prepares)

For each engineer, prepare:
1. One-paragraph summary covering all five dimensions
2. Proposed rating (Exceeds / Meets / Below)
3. Specific evidence for the two highest and two lowest dimensions
4. AI leverage context: what type of work does this engineer do?

### Meeting Flow (2-3 hours for a group of 15-20 engineers)

1. **Align on criteria** (10 min)
   - Review the five dimensions and rating scales
   - Confirm all managers are evaluating on the same basis

2. **Present proposed "Exceeds" ratings** (30 min)
   - Each manager presents their "Exceeds" engineers
   - Panel challenges evidence, not conclusions
   - Apply AI leverage correction
   - Agree on final set of "Exceeds" ratings

3. **Present proposed "Below" ratings** (20 min)
   - Same process
   - Extra scrutiny: is this a performance issue or a work-type issue?

4. **Review "Meets" population** (45 min)
   - Look for engineers who should be moved up or down
   - Compare across teams for consistency
   - Check for bias patterns (volume bias, adoption bias)

5. **Final calibration** (15 min)
   - Review the full distribution
   - Confirm the relative ordering makes sense
   - Identify any remaining inconsistencies

### Bias Checks During Calibration

- [ ] **Volume bias:** Are we rating engineers higher because they produced more agent-assisted output?
- [ ] **Adoption bias:** Are we rating engineers lower because they use AI tools less?
- [ ] **Work-type bias:** Are we comparing engineers on different workstreams without adjusting?
- [ ] **Recency bias:** Are we over-weighting recent performance vs. the full review period?

---

## Feedback Conversation Template

"Based on our evaluation across five dimensions, here is where you stand and what I would like to see in the next cycle:

**Decision Quality** [Developing/Performing/Excelling]
- Evidence: [specific example]
- Growth focus: [what to work on]

**Review Effectiveness** [Developing/Performing/Excelling]
- Evidence: [specific example]
- Growth focus: [what to work on]

**Leverage and Productivity** [Developing/Performing/Excelling]
- Evidence: [specific example]
- Growth focus: [what to work on]

**Growth and Development** [Developing/Performing/Excelling]
- Evidence: [specific example]
- Growth focus: [what to work on]

**Collaboration and Influence** [Developing/Performing/Excelling]
- Evidence: [specific example]
- Growth focus: [what to work on]

**Overall rating:** [Exceeds / Meets / Below]

**Top priority for next cycle:**
_________________________________

**Career ladder connection:**
Reference the relevant criteria from the AI-era career ladder (Chapter 7) that connect this feedback to the engineer's growth path."

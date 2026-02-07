# Metrics are for decisions, not judgment

## One-line reason
Metrics should reduce uncertainty and improve decisions; when used for judgment, they get gamed and stop reflecting reality.

---

## The principle
Engineering metrics exist to support **better decisions** at every level of the system:

- Teams decide what to improve next (reduce wait time, fix flaky tests, simplify deployments).
- Leaders decide where to invest (platform improvements, staffing, risk reduction).
- Security and risk partners decide what controls should be automated vs. gated.

When metrics become **a scorecard**, people naturally optimize for the number rather than the outcome. This is not a cultural failure—it’s a predictable system behavior.

---

## Why this matters
### 1) Goodhart’s Law shows up fast in software delivery
When a measure becomes a target, it stops being a good measure.

Examples:
- Measuring “velocity” increases story points, not value delivered.
- Measuring “deployments per week” can drive risky releases if quality signals are ignored.
- Measuring “vulnerabilities closed” can incentivize reclassification rather than remediation.

### 2) Trust is a prerequisite for good data
If teams believe metrics will be used against them, they will:
- stop reporting accurately,
- spend time explaining numbers rather than improving the system,
- optimize locally and hide systemic constraints.

### 3) Leaders need system signals, not performance surveillance
At enterprise scale, most delivery problems are **system constraints**:
- long environment provisioning times,
- manual approvals,
- brittle integration test suites,
- unclear service ownership,
- slow security feedback loops.

Metrics should surface constraints so leaders can remove them.

---

## What to measure (and what not to)
### Measure (decision-support signals)
**Flow**
- Lead time and cycle time trends
- WIP and queue time patterns
- Deployment frequency (as a trend, not a quota)

**Quality**
- Change failure rate and rollback rates
- MTTR and incident trends
- Test flakiness and build stability

**Security**
- Time-to-remediate critical vulnerabilities
- Security scan coverage trends
- Risk aging (how long known issues remain open)

**Enablement**
- Pipeline wait time (queue + run time)
- Environment provisioning time
- Developer toil indicators (repeated manual steps, ticket-driven access)

These help answer: *“Where is the constraint, and what investment removes it?”*

### Avoid (high-gaming-risk metrics)
- Individual productivity scoring
- Team rankings or league tables
- Story points as performance management
- “Percent utilization” as an output metric
- Compliance checklists without runtime feedback

These tend to incentivize optics over outcomes.

---

## How leaders and teams should use this
### Teams (local improvement)
Teams should use metrics to:
- identify their biggest bottleneck,
- run experiments (e.g., reduce flaky tests, remove manual steps),
- observe whether the change improved flow and stability.

A good team question:
> “What is the next most valuable constraint to remove?”

### Leaders (system investment)
Leaders should use metrics to:
- see patterns across teams and portfolios,
- distinguish local problems from systemic ones,
- prioritize platform work that improves many teams at once.

A good leadership question:
> “What constraint is hurting multiple teams, and what investment removes it?”

### Security / Risk partners (secure-by-default)
Security signals should:
- arrive early (in CI), not late (in audits),
- be actionable, not just compliant,
- be measured as a feedback loop, not a gate.

A good risk question:
> “How can we shorten time-to-detect and time-to-remediate without slowing delivery?”

---

## Anti-patterns to avoid
1. **Metrics as punishment**
   - Outcome: data becomes unreliable and improvements stall.

2. **Single-number productivity**
   - Outcome: teams optimize one dimension and break others.

3. **Local optimization without system context**
   - Outcome: one team improves while the portfolio stays stuck.

4. **Dashboards without decisions**
   - Outcome: metrics theater (reporting replaces improvement).

5. **Security as a late-stage gate**
   - Outcome: teams treat security as external friction, not built-in quality.

---

## Practical “metric governance” rules
These lightweight rules prevent misuse:

- Every metric must have a **decision owner** (“who uses this to decide something?”).
- Every dashboard should list **questions it answers**.
- Avoid team rankings; show **distributions and trends** instead.
- Combine signals (flow + quality + security) to prevent “speed at any cost”.
- Review metrics periodically and retire those that no longer drive decisions.

---

## What good looks like
You know metrics are working when:
- teams can name their current constraint,
- leaders can fund constraint removal (platform, tooling, policy),
- security risk trends improve without delivery slowing down,
- the conversation shifts from blame to system design.
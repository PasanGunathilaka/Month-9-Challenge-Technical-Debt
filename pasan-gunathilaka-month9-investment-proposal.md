# Month 9 — Executive Investment Proposal: Technical Debt Reduction

**Prepared by:** Pasan Gunathilaka  
**Track:** Tech Lead  
**Deliverable:** 4 of 4 — Executive Investment Proposal (25 points)  
**Decision requested:** Approve protected engineering capacity for a 12-month technical debt program.

> **Scenario-based proposal, not actual company financial reporting.** The figures and platform names below are illustrative training assumptions. They must be validated with real Finance, Product and Engineering records before being sent as real organizational claims.

## 1. One-page executive summary (5 points)

### The request

Approve **20% of existing engineering capacity** for a 12-month debt-reduction program. For a hypothetical 6-engineer team, this is **192 hours per month / 2,304 hours annually**. No additional headcount is requested. Authorize the first-quarter milestones, monthly reporting and a quarterly stop/go review.

### Why this matters to the business

The legacy workforce platform has accumulated technical debt that makes features slower to deliver, increases the risk of onboarding/release incidents and exposes the organization to avoidable security and reliability problems.

| Business headline | Scenario estimate |
|---|---:|
| Identified technical debt | 10 items; 2 Critical and 4 High |
| Avoidable effort from the 5 most costly items | **124 engineering hours/month** |
| Annual economic exposure from top-five carry + expected risk | **$97,800** |
| Focused investment to remediate top five | **700 hours / $35,000** |
| Conservative annual benefit *once all five are completed* | **$63,780** |
| Steady-state payback after completion | **6.6 months** |
| Estimated calendar break-even from program launch | **Month 12**, assuming phased delivery as planned |

**Executive outcome:** Lower avoidable operating costs, fewer preventable incidents and faster delivery of customer-facing improvements. Benefits are primarily recovered engineering capacity and reduced *expected* risk, not guaranteed cash savings.

## 2. The business case (10 points)

### Current state and pain points

- **Slow changes:** Duplicated business rules and fragile integrations add repeated implementation and retesting work.
- **Service disruption:** Synchronous workflows allow downstream outages to affect employee onboarding.
- **Security exposure:** Weak automated tenant-boundary coverage increases the chance of authorization defects escaping to production.
- **Release friction:** Manual deployments and rollback steps delay safe product delivery.
- **Poor reporting performance:** Expensive reports compete with the transactional database and affect user experience.

### Cost of inaction

For the **top five** items only, expected annual exposure is **$74,400 in carrying effort** plus **$23,400 in expected incident-risk loss**, or **$97,800/year**. If carrying effort increases by 10% annually, this rises to an estimated **$105,240 in Year 2** and **$113,424 in Year 3**, holding risk flat. These are modeling assumptions, not audited expenditures.

### Investment and expected returns

- **Top-five dedicated remediation:** 700 engineering hours × $50/hour = **$35,000 equivalent capacity**.
- **All 10 known remediation tasks:** 1,080 hours × $50/hour = **$54,000 equivalent capacity**.
- **Entire annual protected debt-management budget:** 2,304 hours × $50/hour = **$115,200 equivalent capacity**. This includes remediation, preventive engineering, measurement/governance and emergent risk work. It is **reallocated existing staff time**, not a separate cash payment.
- **Conservative top-five model:** recover 70% of carrying effort plus avoid 50% of expected risk loss = **$63,780 per full year after implementation**.
- **Steady-state top-five ROI:** ($63,780 − $35,000) / $35,000 = **82.2%** for a full post-remediation year. This is an *economic-capacity ROI*, not a forecast of recognized financial profit.
- **First 12 months from kickoff:** Because improvements arrive in stages, modeled realized top-five benefit is only **$38,940**, with modeled break-even in **month 12**. Avoid presenting the full $63,780 as realized in Year 1.

**Investment boundary:** The quantified ROI above compares the **$35,000 top-five remediation work** against the **top-five benefits**. It does not claim that those benefits justify the entire **$115,200** annual capacity allocation by themselves. The remaining allocation supports six other stated purposes/items; those results must be evaluated separately.

### Risk of not acting

Potential consequences include repeated onboarding failures, slow release recovery, increasing maintenance work, weakened tenant-isolation confidence and poor reporting experience. These risks may affect customer retention, delivery credibility and team capacity, although exact commercial impact has not been verified.

## 3. Proposal details (5 points)

### Specific approval request

1. Protect **20% of team engineering capacity** for 12 months as a tracked portfolio allocation; retain 80% for product priorities and ordinary operations.
2. Authorize **Q1 scope (280 hours / $14,000 equivalent capacity)** covering automated deploy/rollback (TD-04), tenant-boundary integration tests (TD-03) and architecture ownership documentation (TD-09).
3. Assign accountable owners from Engineering, QA, Platform/DevOps and Product. Have Finance validate cost rates and expected-risk assumptions.
4. Approve a monthly KPI readout and a quarterly continue/change/stop decision.

### Timeline and milestones

| Period | Business result | Debt items | Planned fix effort |
|---|---|---|---:|
| First 90 days (Q1) | Safer releases, stronger tenant-access testing, clear ownership | TD-04, TD-03, TD-09 | 280 hours |
| Months 4–6 (Q2) | More reliable onboarding and faster workflow changes | TD-01, TD-02, TD-10 | 344 hours |
| Months 7–9 (Q3) | Faster reports and earlier incident detection | TD-05, TD-08 | 280 hours |
| Months 10–12 (Q4) | Safer legacy code and stable automated test results | TD-06, TD-07 | 176 hours |
| **Total** | | **All 10** | **1,080 hours** |

### Quick wins in the first 90 days

- **By end of M2:** Automate standard deployment and document/test rollback. Business value: reduce release delays and recovery effort.
- **By end of M3:** Add repeatable tenant-isolation integration tests around the highest-risk access paths. Business value: reduce likelihood of exposing one tenant's data to another.
- **By end of M3:** Publish system owners and architecture decision index. Business value: faster incident routing and fewer handover delays.

### Controls and executive visibility

Report each month: committed vs. actual debt hours, high-risk backlog, change failure rate, recovery time, delivery lead-time trend, incident exposure and realized (not just forecast) hours saved. Review with Engineering/Product monthly and executives quarterly. Reassess or stop a remediation effort if the benefit does not justify the investment.

## 4. Appendix: supporting data (5 points)

### A. Top-five supporting calculations

| ID | Issue | Fix hours | Extra hrs/month | Expected risk/year | Full monthly benefit after fix (base case) |
|---|---|---:|---:|---:|---:|
| TD-01 | Duplicate business rules | 120 | 30 | $1,200 | $1,100.00 |
| TD-02 | Coupled onboarding services | 160 | 24 | $7,200 | $1,140.00 |
| TD-03 | Authorization test gaps | 140 | 26 | $6,000 | $1,160.00 |
| TD-04 | Manual deployments | 100 | 20 | $4,000 | $866.67 |
| TD-05 | Reporting DB contention | 180 | 24 | $5,000 | $1,048.33 |
| **Total** | | **700** | **124** | **$23,400** | **$5,315/month** |

**Assumptions:** $50 loaded hourly rate; 70% of carry hours recoverable; 50% of expected incident loss avoidable; phased item completions at M2/M3/M4/M6/M8. For methodology, trend and sensitivity, see Deliverable 2.

### B. Technical design follow-ups

- **TD-02:** Define event contracts, idempotency, retry/dead-letter policy, rollout strategy and failure simulation.
- **TD-03:** Introduce isolated tenant-pair fixtures and negative authorization integration tests in CI.
- **TD-04:** Add immutable release artifacts, one-click rollback and a rehearsed recovery runbook.
- **TD-05:** Compare indexed queries, caching and read-model/reporting isolation against a realistic p95 latency baseline.

### C. Frequently asked executive questions

**Q: Why not spend all engineering capacity on new features?**  
A: Unmanaged debt reduces the team's ability to ship future features. The proposal preserves 80% of capacity for planned delivery while protecting a small, visible investment in reliability and speed.

**Q: Is this an additional $115,200 cash budget?**  
A: No. It is the illustrative fully loaded value of time reallocated from an existing 6-person team. Any actual funding change needs separate Finance approval.

**Q: Why is the payback 6.6 months but break-even in month 12?**  
A: 6.6 months assumes every top-five fix is already complete. Real implementation is phased through month 8, so benefits arrive gradually; modeled cumulative benefit exceeds the $35,000 repair effort around month 12.

**Q: Are the savings guaranteed?**  
A: No. Carry-hours recovery and avoided incidents are estimated economic benefits. Validate with telemetry, incident reviews and actual work sampling.

**Q: What if a customer feature becomes urgent?**  
A: Exceptions are allowed, but logged; Product and Engineering re-plan the next sprint and avoid repeatedly eliminating the debt allocation.

**Q: When do we stop?**  
A: At quarterly reviews if measured savings fail, critical risks change, or the business case no longer supports the sequence. Individual items close only when evidence proves the outcome.

### D. Supporting artifacts

1. `pasan-gunathilaka-month9-debt-inventory.md` — complete 10-item register and risk hot spots.
2. `pasan-gunathilaka-month9-cost-model.md` — formulas, trend, sensitivity, staged ROI.
3. `pasan-gunathilaka-month9-reduction-roadmap.md` — scoring, sequencing, resources and metrics.

**Decision statement for leadership:** Approve the protected 20% capacity allocation and Q1 scope, with monthly measurement and quarterly review. This targets measurable delivery friction and production risk while preserving product delivery capacity.

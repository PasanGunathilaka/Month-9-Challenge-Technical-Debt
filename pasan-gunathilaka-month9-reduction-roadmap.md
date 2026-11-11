# Month 9 — 12-Month Technical Debt Reduction Roadmap

**Participant:** Pasan Gunathilaka  
**Track:** Tech Lead  
**Deliverable:** 3 of 4 — Debt Reduction Roadmap (25 points)  
**System:** Hypothetical Legacy Workforce Management Platform (LWMP)

> **Illustrative scenario:** All priorities, hours, dates and metric baselines are sample assumptions. Substitute real backlog and team commitments before putting this into operation.

## 1. Strategic objective

Within 12 months, reduce avoidable engineering toil, protect tenant security, shorten release cycles and improve reliability **without stopping new feature delivery**. Do not try to eliminate every form of technical debt. Tackle the items with the highest current impact first, then prevent new debt from accumulating unnoticed.

## 2. Prioritization framework (5 points)

Each factor is scored from **1 (low) to 5 (high)**. For **Engineering Cost**, a higher score means *more ongoing burden from keeping the debt*, not a higher remediation price. Repair effort is evaluated separately during sequencing.

**Priority score (out of 5) = 0.30 × Business impact + 0.25 × Engineering carrying burden + 0.25 × Risk + 0.20 × Strategic fit.**

| ID | Business 30% | Carry burden 25% | Risk 25% | Fit 20% | Weighted score | Decision |
|---|---:|---:|---:|---:|---:|---|
| TD-02 | 5 | 4 | 5 | 5 | **4.75** | Priority 1; critical dependency failure |
| TD-03 | 5 | 4 | 5 | 5 | **4.75** | Priority 1; tenant-security tests |
| TD-01 | 5 | 5 | 3 | 4 | **4.30** | Priority 2; broad change impact |
| TD-05 | 4 | 4 | 5 | 4 | **4.25** | Priority 2; performance/customer impact |
| TD-04 | 4 | 4 | 4 | 5 | **4.20** | Priority 1 enabler; safer delivery |
| TD-08 | 4 | 3 | 4 | 4 | 3.75 | Priority 3; faster detection/diagnosis |
| TD-07 | 3 | 3 | 4 | 4 | 3.45 | Priority 3; stabilize automation |
| TD-06 | 3 | 3 | 4 | 3 | 3.25 | Priority 3; targeted code safety |
| TD-10 | 2 | 2 | 3 | 3 | 2.45 | Priority 4; controlled modernization |
| TD-09 | 2 | 2 | 2 | 3 | 2.20 | Priority 4; quick enabler |

**Trade-off:** TD-04 is scheduled before TD-02 even with a slightly lower score because repeatable deployment and rollback reduce risk when changing a critical onboarding flow. TD-09 is also brought forward because clear ownership and decision records improve future execution at low cost. Scores guide decisions; prerequisites and risk exposure can override rank, with written justification.

## 3. 12-month roadmap (10 points)

**Start:** Month 1 (relative to approval). Dates are relative months rather than promising an unapproved calendar date.

| Quarter | Months | Target debt items | Fix hours | Outcomes / acceptance evidence | Dependencies |
|---|---|---|---:|---|---|
| Q1 — Stabilize delivery and security | M1–M3 | TD-04 (100h), TD-03 (140h), TD-09 (40h) | **280** | Repeatable deploy/rollback by M2; tenant-boundary integration suite by M3; ownership map/ADR index | Environment access, test fixtures, DevOps support |
| Q2 — Reduce coupling and duplicated work | M4–M6 | TD-01 (120h), TD-02 (160h), TD-10 (64h) | **344** | One shared rules implementation by M4; idempotent async onboarding by M6; updated validator in supported routes | Q1 test/deploy controls; event contracts, retries and dead-letter handling |
| Q3 — Improve performance and detection | M7–M9 | TD-05 (180h), TD-08 (100h) | **280** | Reporting isolated/cached and verified by M8; actionable tracing/alerts by M9 | Safe database migration, tracing standards, performance baselines |
| Q4 — Reduce remaining quality friction | M10–M12 | TD-06 (96h), TD-07 (80h) | **176** | Safe parameterized data paths and stabilized E2E suite; year-end remeasurement | Regression tests, service ownership, stable CI infrastructure |
| **Total** | | **All 10 debt items** | **1,080** | | |

### Quarter-specific checkpoints

- **End Q1:** Demonstrate a rollback drill; verify tenant isolation tests pass; review incident trend and early capacity recovery.
- **End Q2:** Run a failure simulation on downstream onboarding services; verify retry, idempotency and dead-letter handling; track duplicate-code removal.
- **End Q3:** Load-test reporting at agreed workload; show p95 trend; verify distributed traces and response playbooks.
- **End Q4:** Verify flaky-test improvement and validation refactors; reassess the remaining risk register and establish next-year priorities.

### Definition of done for each item

A debt item can close only after code review, automated tests, performance/security checks where relevant, approved rollback plan, updated documentation and at least 30 days of post-release metric monitoring. If outcomes do not improve, reopen or re-scope the item.

## 4. Capacity allocation and trade-offs (5 points)

**Illustrative available engineering capacity:** 6 engineers × 160 hours/month = **960 hours/month**. Reserve **20% = 192 hours/month**, or **2,304 hours/year**, for technical debt and debt prevention. Keep **80%** for product delivery/operational commitments, subject to incident needs.

| Annual use of reserved capacity | Hours | Percentage of debt capacity |
|---|---:|---:|
| Planned 10-item remediation | **1,080** | 46.9% |
| Preventive engineering (standards, guardrails, automated checks) | 360 | 15.6% |
| Measurement, evidence capture, debt reviews and enablement | 288 | 12.5% |
| Newly discovered/high-priority debt and incident follow-up reserve | 576 | 25.0% |
| **Total debt-management allocation** | **2,304** | **100%** |

**Quarterly debt-capacity budget:** 576 hours each quarter. Planned fix commitments are Q1 280h, Q2 344h, Q3 280h and Q4 176h. The remainder each quarter supports prevention, measurement and emergent debt (not unplanned feature promises).

**Integration with feature work:** Product and Engineering plan the 80/20 split at the start of each sprint; bundle related debt removal with touching features when safe, but track dedicated hours separately to avoid hiding cost. Do not open major high-risk refactors during release freezes.

**Flexibility:** Critical security incidents can temporarily override the 80/20 split; record the exception, notify Product, and rebalance the following sprint. Re-score the backlog monthly and re-plan quarterly if risk, capacity or measured benefit changes.

## 5. Success metrics (5 points)

Baselines and targets below are illustrative. Confirm with real telemetry during M1 before setting public commitments.

| Metric | Type | Sample baseline | Target by M12 | Source / cadence |
|---|---|---|---|---|
| Carry effort across all 10 known items | Lagging | 184 hours/month | ≤90 hours/month | Time samples; monthly |
| Top-five avoidable carry effort | Lagging | 124 hours/month | ≤37 hours/month | Time samples; monthly |
| Change failure rate | Lagging | 18% | ≤8% | CI/CD + incidents; monthly |
| Tenant-permission escaped defects | Lagging | 4/quarter | 0/quarter | Bug and incident register; quarterly |
| Reporting p95 latency on agreed workload | Lagging | 8 seconds | <3 seconds | APM/load tests; monthly |
| Mean time to recover (MTTR) | Lagging | 120 minutes | <45 minutes | Incident data; monthly |
| Manual deployment effort per release | Leading | 3 hours | ≤30 minutes | Deployment logs; monthly |
| Flaky E2E failure rate | Leading | 12% | <3% | Test history; biweekly |
| High-risk debt items with named owner and evidence | Leading | 50% | 100% | Debt register; monthly |
| Planned debt stories meeting done criteria | Leading | Not measured | ≥85% per quarter | Sprint/quarter review |

**Reporting cadence:** Team reviews the board every two weeks; Tech Lead shares a one-page trend report monthly; leadership gets a quarterly debt-investment review with cost, realized benefits, milestone progress, risk and explicit decisions needed.

## 6. Risks and mitigations

| Roadmap risk | Mitigation |
|---|---|
| Async migration introduces duplicate or lost events | Idempotency keys, outbox where needed, retries, dead-letter queue and gradual rollout |
| Test fixtures miss cross-tenant access cases | Negative tests, representative tenant pairs and security review |
| Report isolation changes data freshness | Agree acceptable freshness with product stakeholders and test reconciliation |
| Urgent features consume debt allocation | Track allocation visibly, escalate repeated exceptions and re-plan |
| Claimed savings do not materialize | Measure before/after; stop or revise weak-return initiatives |

**Approval requested:** Product Manager and Engineering Manager agree to the 20% capacity policy, the first quarter's acceptance criteria and monthly metric reporting. Finance validates the blended rate for the business case.

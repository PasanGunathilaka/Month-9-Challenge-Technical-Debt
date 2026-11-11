# Month 9 — Technical Debt Cost Model

**Participant:** Pasan Gunathilaka  
**Track:** Tech Lead  
**Deliverable:** 2 of 4 — Debt Cost Model (25 points)  
**System:** Hypothetical Legacy Workforce Management Platform (LWMP)

> **Training estimates only.** Figures are consistent with the companion inventory, roadmap and investment proposal. They are not BISTEC financials or verified project measurements. Validate all assumptions before real executive use.

## 1. Cost framework (5 points)

| Component | Simple meaning | Calculation | Treatment |
|---|---|---|---|
| **Fix cost** | One-time engineering effort to remove debt | Remediation hours × $50/hour | Investment, not annual carrying burden |
| **Carry cost** | Extra effort *each month* while debt remains | Avoidable hours/month × $50/hour | Recurring time/capacity exposure |
| **Opportunity cost** | Roadmap work delayed because engineers deal with debt | Features/sprints delayed, or independently validated lost value | Presented as delivery delay, **not double-counted** as money |
| **Risk cost** | Expected annual loss from incidents attributable to debt | Annual incident probability × impact per incident | Expected-value exposure; not a guaranteed cash expense |

**Illustrative blended fully loaded engineering rate: $50/hour.** It includes salary, overhead and tooling; it is not an employee's pay rate. Monetary values are **USD**.

**Measurement:** Time tracking over 8 weeks, incident reviews over 12 months, pipeline logs and delivery planning reviews. For this assignment, all measurements are scenario assumptions pending real evidence. Probability × severity is an annual single-event approximation; multiple incidents would require a frequency-based model.

**Important rule:** Do not add opportunity cost in dollars when it already represents the same engineering hours counted in carry cost. Likewise, exclude incident-recovery hours from carry hours when those hours are represented by expected risk loss. This avoids misleading ROI.

## 2. Top-five calculations (10 points)

| ID | Fix hours | Fix cost | Extra hours/mo | Carry cost/mo | Carry cost/yr | Risk probability × impact/yr | Risk cost/yr |
|---|---:|---:|---:|---:|---:|---|---:|
| TD-01 | 120 | $6,000 | 30 | $1,500 | $18,000 | 40% × $3,000 | $1,200 |
| TD-02 | 160 | $8,000 | 24 | $1,200 | $14,400 | 60% × $12,000 | $7,200 |
| TD-03 | 140 | $7,000 | 26 | $1,300 | $15,600 | 40% × $15,000 | $6,000 |
| TD-04 | 100 | $5,000 | 20 | $1,000 | $12,000 | 50% × $8,000 | $4,000 |
| TD-05 | 180 | $9,000 | 24 | $1,200 | $14,400 | 50% × $10,000 | $5,000 |
| **Total** | **700** | **$35,000** | **124** | **$6,200** | **$74,400** | | **$23,400** |

### Opportunity impact (not independently monetized)

| ID | Potential business work delayed or reduced |
|---|---|
| TD-01 | New onboarding policy changes require duplicate implementation and testing |
| TD-02 | New onboarding integrations wait on fragile synchronous flows |
| TD-03 | Security-sensitive tenant features require extra manual verification |
| TD-04 | Frequent releases, hotfixes and experimentation become slower |
| TD-05 | Reporting enhancements compete with transactional workload and slow delivery |

**Baseline annual economic exposure if top five are ignored:** $74,400 carry + $23,400 expected risk = **$97,800/year**. This is an estimate of capacity/risk exposure, *not* a guaranteed cash saving or extra invoice. The $35,000 one-time fix cost is the investment needed to reduce exposure; it is not part of the annual cost of inaction.

**Wider inventory:** All 10 items are estimated to create 184 avoidable hours/month ($110,400/year in carrying effort). Risk is priced for the top five only, so the organization-wide risk estimate is incomplete.

## 3. Trend analysis and no-action scenario (5 points)

Assume carrying work grows **10% per year** if debt is not addressed, with risk exposure held flat for a conservative baseline.

| Period | Top-five carry cost | Top-five expected risk | Total annual exposure |
|---|---:|---:|---:|
| Year 1 | $74,400 | $23,400 | **$97,800** |
| Year 2 | $81,840 | $23,400 | **$105,240** |
| Year 3 | $90,024 | $23,400 | **$113,424** |

The increase reflects more time needed to change and support growing systems, not an assumed increase in developer salary.

### Break-even definition

- **Steady-state payback:** One-time fix investment ÷ monthly benefit once **all five fixes are in production**.
- **Calendar break-even:** Month when cumulative *realized* benefits from phased deliveries exceed $35,000. Benefits begin only *after* each fix completes.

## 4. ROI model (5 points)

Conservative effectiveness assumptions for completed fixes:

- **70%** of the modeled 124 carry hours/month is actually recovered.
- **50%** of expected incident-risk loss is avoided.
- Retained 30% carry cost acknowledges residual complexity; the model does not assume all debt disappears.

| Calculation | Result |
|---|---:|
| Carry saving/year = $74,400 × 70% | **$52,080** |
| Expected risk reduction/year = $23,400 × 50% | **$11,700** |
| **Steady-state annual economic benefit** | **$63,780** |
| One-time top-five remediation investment | **$35,000** |
| Monthly benefit when fully live = $63,780 ÷ 12 | **$5,315** |
| Steady-state payback = $35,000 ÷ $5,315 | **6.6 months** |
| First complete *steady-state year* net benefit | **$28,780** |
| First complete steady-state year ROI = $28,780 ÷ $35,000 | **82.2%** |

**Capacity, not guaranteed cash:** Much of the benefit is engineering time freed for planned features and reliability work. It is only a cash saving if staff costs or outside spend actually decrease.

### Time-phased realization (roadmap-aligned)

The roadmap assumes completions at **TD-04 month 2**, **TD-03 month 3**, **TD-01 month 4**, **TD-02 month 6** and **TD-05 month 8**. Full monthly benefit for each begins in the *next* month.

| ID | Completion | Estimated full monthly benefit | Benefit realized in first 12 months |
|---|---|---:|---:|
| TD-04 | End M2 | $866.67 | $8,666.67 |
| TD-03 | End M3 | $1,160.00 | $10,440.00 |
| TD-01 | End M4 | $1,100.00 | $8,800.00 |
| TD-02 | End M6 | $1,140.00 | $6,840.00 |
| TD-05 | End M8 | $1,048.33 | $4,193.33 |
| **Total** | | **$5,315.00** | **$38,940.00** |

**Calendar break-even is approximately month 12** from kickoff: cumulative modeled benefit is $33,625 at the end of month 11 and $38,940 at the end of month 12, versus $35,000 of top-five fix effort. This assumes on-time delivery and benefit realization; it excludes other program costs and benefits.

### Sensitivity analysis

All rows assume 50% risk-cost reduction and an unchanged $35,000 fix cost.

| Recovered carry cost | Annual economic benefit | Steady-state payback | Annual steady-state ROI |
|---:|---:|---:|---:|
| 50% | $48,900 | 8.6 months | 39.7% |
| **70% (base)** | **$63,780** | **6.6 months** | **82.2%** |
| 90% | $78,660 | 5.3 months | 124.7% |

**Control against optimism:** Run a 30-day post-fix measurement window for each item. If documented carry savings are under 50% of the plan, pause discretionary next steps and revisit effort estimates.

## 5. Sources, uncertainty and audit trail

**Sample source map to populate with real data:** Jira/Azure DevOps tickets (cycle time and affected changes), pipeline logs (deployment effort), production alerts and incidents (risk estimates), time logs (carry hours), finance rate card (loaded hourly cost), roadmap planning (feature delays).

**Confidence:** Low for all illustrative numbers. For actual reporting, classify each number as Measured / Estimated / Assumed, record a date range and have Finance, Product and Engineering validate costs independently.

**Business interpretation:** Remediation does not promise zero incidents; it buys lower recurring effort and fewer avoidable disruptions, while preserving capacity for new features.

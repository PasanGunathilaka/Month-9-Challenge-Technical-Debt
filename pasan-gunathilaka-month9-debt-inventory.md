# Month 9 — Technical Debt Inventory

**Participant:** Pasan Gunathilaka  
**Track:** Tech Lead  
**Session:** Technical Debt Strategy  
**Deliverable:** 1 of 4 — Technical Debt Inventory (25 points)  
**Assessment date:** 11 November 2026  

> **Training scenario / data integrity:** This is a completed *illustrative* submission for a hypothetical **Legacy Workforce Management Platform (LWMP)**, not a factual assessment of BISTEC or One Global Portal. All system names, ages, hours, incident assumptions and baselines are sample estimates. Replace and validate them against an actual system before presenting the work as measured organizational data.

## 1. Executive snapshot

The LWMP has **10 known debt items**, affecting the Employee Portal, Workflow API, Identity/Authorization Service, Reporting Service and delivery infrastructure. The main business issue is that onboarding changes and releases take longer while risks accumulate around reliability and tenant isolation.

- **2 Critical**, **4 High**, **2 Medium**, **2 Low** severity items.
- **6 items** have existed for at least 24 months.
- **Top five items** (TD-01 through TD-05) contribute an estimated **124 avoidable engineering hours per month**.
- A dedicated 20% debt-reduction allocation is recommended, with a prioritized 12-month roadmap.

## 2. Inventory structure and method (5 points)

**Identifier:** `TD-XX` is a permanent unique identifier. Each item links to a work ticket, affected repository/service, accountable owner, evidence and planned validation test.  
**Category:** Code, Architecture, Infrastructure, Documentation or Test.  
**Severity:** Critical (security / major business continuity risk), High (material reliability / delivery impact), Medium (recurring team friction), Low (localized issue).  
**Origin:** Deliberate/prudent, inadvertent/prudent, reckless/deliberate or reckless/inadvertent (where evidence permits). The quadrants explain *how* debt arose; they do not automatically set priority.

**Discovery method:** review incident postmortems, deployment history, lead-time data, developer interviews, architecture diagrams, code quality scans and open issue tags. Confirm every estimate with an owner at the next debt review.

## 3. Debt register (10 points)

| ID | Category | Description | Origin / quadrant | Systems affected | Age | Severity | Accountable owner |
|---|---|---|---|---|---:|---|---|
| TD-01 | Code | Business rules duplicated between API and admin UI, requiring two edits per change | Inadvertent/prudent: patterns diverged as product grew | Workflow API, Employee Portal | 30 months | High | API Tech Lead |
| TD-02 | Architecture | Synchronous onboarding calls to notifications and reporting cause cascading failures | Deliberate/prudent: synchronous flow used to meet initial release | Workflow API, Notification Service, Reporting Service | 36 months | Critical | Platform Architect |
| TD-03 | Test | Missing integration tests for authorization and tenant-data boundaries | Reckless/deliberate: tests repeatedly postponed | Identity Service, Workflow API | 18 months | Critical | QA Lead + Identity Lead |
| TD-04 | Infrastructure | Deployment and rollback rely on manual steps and individual knowledge | Deliberate/prudent: temporary manual deployment became permanent | CI/CD, all application services | 24 months | High | DevOps Lead |
| TD-05 | Architecture | Heavy reports query the transactional database and degrade response time | Inadvertent/prudent: reporting volume grew unexpectedly | Reporting Service, Main PostgreSQL DB | 30 months | High | Data/Backend Lead |
| TD-06 | Code | Legacy SQL construction and duplicate validation logic complicate safe changes | Inadvertent/prudent: multiple legacy code paths evolved | Workflow API | 26 months | Medium | Backend Lead |
| TD-07 | Test | Flaky UI end-to-end tests create false failures and reruns | Inadvertent/prudent: asynchronous UI behavior was poorly handled | Employee Portal, test pipeline | 14 months | Medium | QA Automation Lead |
| TD-08 | Infrastructure | Incomplete centralized logging, traces and alerting delay incident diagnosis | Reckless/deliberate: observability deferred | All APIs, production operations | 24 months | High | SRE/DevOps Lead |
| TD-09 | Documentation | No current ownership map or architecture decision history | Inadvertent/prudent: teams changed without documentation upkeep | Platform-wide | 16 months | Low | Tech Lead |
| TD-10 | Code | Legacy request-validation library is outdated and inconsistently used | Inadvertent/prudent: upgrade postponed because of compatibility concerns | Employee Portal, Workflow API | 10 months | Low | Frontend Lead |

**Owner accountability:** Owners verify impact, provide remediation estimates and report closure evidence; they do not necessarily perform every implementation task.

## 4. Categorization analysis (5 points)

### By category

| Category | Items | Count | Share |
|---|---|---:|---:|
| Code | TD-01, TD-06, TD-10 | 3 | 30% |
| Architecture | TD-02, TD-05 | 2 | 20% |
| Infrastructure | TD-04, TD-08 | 2 | 20% |
| Test | TD-03, TD-07 | 2 | 20% |
| Documentation | TD-09 | 1 | 10% |
| **Total** | | **10** | **100%** |

### By severity

| Severity | Count | Share | Items |
|---|---:|---:|---|
| Critical | 2 | 20% | TD-02, TD-03 |
| High | 4 | 40% | TD-01, TD-04, TD-05, TD-08 |
| Medium | 2 | 20% | TD-06, TD-07 |
| Low | 2 | 20% | TD-09, TD-10 |

### By age

| Age band | Count | Share | Items |
|---|---:|---:|---|
| Under 12 months | 1 | 10% | TD-10 |
| 12–23 months | 3 | 30% | TD-03, TD-07, TD-09 |
| 24 months and older | 6 | 60% | TD-01, TD-02, TD-04, TD-05, TD-06, TD-08 |

## 5. Hot spots (5 points)

### Top five business-impact items

| Rank | ID | Why this is a hot spot | Indicative recurring burden |
|---:|---|---|---:|
| 1 | TD-02 | Onboarding failures can cascade across dependencies | 24 hours/month + material outage risk |
| 2 | TD-03 | Tenant-access test gaps create severe security/business exposure | 26 hours/month + high incident impact |
| 3 | TD-01 | Duplicate rules slow almost every workflow change | 30 hours/month |
| 4 | TD-05 | Report jobs slow important employee workflows | 24 hours/month + performance incidents |
| 5 | TD-04 | Manual rollout and recovery increase release friction | 20 hours/month + deployment incidents |

**Highest concentrations:** Workflow API appears in TD-01, TD-02, TD-03, TD-06 and TD-10; release/test infrastructure appears in TD-04, TD-07 and TD-08. Counting system references is an indicator, not proof of cost by itself.

**Patterns identified:**

1. Shortcuts made to hit early deadlines were never revisited (TD-02, TD-04).
2. Automated quality controls were weaker than feature-delivery pressure (TD-03, TD-07).
3. Cross-service dependencies amplify local failures (TD-02, TD-05).
4. Missing ownership documentation makes recurring debt harder to detect (TD-09).

## 6. Validation and governance

- **Every two weeks:** Owners update new/closed items, evidence, severity and confidence.
- **Monthly:** Tech Lead reviews top five risk and effort trends with Product Manager.
- **Quarterly:** Architect and leadership review category concentrations, funding and roadmap changes.
- **Closure rule:** No item closes based on a code merge alone. Verify test results, production metric improvement, rollback readiness and an updated runbook/ADR where relevant.
- **Evidence needed before live submission:** incident tickets, deployment timestamps, issue labels, performance traces, developer time samples and risk-review sign-off.

## 7. Link to other deliverables

- **Deliverable 2:** Costs and ROI for TD-01 through TD-05.
- **Deliverable 3:** 12-month plan to address all 10 items, beginning with safety and reliable delivery.
- **Deliverable 4:** Business funding request and executive communication.

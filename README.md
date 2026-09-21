# Saudi BD Market Intelligence

**Business Development & Market Intelligence portfolio project** covering target-account research, ICP-based account scoring, CRM pipeline management and a Power BI dashboard, built around a hypothetical B2B HR technology + consulting provider growing in Riyadh.

> ⚠️ **SIMULATED DATA — for portfolio demonstration only.**
> Scores, tiers, opportunities, pipeline stages, tasks and next steps are simulated. They are not real client, contact or sales data. No outreach was sent to any company.

---

## Project Overview

| | |
|---|---|
| **Role in the case** | Business Development Specialist |
| **Market** | Saudi Arabia (Riyadh focus) |
| **Offering** | HR technology implementation combined with change management / user adoption |
| **Scope** | 50 target accounts · 8 market segments · 9 pipeline opportunities |
| **Output** | Scored account list, CRM pipeline, Power BI dashboard, business analysis |

## Business Problem

A BD team with limited prospecting time has to decide which Saudi companies to pursue first. A long market list, ranked by segment size, does not show which accounts actually fit the offering or where effort is being lost in the pipeline.

## Objectives

1. Build a researched target-account list across Saudi market segments.
2. Score every account against an explicit ICP model and group accounts into tiers.
3. Manage the resulting opportunities in a staged CRM pipeline with next-step tasks.
4. Visualise coverage, fit and pipeline in a Power BI dashboard.
5. Turn the data into evidence-based BD priorities and next actions.

## Dataset

| Table | Content |
|---|---|
| `dim_account` | 50 accounts: segment, tier, fit score, business signal, Riyadh presence, status |
| `fact_score_component` | 7 scoring components per account (350 rows) |
| `dim_tier` | Tier definitions and recommended action per tier |
| `fact_opportunity` | 9 opportunities: stage, priority, expected close month, next step |
| `dim_stage` | 7 pipeline stages with stage probability |
| `fact_task` | 18 next-step tasks linked to opportunities |

**SIMULATED DATA disclaimer:** company names are used as research targets. All scoring outcomes, tiers, opportunities, tasks and pipeline activity are simulated for demonstration. There are no Closed Won or Closed Lost records, so the project does not measure conversion or win rates.

## Methodology

1. **Research:** identify target accounts and record a dated business signal for each.
2. **Scoring:** score each account on 7 ICP components (100 points total).
3. **Tiering:** assign Tier A / B / C with a defined BD action per tier.
4. **Pipeline:** open opportunities for prioritised accounts and track them through CRM stages with next-step tasks.
5. **Reporting:** model the data in Power BI and QA every visual against the semantic model.
6. **Analysis:** segment, tier, fit-score and pipeline analysis, with every figure verified using read-only DAX queries.

## Account Scoring & Tiering

The Fit Score is the sum of seven components (verified: components sum to the Fit Score for all 50 accounts).

| Component | Max points |
|---|---|
| Sector | 20 |
| HR | 20 |
| Trigger | 15 |
| Size | 15 |
| Riyadh | 15 |
| Need | 10 |
| Access | 5 |
| **Total** | **100** |

| Tier | Accounts | Share | Avg Fit | Fit range | BD action |
|---|---|---|---|---|---|
| A | 11 | 22% | 83.9 | 76–91 | Pursue now – convert to pipeline |
| B | 20 | 40% | 68.0 | 61–77 | Nurture – re-score when a new dated trigger appears |
| C | 19 | 38% | 52.7 | 41–59 | Monitor only – no BD effort allocated |

Tiers are analyst-assigned. Every account scoring 80+ is Tier A and every account below 70 is Tier B or C; the 70–79 band is where analyst judgement decides the tier.

## CRM / HubSpot Pipeline Workflow

Opportunities follow a 7-stage deal pipeline based on HubSpot's default deal stages:

| Order | Stage | Stage probability | Group |
|---|---|---|---|
| 1 | Prospect Identified | 10% | Pre-engagement |
| 2 | Qualified Account | 25% | Pre-engagement |
| 3 | Initial Outreach | 40% | Engagement |
| 4 | Meeting / Discovery | 60% | Engagement |
| 5 | Proposal / Negotiation | 80% | Commercial |
| 6 | Closed Won | 100% | Closed |
| 7 | Closed Lost | 0% | Closed |

Each opportunity carries a deal priority, an expected close month and a next step, with two linked tasks (qualification + stage-specific preparation). Stage probabilities are model assumptions, not observed rates.

## Power BI Dashboard

**Saudi BD Market Intelligence Dashboard**: a one-page executive view.

- **Filters:** Segment, Tier, Stage, Deal Priority
- **KPIs:** Total Accounts (50), Pipeline Accounts (9), Average Fit Score (65.70), Tier A Accounts (11)
- **Visuals:** Accounts by Segment, Accounts by Tier, Pipeline by Stage, Top Priority Accounts (`priority_rank = 1`, sorted by Fit Score), Key Insights
- **QA:** every KPI, chart value, table row and filter result was checked against the semantic model with read-only DAX.

## Key Findings

1. **Account volume did not mean account quality.** Healthcare + Transport & logistics produced 6 Tier A accounts from 14 (43%); Construction + Technology produced 1 from 18 (6%).
2. **Tiering concentrates effort as designed.** Tier A is 22% of accounts and holds all 9 opportunities. Because no deal has closed, this shows consistency, not predictive power.
3. **The score is decisive at both ends.** All 8 accounts scoring 80+ are Tier A; all 34 accounts below 70 are Tier B/C. The 70–79 band (8 accounts) relies on undocumented analyst judgement.
4. **HR and Trigger components separate high-fit from low-fit accounts; Access barely differentiates** (Tier A vs C gap: HR +6.8, Trigger +6.6, Access +0.1 points).
5. **Priority runs opposite to pipeline progress.** All 4 Priority 1 opportunities are in the first two stages; the only Proposal / Negotiation opportunity is Priority 3.
6. **The pipeline is early-stage.** 6 of 9 opportunities (67%) are at Prospect Identified or Qualified Account.

## BD Recommendations

1. **Act on late-stage deals first:** clear overdue next steps on the Proposal and Meeting-stage opportunities.
2. **Close Tier A coverage:** open qualification for the 2 pending Tier A accounts before adding new accounts.
3. **Re-assess boundary Tier B accounts:** review the 5 Tier B accounts scoring 74–77 with a documented rationale.
4. **Focus prospecting on fit, not list size:** prioritise Healthcare and Transport & logistics; review targeting criteria for Construction, Technology and Financial services (22 accounts, 1 Tier A, 0 opportunities).
5. **Combine Fit Score with pipeline stage** when setting account priority.
6. **Document tiering rules:** record a rationale for 70–79 accounts, test a minimum HR-component threshold for Tier A, and review the Access component.
7. **Measure once real outcomes exist:** win rate and cycle length by tier and fit band, stage conversion, and which score components are associated with won deals.

## Limitations

- **SIMULATED DATA:** results describe how the model and pipeline were built, not market demand.
- Small sample: 50 accounts, 9 opportunities, 3–10 accounts per segment.
- No Closed Won / Lost outcomes and a single opportunity creation date, so there is no conversion, velocity or aging analysis.
- Fit Score components are the project's own ICP design; findings do not prove causation or market attractiveness.

## Tools & Skills

**Tools:** HubSpot CRM · Power BI (semantic model, DAX, report design) · GitHub

**Skills:** Market & account research · ICP definition and account scoring · Account tiering and prioritisation · CRM pipeline design · Business analysis and data QA · Dashboard design and executive reporting · Evidence-based BD recommendations

---

*SIMULATED DATA: portfolio demonstration only. Not real client, contact or sales data.*

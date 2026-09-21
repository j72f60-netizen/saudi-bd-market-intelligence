# Methodology

> ⚠️ **SIMULATED DATA — for portfolio demonstration only.** Scores, tiers, opportunities, pipeline stages and tasks are simulated. Every figure below was verified against the Power BI semantic model with read-only DAX.

## 1. Account targeting

- 50 target accounts across 8 Saudi market segments, each with a recorded business signal and research source.
- Segment coverage (accounts / Tier A):

| Segment | Accounts | Share | Tier A | Avg Fit Score | Opportunities |
|---|---|---|---|---|---|
| Construction, real estate & industrial | 10 | 20% | 1 | 64.0 | 0 |
| Healthcare | 9 | 18% | 4 | 77.2 | 4 |
| Technology & platforms | 8 | 16% | 0 | 51.9 | 0 |
| Retail, e-commerce & F&B | 7 | 14% | 2 | 68.9 | 2 |
| Transport & logistics | 5 | 10% | 2 | 72.8 | 1 |
| Education & training | 4 | 8% | 1 | 69.5 | 1 |
| Financial services & fintech | 4 | 8% | 0 | 54.5 | 0 |
| Leisure & hospitality | 3 | 6% | 1 | 64.3 | 1 |
| **Total** | **50** | **100%** | **11** | **65.7** | **9** |

## 2. Fit Score

The Fit Score (0–100) is the sum of seven components; components sum exactly to the Fit Score for all 50 accounts.

| Component | Max points | Avg Tier A | Avg Tier B | Avg Tier C |
|---|---|---|---|---|
| Sector | 20 | 20.0 | 18.0 | 14.1 |
| HR | 20 | 12.8 | 9.9 | 6.1 |
| Trigger | 15 | 12.1 | 7.6 | 5.5 |
| Size | 15 | 12.5 | 10.5 | 8.8 |
| Riyadh | 15 | 13.5 | 11.9 | 8.6 |
| Need | 10 | 8.5 | 6.1 | 5.4 |
| Access | 5 | 4.5 | 4.1 | 4.3 |

Distribution: min 41, 25th percentile 54.3, median 65, mean 65.7, 75th percentile 74, max 91, standard deviation 12.6.

| Band | Accounts | Tier A | Tier B | Tier C | In pipeline |
|---|---|---|---|---|---|
| 80–100 | 8 | 8 | 0 | 0 | 7 |
| 70–79 | 8 | 3 | 5 | 0 | 2 |
| 60–69 | 15 | 0 | 15 | 0 | 0 |
| 50–59 | 16 | 0 | 0 | 16 | 0 |
| Below 50 | 3 | 0 | 0 | 3 | 0 |

## 3. Tiering

Tiers are **analyst-assigned** (per `dim_tier`) and are not a pure score cut-off.

| Tier | Accounts | Share | Avg Fit | Fit range | Pipeline | BD action |
|---|---|---|---|---|---|---|
| A | 11 | 22% | 83.9 | 76–91 | 9 of 11 (82%) | Pursue now – convert to pipeline |
| B | 20 | 40% | 68.0 | 61–77 | 0 | Nurture – re-score when a new dated trigger appears |
| C | 19 | 38% | 52.7 | 41–59 | 0 | Monitor only – no BD effort allocated |

- Every account scoring 80+ is Tier A; every account below 70 is Tier B or C.
- The 70–79 band mixes tiers. Tier A minimum is 76 (Flynas); Tier B maximum is 77 (Marketing Home Group). Flynas scores higher on HR (13 vs 5); Marketing Home scores higher on Size (15 vs 8) and Access (5 vs 3). This is consistent with HR relevance influencing tier, but no field records the per-account rationale.

## 4. Pipeline

- 9 opportunities, all Tier A, all created on the same date; no Closed Won or Closed Lost records.
- Stages follow a 7-stage pipeline based on HubSpot default deal stages; stage probabilities are model assumptions.

| Stage | Opportunities | Share | Avg Fit | Priority mix |
|---|---|---|---|---|
| Prospect Identified | 3 | 33% | 89.7 | 3 × P1 |
| Qualified Account | 3 | 33% | 86.3 | 1 × P1, 2 × P2 |
| Initial Outreach | 0 | 0% | — | — |
| Meeting / Discovery | 2 | 22% | 80.0 | 1 × P2, 1 × P3 |
| Proposal / Negotiation | 1 | 11% | 78.0 | 1 × P3 |

- 6 of 9 opportunities (67%) are in the two Pre-engagement stages.
- Priority rank follows Fit Score, not stage: all Priority 1 opportunities are at stages 1–2, while the only Proposal / Negotiation opportunity is Priority 3.
- Pipeline by segment: Healthcare 4, Retail, e-commerce & F&B 2, Transport & logistics 1, Education & training 1, Leisure & hospitality 1.
- 18 tasks (2 per opportunity): 9 completed (all Qualification), 9 open and not started.

## 5. Recommendations

1. Act on late-stage opportunities first and clear their open next steps.
2. Open qualification for the 2 pending Tier A accounts (Flynas, Saudi Arabian Trading) before adding new accounts.
3. Re-assess the 5 Tier B accounts scoring 74–77 with a documented rationale.
4. Prioritise Healthcare and Transport & logistics; review targeting criteria for Construction, Technology and Financial services (22 accounts, 1 Tier A, 0 opportunities).
5. Combine Fit Score with pipeline stage when setting priority.
6. Record a tier rationale for 70–79 accounts, test a minimum HR-component threshold for Tier A, and review the Access component.
7. Once real outcomes exist, measure win rate and cycle length by tier and fit band, stage conversion, and which components are associated with won deals.

## 6. Limitations

- Simulated data; results describe how the model and pipeline were built, not market demand.
- Small samples: 50 accounts, 9 opportunities, 3–10 accounts per segment.
- No closed outcomes and a single creation date, so there is no conversion, velocity or aging analysis.
- Fit Score components are the project's own ICP design; findings do not prove causation or market attractiveness.

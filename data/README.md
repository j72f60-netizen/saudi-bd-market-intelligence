# Data

> ⚠️ **SIMULATED DATA — for portfolio demonstration only.**
> These files are not real client, contact or sales data.

## About these files

- The 7 CSV files are **exact exports of the Power BI semantic model** behind the *Saudi BD Market Intelligence Dashboard*. Each file was exported table by table with read-only DAX queries; no rows or values were generated, modified or enriched.
- They are **not the original source files**. The original CSVs live in the author's private cloud storage and were not published. File names were cleaned (duplicate suffixes removed).
- **Company names, business signals and research source URLs** may come from public research. **All scoring, tiers, opportunities, pipeline stages, tasks and next steps are simulated.** No outreach was sent to any company.
- Dates and date-times are exported in ISO format (`YYYY-MM-DDTHH:MM:SS`). Blank cells are empty values in the model.

## Files

| File | Rows | Content |
|---|---|---|
| `dim_account.csv` | 50 | Target accounts: segment, tier, Fit Score and band, Riyadh presence, size and listing proxies, business signal, status, pipeline flag, task counts, research source URL |
| `fact_score_component.csv` | 350 | Fit Score breakdown: 7 components per account (points awarded, max points, attainment %) |
| `dim_tier.csv` | 3 | Tier definitions: observed score range, account count, BD action, tier note |
| `dim_segment.csv` | 8 | Market segments: accounts researched and accounts in pipeline |
| `dim_stage.csv` | 7 | Pipeline stages: order, label, stage probability, closed flag, stage group |
| `fact_opportunity.csv` | 9 | Opportunities: account, stage, Fit Score, deal priority and rank, expected close, created date, next step |
| `fact_task.csv` | 18 | Next-step tasks linked to opportunities: category, status, priority, due date |

## Relationships (as used in the model)

- `dim_account.account_key` → `fact_opportunity`, `fact_task`, `fact_score_component`
- `dim_tier.account_tier` → `dim_account.account_tier`
- `dim_segment.bd_segment` → `dim_account.bd_segment`

`fact_opportunity` and `fact_task` include `is_simulated` / `data_class` columns marked `SIMULATED`. The other tables have no such column but are equally part of the simulated dataset.

# Union Budget 2024-25: Budget Estimate vs Revised Estimate vs Actuals, by demand for grants

File: `budget-be-vs-actual-2024-25.csv` (UTF-8, header row, 102 data rows, one per demand for grants).
Published 23 November 2026 with the study https://paisatools.co.in/research/union-budget-2024-25-allocation-vs-spending

## Columns

| Column | Meaning |
|---|---|
| `ministry_or_department` | Name of the demand as printed in Statement 3 |
| `demand_no` | Demand number (1 to 102) |
| `be_2024_25_cr` | Budget Estimate 2024-25, Budget presented July 2024 (Rs crore, net) |
| `re_2024_25_cr` | Revised Estimate 2024-25, printed February 2025 (Rs crore, net) |
| `actual_2024_25_cr` | Actuals 2024-25, printed February 2026 (Rs crore, net) |
| `diff_cr` | Actual minus BE, Rs crore (derived by PaisaTools) |
| `pct_of_be` | Actual as % of BE, two decimals (derived by PaisaTools; empty where BE is nil) |
| `source_be` | Document, statement and printed page of the BE figure |
| `source_actual` | Document, statement and printed page of the Actual figure |

## Units

Rs crore (1,00,000 crore = 1 lakh crore). Figures are net of receipts and recoveries, as printed (Budget at a Glance 2026-27, p.ii, note 3), with the two decimals the documents print. Demand 40, Repayment of Debt, is nil in all columns.

## Sources

All Ministry of Finance, Budget Division, downloaded from indiabudget.gov.in on 23 November 2026. Page numbers are printed page numbers.

- Expenditure Profile 2024-25 (July 2024), Statement 3, pp.4-20: https://www.indiabudget.gov.in/budget2024-25/doc/eb/vol1.pdf
- Expenditure Profile 2025-26 (February 2025), Statement 3, pp.4-20: https://www.indiabudget.gov.in/budget2025-26/doc/eb/vol1.pdf
- Expenditure Profile 2026-27 (February 2026), Statement 3, pp.4-20; Statements 1 and 17: https://www.indiabudget.gov.in/doc/eb/vol1.pdf
- Budget at a Glance 2024-25, 2025-26, 2026-27, p.1 row 9 (Total Expenditure), used to check the three Grand Totals.

## Checks

The 102 demand totals add up exactly to the printed Grand Total in each document; Revenue + Capital = Total for every demand; the BE printed in February 2025 equals the BE printed in July 2024 for every demand. A separate AI agent recomputed the totals, the share spent, the gap, the count of 85 demands with a BE of Rs 1,000 crore or more (56 below BE) and the largest gap on 23 November 2026: all agree.

## Limits

The documents print "Actuals 2024-2025" without saying they are final or audited. No cross-check with the Controller General of Accounts. Demands, not ministries. No reasons for any gap are given in Statement 3. Net, not gross, figures.

## Licence

Our derived columns (`diff_cr`, `pct_of_be`), the joins and the tables are CC BY 4.0, attribution required: https://creativecommons.org/licenses/by/4.0/. The budget figures themselves are Government of India data and keep the Ministry of Finance's own terms; we link the source documents.

Cite as: PaisaTools Research (2026). Union Budget 2024-25: Budget Estimate vs Revised Estimate vs Actuals by demand for grants. https://paisatools.co.in/open-data/budget-be-vs-actual-2024-25.csv

Corrections: https://paisatools.co.in/contact (reply within 2 working days). Not legal or financial advice.

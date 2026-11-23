# PaisaTools open pay data (7th CPC), 12 Nov 2026

Small CSV data set (UTF-8, LF, header row) from figures the PaisaTools Sarkari Pay and DA calculators already use.

Last updated: 12 Nov 2026

## Files and sources

| File | What it is | Source order named in our code |
|---|---|---|
| `pay-matrix-7cpc.csv` | 7th CPC pay matrix: level, cell, basic pay in INR (540 cells, Levels 1 to 18 incl. 13A) | CCS (Revised Pay) Rules, 2016, Schedule, Part A, Ministry of Finance notification 25 July 2016 (Gazette of India No. 512, G.S.R. 721(E)). Level 13 is the amended row: CCS (Revised Pay) (Amendment) Rules, 2017, G.S.R. 592(E), 15 June 2017 (w.e.f. 1 Jan 2016); the Level 13 rows carry that in their `source` column. |
| `da-history-central.csv` | Central government DA rates (% of basic pay) under the 7th CPC, 1 Jan 2016 to 1 Jul 2026, one row per revision, with the DoE OM, the PDF opened and a status | 21 DoE (E.II(B)) OMs, from No. 1/2/2016-E-II (B), 4 Nov 2016 to No. 1/2(i)/2026-E.II(B), 29 Oct 2026; see "DA history: checks and gaps" |
| `hra-transport-rules.csv` | HRA rates by city class, transport allowance by level, the 19 higher-TA cities | HRA: DoE OM, 7 July 2017. Transport allowance: DoE OM No. 21/5/2017-E.II(B), 7 July 2017. City list: DoE OMs of 7 Jul / 2 Aug 2017 |
| `central-pay-vs-cpi-iw-2016-2026.csv` | Central pay vs prices, Jan 2016 to 2026, monthly: CPI-IW (published and linked to a 2016 base), DA due and DA paid, and the real value of pay. Data dictionary and method: `central-pay-vs-cpi-iw-2016-2026.README.md`. Article: https://paisatools.co.in/research/central-pay-vs-prices-2016-2026 (added 23 Nov 2026) | Labour Bureau CPI-IW releases and annual reports; DoE (E.II(B)) DA OMs; per-row source columns |
| `budget-be-vs-actual-2024-25.csv` | Union Budget 2024-25: Budget Estimate (July 2024) vs Actuals for every demand for grants, Rs crore, with the share spent. Data dictionary: `budget-be-vs-actual-2024-25.README.md`. Article: https://paisatools.co.in/research/union-budget-2024-25-allocation-vs-spending (added 23 Nov 2026) | Expenditure Profile 2024-25, 2025-26 and 2026-27 (Statement 3); Budget at a Glance 2024-25, 2025-26 and 2026-27 (indiabudget.gov.in); per-row source columns |
| `state-da-orders-july-2026.csv` | State and UT dearness allowance orders after the Centre's July 2026 DA rise: order number and date, new and previous rate, effective date, arrear terms, days from 1 July and from the Centre's order. Data dictionary: `state-da-orders-july-2026.README.md`. Article: https://paisatools.co.in/research/state-da-orders-july-2026 (added 23 Nov 2026) | Each government's finance department order on its official website (URL per row) |

## How the data was made

These are the orders as read by PaisaTools editors, not an official publication. Dates stated in our code comments: the pay matrix was extracted from the Gazette text PDF on 5 Nov 2026 and re-checked cell by cell on 6 Nov 2026 (all rows matched except Level 13, the amended row); the DA rates were last checked on 30 Oct 2026. Our code states no reading dates for the HRA and transport allowance rules.

## Licence

Proposed: Creative Commons Attribution 4.0 (CC BY 4.0), attribution required.

Cite as: PaisaTools, Open pay data (7th CPC), https://paisatools.co.in, accessed <date>

## Not legal or financial advice

This is reference data, not legal or financial advice. Check the official order for your own case.

Corrections: https://paisatools.co.in/contact

## Checks

- `pay-matrix-7cpc.csv`: 540 data rows (19 levels).
- `da-history-central.csv`: 23 data rows (see below).
- `hra-transport-rules.csv`: 29 data rows (4 HRA, 6 transport allowance, 19 cities).
- `central-pay-vs-cpi-iw-2016-2026.csv`: 129 data rows.
- 5 random pay-matrix rows spot-checked against `src/data/pay-matrix-7cpc.ts`, all matched: L13 cell 13 = 175500; L7 cell 36 = 126600; L9 cell 39 = 162900; L4 cell 27 = 55100; L10 cell 31 = 136000.

## Gaps

- DA: see "DA history: checks and gaps" below.
- HRA: our code names no OM number, only "DoE OM, 7 July 2017".
- City list: no OM numbers for the 7 Jul / 2 Aug 2017 OMs in our code; the 2 Aug 2017 OM is not separately identified.
- HRA rule "once DA has crossed 50%" comes from a code comment; the paragraph of the OM is not stated, except para 6 for Ghaziabad.

## DA history: checks and gaps

Checked 12 Nov 2026. Every row's PDF was downloaded from doe.gov.in and its scanned page read; `order_ref` is the OM number and date as printed on the OM. Columns added: `issuing_body`, `official_url` (the PDF opened), `status`.

- 23 data rows: 23 `read`, 0 `not verified`. They cover every 1 January / 1 July date from 1 Jan 2016 to 1 Jul 2026, plus a second 1 Jul 2021 row.
- 7th CPC reset: OM No. 1/2/2016-E-II (B), 4 Nov 2016, para 2. The revised pay from 1 Jan 2016 already includes the 125% DA of the old pay structure, so DA in the revised structure is zero from 1 Jan 2016. The same OM sets 2% from 1 Jul 2016.
- 2020-21 freeze: OM No. 1/1/2020-E-II (B), 23 Apr 2020, stopped the instalments due 1 Jan 2020, 1 Jul 2020 and 1 Jan 2021, kept the current rate, and said no arrears for 1 Jan 2020 to 30 Jun 2021. OM No. 1/1/2020-E-II (B), 20 Jul 2021, set 28% from 1 Jul 2021 (subsuming the three instalments) and kept 17% for 1 Jan 2020 to 30 Jun 2021. OM No. 1/4/2021-E-II (B), 25 Oct 2021, then raised it to 31% from the same 1 Jul 2021. The three freeze rows show 17% (the rate paid).
- 58% row: now dated 1 Jul 2025, OM No.1/4(i)/2025-E.II(B), 06 Oct 2025 (read). 60% row: OM No. 1/1(i)/2026-E.II(B), 22 Apr 2026, number and date confirmed on the OM.
- Not found / not opened: the notional instalment rates for 1 Jan 2020, 1 Jul 2020 and 1 Jan 2021 are not stated in the freeze or restoration OM, and no DoE OM granting them is on the DoE DA list; any Cabinet/PIB release for them was not opened. The 125% OM of 7 Apr 2016 (6th CPC pay) and the DoPPW DR orders were not opened. The 63% row's PIB release was not re-opened (the OM itself was read).
- Where DoE's list differs from the OM: the 1 Jan 2019 OM is listed as 1/2/2019-E.II(B) but prints 1/1/2019-E-II (B); the CSV uses the printed number. The 1 Jul 2023, 1 Jan 2024 and 1 Jul 2024 OMs are not on DoE's DA list pages; they were found on DoE's What's New pages (`source_url`).
- Railway employees and Armed Forces personnel get separate orders from their ministries; these rows are the DoE orders for civilian central government employees only.

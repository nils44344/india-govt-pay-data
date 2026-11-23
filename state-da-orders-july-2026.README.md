# July 2026 dearness allowance (DA) rise: state and UT orders opened on official websites, with day counts

File: `state-da-orders-july-2026.csv` (UTF-8, header row, 8 data rows: the Centre's order as a reference row and the 7 state and UT orders counted).
Published 23 November 2026 with the study https://paisatools.co.in/research/state-da-orders-july-2026
Data as of 23 November 2026 (every order downloaded from the government's own website and read that day).

## Columns

| Column | Meaning | Label |
|---|---|---|
| `government` | Government that issued the order | - |
| `role` | `reference` (the Centre's order, not counted) or `counted` (one of the 7 state and UT orders) | - |
| `issuer` | Department named on the order | Official |
| `order_no` | Order, resolution or memorandum number, in English as printed or transliterated | Official |
| `order_no_as_printed` | The number in the order's own script where it is not English (Gujarat in Gujarati, Karnataka in Kannada); empty otherwise | Official |
| `order_date` | Date printed on the order, ISO (YYYY-MM-DD). Odisha's date is handwritten on the order ("18/11/2026") | Official |
| `rate_from_pct`, `rate_to_pct` | DA rate before and after, % of basic pay. Empty for Puducherry, whose order adopts the Centre's memorandum instead of printing a rate. Karnataka is on its own 2024 pay scale with its own rates | Official |
| `rate_text` | The rate as it reads in the order | Official |
| `effective_from` | Date from which the order applies the new rate (1 July 2026 in every order) | Official |
| `cash_month` | Month (YYYY-MM) with whose salary the new rate is first paid, or `not stated` | Official |
| `cash_text` | The payment month in the order's words | Official |
| `arrear_term` | How the July to October 2026 difference is handled: `cash_with_nov_salary`, `named_later_month`, `provident_fund`, `after_nov_salary_no_date`, `not_stated` | Official (our grouping of the order's words) |
| `arrear_text` | The arrear term in the order's words | Official |
| `cites_centre_om_29_oct_2026` | `yes` if the order cites the Centre's OM No. 1/2(i)/2026-E.II(B) of 29 October 2026 by number; empty for the Centre's own row | Official |
| `days_after_effective` | Days from 1 July 2026 to `order_date` | Measured |
| `days_after_centre` | Days from 29 October 2026 (the Centre's order) to `order_date` | Measured |
| `source_url` | The official web address the order was downloaded from | - |
| `source_date` | Date the order was downloaded and read (2026-11-23) | - |
| `read_method` | How the order was read: PDF text layer, or by eye where the PDF is a scan | - |
| `label` | Label of the row's figures (methodology: https://paisatools.co.in/research/methodology) | - |
| `facts_rows` | Row ids in our facts file for this order | - |

## How it was made

1. For each government, the finance department order raising DA from 1 July 2026 was found and downloaded from the official website on 23 November 2026 (six of the orders were also read on 22 November; the files were byte-identical).
2. Order number, date, rate, payment month and arrear paragraph were read from the order itself.
3. `scripts/research/state-da-orders-july-2026.mjs` computes the day counts by date arithmetic and writes this CSV; it stops if any computed count differs from our facts file.
4. A separate AI agent, given the source links and the formulas but not our findings, recomputed the day counts, the median and the range on 23 November 2026: all agree.

## Not in this file

- Uttar Pradesh: a copy of an order was seen only on a private website (the official portal needs a captcha). Not confirmed; not counted.
- Governments with no official copy of a July 2026 order found by 23 November 2026 (among them Tamil Nadu, Jharkhand, Bihar and Arunachal Pradesh). "No order found" means we did not find an official copy; it does not mean no order exists.
- Pensioner orders (Dearness Relief) are not measured.

## Licence

Our CSV, the day counts and the grouping are CC BY 4.0, attribution required: https://creativecommons.org/licenses/by/4.0/. The orders themselves are government documents and keep their own terms; we link them.

Cite as: PaisaTools Research (2026). July 2026 DA rise: state and UT orders and day counts. https://paisatools.co.in/open-data/state-da-orders-july-2026.csv

Corrections: https://paisatools.co.in/contact (reply within 2 working days). Not legal or financial advice.

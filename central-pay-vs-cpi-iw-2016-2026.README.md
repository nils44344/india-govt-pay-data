# Central pay vs CPI-IW, January 2016 to September 2026 (PaisaTools Research)

One row per month. Real value of a 7th Central Pay Commission pay cell's basic pay plus dearness allowance (DA), measured
against the All-India Consumer Price Index for Industrial Workers (CPI-IW), January 2016 = 1.00.

Article: https://paisatools.co.in/research/central-pay-vs-prices-2016-2026
Data date: CPI-IW to September 2026 (labourbureau.gov.in/all-india-index, read 22 November 2026); DA orders to the OM of
29 October 2026. Built by build_series.py and compute_real_pay.py (published alongside).

## Columns
| Column | Unit | Label | Meaning |
|---|---|---|---|
| month | YYYY-MM | | Calendar month |
| cpi_iw_published | index points | official | CPI-IW as published by the Labour Bureau, on the base in the next column |
| cpi_iw_published_base | year | official | 2001 (Jan 2016 to Aug 2020) or 2016 (Sep 2020 onward) |
| cpi_iw_base2016 | index points | official / derived | Base-2016 value: as published from Sep 2020; before that the published base-2001 value divided by the official linking factor 2.88 |
| cpi_iw_base2016_status | text | | "published" or "linked (published / 2.88)" |
| cpi_iw_source | text | | Document the published value comes from |
| price_level_vs_jan2016 | ratio | derived | cpi_iw_base2016 / January 2016 value (93.4028) |
| da_due_pct | % of basic pay | official | DA rate in force by its effective date (the rate finally due, arrears included) |
| da_due_effective_from | date | official | Effective date of that rate |
| da_due_om_date | date | official | Date of the OM that set it (for January 2020 to June 2021: the restoration OM of 20 July 2021, which confirmed 17%) |
| da_paid_pct | % of basic pay | derived | DA rate in monthly pay that month, counting a new rate from the month after its OM; arrears paid later are not included |
| da_paid_om_date | date | official | Date of the OM behind da_paid_pct (blank before the first OM) |
| real_value_due | ratio | derived | (1 + da_due_pct/100) / price_level_vs_jan2016; 1.00 = January 2016 purchasing power |
| real_value_paid | ratio | derived | (1 + da_paid_pct/100) / price_level_vs_jan2016 |
| da_due_om_ref | text | official | Number and date of the OM behind da_due_pct, as printed on it; freeze months name the freeze OM of 23 April 2020 and the restoration OM of 20 July 2021 |
| da_paid_om_ref | text | official | Number and date of the OM behind da_paid_pct (blank before the first OM) |
| da_om_source_url | URL | | Link to the OM behind da_due_pct (Department of Expenditure, or the PIB release where the OM file was not on the DoE site) |
| cpi_iw_source_url | URL | | Labour Bureau annual report (base-2001 months) or the All-India index page (base-2016 months) |
| source_read_date | text | | When we read the sources: CPI-IW 22 November 2026, DA OMs 12 November 2026 |

The ratio is the same for every cell of the pay matrix, because DA is a percentage of basic pay. It measures the pay scale,
not a person's pay (no annual increments, no HRA or other allowances).

## Limits
- January 2016 (269) and the other base-2001 values are published as whole numbers and the linking factor (2.88) to two
  decimals. At the edges of that rounding, the September 2026 real_value_due lies between 0.976 and 0.983.
- The paid columns assume a new rate reaches pay the month after its order; payroll months vary by office.
- 2020-21 freeze: January 2020 to June 2021 carry 17%, the rate in force under the Finance Ministry order of 23 April 2020.

## Sources
- Labour Bureau, Annual Report on CPI-IW 2019 (Table 4.1) and 2020 (month-wise table; linking factor); labourbureau.gov.in/all-india-index.
- PIB, Ministry of Labour and Employment, 22 October 2020 (PRID 1666782): new series and linking factor 2.88.
- Department of Expenditure DA office memorandums, 2016-2026: see da-history-central.csv for each OM's number, date and link.

## Licence and citation
Our calculated columns are CC BY 4.0: reuse with credit, no permission needed. CPI-IW values (Labour Bureau) and DA orders
(Department of Expenditure) keep their own terms. Cite: PaisaTools Research (2026), "Has central government pay kept pace
with prices since January 2016?", paisatools.co.in/research/central-pay-vs-prices-2016-2026.
Corrections within 2 working days of a valid report.

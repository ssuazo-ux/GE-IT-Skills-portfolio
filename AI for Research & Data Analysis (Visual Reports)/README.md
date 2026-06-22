# Data Analytics & Visual Report

### Dataset Focus: Mindanao LGU Budget Utilization & Expenditure Performance Index
**Role:** Data Analyst — Regional Development Council / Commission on Audit (COA) Liaison Unit, Mindanao
**Audience:** Regional Policymakers and LGU Department Heads
**Period:** 2020–2025

---

## 1. Data Cleaning Protocol Log

**Raw Input Problem:**
The CSV file contained 120 row inputs across three provincial LGU clusters with the following structural issues:
- Mixed currency formatting (e.g., `"₱1,200,000"` vs. `"1200000"` vs. `"1.2M"`) across budget columns
- 11 null cells in the `Utilization Rate (%)` column concentrated in 2022–2023 fiscal records
- Inconsistent sector labeling (e.g., `"Health"` vs. `"health services"` vs. `"HEALTH"`)
- Two duplicate entries for Zamboanga del Sur infrastructure disbursements in FY2021

**AI Cleaning Instruction:**
> "Scan this dataset. Identify all null rows in the `Utilization Rate (%)` column and replace them with the median value for that specific sector and province cluster. Standardize all currency values to Philippine Peso in millions (₱M). Normalize sector labels to title case. Remove duplicate rows. Output the first 5 rows of the cleaned table."

**Result:**
Successfully normalized 120 row inputs across three provincial LGU clusters.

| Metric | Value |
|---|---|
| Rows Processed | 120 |
| Null Values Imputed | 11 (via per-sector median replacement) |
| Currency Format Conversions | 43 (standardized to ₱M) |
| Label Conflicts Resolved | 12 (case normalization) |
| Duplicate Rows Removed | 2 |

**First 5 Rows of Cleaned Table:**

| Year | Province | Sector | Appropriated Budget (₱M) | Actual Disbursement (₱M) | Utilization Rate (%) |
|---|---|---|---|---|---|
| 2020 | Zamboanga del Norte | Health | 142.50 | 118.30 | 83.0% |
| 2020 | Zamboanga del Sur | Infrastructure | 210.80 | 165.40 | 78.5% |
| 2020 | Zamboanga City | Education | 188.60 | 174.20 | 92.4% |
| 2021 | Zamboanga del Norte | Infrastructure | 198.30 | 141.60 | 71.4% |
| 2021 | Zamboanga del Sur | Health | 156.70 | 138.90 | 88.6% |

---

## 2. Visualizations Generated

### Chart A — LGU Budget Utilization Rate by Sector (2020–2025)
**Type:** High-contrast multi-series line chart
**Source data:** Mindanao LGU Budget Utilization Index, 2020–2025
**Scope:** Annual utilization rate (%) across Health, Infrastructure, and Education sectors

```
Utilization Rate (%)
95% |         ● Education
    |    ●              ●         ●
90% |                        ●
    |                                   ●
85% | ●
    |              ● Health
80% |    ●                   ●
    |         ●                    ●         ●
75% |                   ↓ Pandemic
    |              ↓ disruptions        ● Infrastructure
70% |                        ●
    |    ●
65% |
    +----+-----+-----+-----+-----+-----+
        2020  2021  2022  2023  2024  2025
```

*(Embedded high-contrast multi-series line chart — LGU Budget Utilization Rate by Sector, 2020–2025)*

**Key observations:**
- Education consistently posted the highest utilization rates (88–94%), reflecting stable personnel and operational expenditure patterns
- Infrastructure utilization dropped sharply to 68% in 2021–2022, driven by COVID-19 lockdown delays in procurement and project implementation
- Health sector utilization spiked in 2021 (91%) due to emergency pandemic spending, then normalized to 82–85% by 2023–2025
- All three sectors trended upward post-2023, indicating recovery in LGU absorptive capacity

---

### Chart B — Appropriated vs. Actual Disbursement by Province (₱M, Stacked)
**Type:** High-contrast grouped bar chart
**Source data:** Mindanao LGU Budget Disbursement Records, 2020–2025
**Scope:** Total annual appropriations vs. actual disbursements across three Zamboanga Peninsula provinces

```
Budget (₱M)
700 |
    |  ▓▓▓  Appropriated
600 |  ███  Actual Disbursed
    |
500 | ▓▓▓ ▓▓▓ ▓▓▓ ▓▓▓ ▓▓▓ ▓▓▓
    | ███ ███ ███ ███ ███ ███
400 |
    |
300 |
    +----+-----+-----+-----+-----+-----+
        2020  2021  2022  2023  2024  2025

  Province clusters: Zamboanga del Norte | Zamboanga del Sur | Zamboanga City
```

*(Embedded high-contrast grouped bar chart — Appropriated vs. Actual LGU Disbursements by Province, 2020–2025)*

**Key observations:**
- Zamboanga City consistently recorded the highest appropriations (avg. ₱610M/year) but also the widest variance gap in 2021–2022
- Zamboanga del Norte showed the lowest absorptive capacity across the period, averaging only 74.3% utilization
- The aggregate unutilized budget across all three provinces peaked at ₱312M in 2022, representing a significant opportunity cost in deferred public services
- By 2025, the gap narrowed to ₱89M — the lowest on record — suggesting improved procurement processes and cash management

---

## 3. Human Analytical Narrative — The "Why" Factor

The six-year budget utilization data for the Zamboanga Peninsula LGU cluster reveals a systemic pattern that goes beyond the disruptions of the pandemic: **LGU absorptive capacity in the region has been chronically constrained**, not merely by external shocks, but by structural weaknesses in local procurement systems, budget programming, and financial management personnel.

The 2021–2022 infrastructure utilization collapse — dropping to as low as 68% in some provincial clusters — is the most visible data point, and while COVID-19 lockdowns provide partial explanation, human cross-referencing with COA annual audit reports from the same period identifies a more persistent cause: **late submission of disbursement vouchers, delayed obligation of allotments, and absence of trained accountants in key municipal offices**. These are not pandemic-induced anomalies. They are pre-existing vulnerabilities that the pandemic simply made impossible to ignore.

The Education sector's relative stability (88–94% utilization throughout) is instructive precisely because it contrasts with Infrastructure. Education spending is dominated by personnel services — salaries, MOOE for schools — which are regular, predictable, and processed through well-established payroll systems. Infrastructure, by contrast, demands competitive bidding under RA 9184, project monitoring, and multi-step disbursement workflows that overtax understaffed local accounting and engineering offices simultaneously.

This data makes a specific argument to budget policymakers: **the problem is not insufficient appropriations — it is insufficient institutional capacity to spend what is already allocated.** Increasing LGU Internal Revenue Allotment (IRA) shares without parallel investment in local financial management capacity will only widen the unutilized budget gap. The ₱312M in unspent funds recorded in 2022 represents deferred health centers, unpaved farm-to-market roads, and delayed classroom repairs — not fiscal prudence.

The policy recommendation is threefold. First, DILG and DBM should jointly mandate **LGU Budget Utilization Scorecards** published quarterly, making absorptive capacity a condition for the release of Special Purpose Fund tranches. Second, the Civil Service Commission should fast-track the deployment of **government accountants to fourth- and fifth-class municipalities** in Zamboanga Peninsula, where vacancy rates in accounting positions remain above 40%. Third, LGUs should be required to submit **Annual Procurement Plans aligned to cash flow projections** — not just to BAC timelines — so that budget utilization is planned as a financial management exercise, not merely a compliance one.

The upward trend from 2023 onward is encouraging, but it reflects recovery, not reform. Sustained improvement will require structural intervention, not just the absence of a pandemic.

---

*Prepared by the Regional Data Analytics Unit · Zamboanga Peninsula Regional Development Council · June 2025*
*Dataset: Mindanao LGU Budget Utilization & Expenditure Performance Index (Mock CSV Analysis)*

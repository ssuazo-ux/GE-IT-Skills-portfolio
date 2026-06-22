# Data Analytics & Visual Report

### Dataset Focus: Davao Region Agricultural & Energy Production Index
**Role:** Data Analyst — Regional Development Council / Environmental Monitoring Coalition, Mindanao
**Audience:** Regional Policymakers and LGU Department Heads
**Period:** 2020–2025

---

## 1. Data Cleaning Protocol Log

**Raw Input Problem:**
The CSV file contained 120 row inputs across three provincial clusters with the following structural issues:
- Mixed mass units (metric tons vs. kilograms) across entries
- 14 null cells in the `Yield` column concentrated in 2023 records
- Inconsistent crop-tier labeling (e.g., `"Cacao"` vs. `"cacao"` vs. `"CACAO"`)
- Duplicate row entries for two municipal cluster codes

**AI Cleaning Instruction:**
> "Scan this dataset. Identify all null rows in the `Yield` column and replace them with the median value for that specific crop tier. Convert all mass metrics to standard Metric Tons (MT). Normalize crop-tier labels to title case. Remove duplicate rows. Output the first 5 rows of the cleaned table."

**Result:**
Successfully normalized 120 row inputs across three provincial clusters.

| Metric | Value |
|---|---|
| Rows Processed | 120 |
| Null Values Imputed | 14 (via per-tier median replacement) |
| Unit Conversions Applied | 37 (kg → Metric Tons) |
| Label Conflicts Resolved | 9 (case normalization) |
| Duplicate Rows Removed | 2 |

**First 5 Rows of Cleaned Table:**

| Year | Province | Crop Tier | Yield (MT) | Energy Output (MWh) | Waste Generated (kMT) |
|---|---|---|---|---|---|
| 2020 | Davao del Norte | Cacao | 1,240 | 8,420 | 142 |
| 2020 | Davao del Sur | Banana | 5,810 | 6,115 | 98 |
| 2020 | Davao City | Mixed Vegetable | 3,305 | 14,870 | 312 |
| 2021 | Davao del Norte | Cacao | 1,380 | 8,900 | 149 |
| 2021 | Davao del Sur | Banana | 6,120 | 6,440 | 104 |

---

## 2. Visualizations Generated

### Chart A — Cacao & Banana Yield Trend vs. Climate Outlier Years
**Type:** High-contrast multi-series line chart
**Source data:** Davao Region Agricultural Production Index, 2020–2025
**Scope:** Annual output in Metric Tons across three provincial clusters

```
Yield (MT)
21,000 |                                                        ● Banana
       |                                         ○         ○
19,000 |                  ○         ○                  ○
       |     ○
17,000 |                                    ↓ El Niño (2023)
       |
 5,500 |                                                   ● Cacao
       |              ●         ●                  ●
 4,500 |   ●                            ↓
       |                            ●
       +----+-----+-----+-----+-----+-----+
           2020  2021  2022  2023  2024  2025
```

*(Embedded high-contrast line chart — Cacao & Banana Production vs. Climate Outlier Years, 2020–2025)*

**Key observations:**
- Cacao yield peaked at 5,340 MT in 2022, then dropped 18% to 4,380 MT in 2023 coinciding with El Niño
- Banana yield followed a parallel decline from 20,100 MT to 17,600 MT in the same window
- Both crops recovered strongly in 2024–2025, suggesting resilience when climate pressure subsided

---

### Chart B — Municipal Waste Generation by Province (Stacked Bar)
**Type:** High-contrast stacked bar chart
**Source data:** Davao Region Environmental Monitoring Dataset, 2020–2025
**Scope:** Annual waste generation in thousand Metric Tons (kMT)

```
Waste (kMT)
900 |                             ████
    |                        ████████
800 |               ████████████████
    |          ████████████████████
700 |     ████████████████████████████
    |████████████████████████████████
    +----+-----+-----+-----+-----+-----+
        2020  2021  2022  2023  2024  2025

    ████ Davao City   ████ Davao del Norte   ████ Davao del Sur
```

*(Embedded high-contrast stacked bar chart — Municipal Waste Generation by Province, 2020–2025)*

**Key observations:**
- Total regional waste rose from 552 kMT in 2020 to 691 kMT in 2025
- A notable spike across all three clusters occurred in 2023, coinciding with the El Niño period
- Davao City consistently accounts for the largest share (~55–58% of total)

---

## 3. Human Analytical Narrative — The "Why" Factor

The trend data reveals a clear and troubling pattern: smallholder cacao output in the Davao cluster recorded an **18% decline** centered on late 2023. While the automated AI analysis initially attributed this drop to standard market volatility, human cross-referencing of local news archives reveals this period matched a **severe regional El Niño weather event** that gripped Mindanao from mid-2023 through early 2024 — reducing soil moisture levels and disrupting flowering cycles across highland cacao farms in Davao del Norte and del Sur.

Simultaneously, municipal waste generation spiked across all three provincial clusters in 2023, which at first glance appears counterintuitive. However, this is explainable: **emergency food relief operations** and increased single-use packaging from disaster-response logistics drove the uptick, revealing the indirect environmental cost of climate-induced agricultural crises. The data signal is not just economic — it is socio-environmental.

These findings emphasize the urgent need for NEDA and local LGUs to invest in two convergent priorities. First, **climate-resilient irrigation infrastructure** — particularly solar-powered drip systems for smallholder farms in Davao del Norte and del Sur — to buffer against the yield volatility that El Niño events introduce. Second, **integrated solid waste management capacity** that can scale during disaster response periods, rather than operating only under baseline conditions.

Budget allocations that treat agriculture and waste management as isolated departmental line items will continue to miss this compounding dynamic. The data argues for cross-departmental emergency planning that accounts for both food production vulnerability and secondary waste impacts within the same climate event window. A coordinated regional resilience fund — modeled after the DILG Sagana at Ligtas na Tubig sa Lahat framework but extended to agricultural and solid waste infrastructure — would be the most actionable structural response the data currently supports.

---

*Prepared by the Regional Data Analytics Unit · Davao Regional Development Council · June 2025*
*Dataset: Davao Region Agricultural & Environmental Production Index (Mock CSV Analysis)*

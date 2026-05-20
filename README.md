# IslandGuard-Insurance-Dashboard
End-to-end Power BI dashboard for IslandGuard Insurance Ltd (Mauritius) — Premium performance, risk analysis, and customer retention insights. Features a 7-table star schema, 12+ custom DAX measures, and a strong focus on surrender rate &amp; retention challenges

## How to Open It

1. Download the `.pbix` file
2. Open in Power BI Desktop
3. Use the slicers (Policy Type, District, Agent, Occupation, Year) to explore
4. Risk & Retention page has its own filter logic  Surrendered and Lapsed policies appear there even though Active-only is applied everywhere else


## What This Is

A 3-page Power BI dashboard built for a fictional Mauritian life insurance company IslandGuard Insurance Ltd.

I built the dataset from scratch. There was no data handed to me I started with blank Excel templates and populated 10,000 policy records myself, localised to the Mauritius market (districts, occupations, MUR currency, agent names). From there I modelled it as a 7-table star schema, wrote 12+ DAX measures, and built the dashboard across three pages aimed at three different audiences.

The insurance domain was deliberate. The analytical framework here ,risk segmentation, premium analysis, retention modelling maps directly to banking, reinsurance, and financial services, which is where I want to work.

---

## The Dashboard

| Page | Who It's For | What It Shows |
| Executive Summary | CFO / Senior Leadership | Portfolio KPIs, premium pipeline, interactive policy explorer |
| Insurance Overview | Analysts & Sales Management | Premium by product, district, agent, and year |
| Risk & Retention | Risk & Retention Teams | Surrender rate, lapse analysis, at-risk policies by agent |

---

## What the Data Showed

The headline number is the surrender rate: **25.21%** against an industry benchmark of 8 -12%. That's not a rounding error ,it means IslandGuard is losing **MUR 637.9 million** in annual premium to policy exits.

What made this interesting analytically is *where* the problem sits. The surrender rate is consistent across every tenure band — 24–27% whether the policy is 5 years or 25 years old. That rules out product design as the cause. It points to something systemic: service quality, pricing, or competitive pressure.

A few other things the data surfaced:

- Port Louis generates 31% of total premium - heavy geographic concentration
- Quatre Bornes, Plaines Wilhems, and Flacq have the highest churn despite being urban, higher-income districts
- Whole Life policies make up 37.3% of annual premium - meaningful concentration risk if the market shifts toward investment-linked products
- Premium growth plateaued after 2022, which suggests the core districts are close to saturation

---

## Technical Notes

**Data model:** Star schema - 1 fact table, 6 dimension tables, 6 relationships. Built to be production-ready, not just demo-ready.

**DAX:** 12 measures covering annualised premium, CAGR, surrender rate, lapse rate, premium lost, maturity liability, ROI, and more. SUMX used throughout for row-level iteration. CAGR implemented as `POWER(EndValue/StartValue, 1/Tenure) - 1` with an IF guard for zero-tenure edge cases. VAR blocks used in every complex measure.

**Power Query:** Five data issues caught and fixed during profiling - including a broken agent relationship that was making every agent show equal premium values, and a missing Monthly case in the payment frequency SWITCH that was silently returning blanks across multiple columns.

**Filter context:** Report-level filter (Active policies only) with a page-level override on Risk & Retention to expose Surrendered and Lapsed records.



## Full Write-Up

The PDF contains dashboard visuals, KPI explanations, business findings, and the full analytical walkthrough.



## Stack

Power BI Desktop , DAX , Power Query (M) , Excel , Star Schema , GitHub

---

## Author

**Isheanesu William Zinyuke**
MSc Data Analytics · 2026

---

*All data is fictitious and created for portfolio purposes only.*

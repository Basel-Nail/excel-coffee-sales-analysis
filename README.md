# Coffee Bean Sales & Profitability Analysis (End-to-End Excel)

## Business Objective
Analyze 3.5+ years of multi-market coffee bean order data (Jan 2019 – Aug 2022) to identify top-performing coffee varieties, pack sizes, geographic markets, and customer loyalty patterns—translating raw transactional tables into pricing, promotion, and data-capture recommendations.

## Dataset & Workbook Architecture
- **Source Tables:** 3 relational tables (`orders` with 1,000 order lines / 957 unique orders, `customers` with 1,000 profiles, and `products` with 48 SKUs across 4 bean varieties, 3 roast levels, and 4 bag sizes).
- **Workbook Tabs:**
  1. `Executive_Dashboard` — Dynamic KPI cards, 4 visual charts, and strategic recommendations.
  2. `Summary_Tables` — Dynamic `SUMIF` / `COUNTIF` performance tables across product, geography, time, and loyalty dimensions.
  3. `orders` — Enriched transactional table using `INDEX/MATCH`, `TRIM`, `IFERROR`, `YEAR`, and `TEXT` formulas.
  4. `customers` & `products` — Reference dimension tables.
  5. `Data_Cleaning_Notes` — Audit log of data quality checks, null handling, and calculated metric definitions.

## Data Cleaning & Preparation
- **Relational Enrichment:** Joined customer attributes (`Country`, `City`, `Loyalty Card`) and product attributes (`Coffee Type`, `Roast Type`, `Size`, `Unit Price`, `Unit Profit`) into `orders` via `INDEX/MATCH`.
- **Null & Text Standardization:** Wrapped customer names in `TRIM()`, standardized column naming (`City`), and updated email lookups with `IF(...="","")` after identifying **204 customer records (20.4%)** with missing emails and **130 (13.0%)** with missing phone numbers.
- **Metric Engineering:** Computed line-level `Profit` (Unit Profit × Quantity) and `Margin %` (Profit / Sales) across all 1,000 order lines, and flagged 2022 as partial-year data (Jan–Aug) for accurate YoY comparisons.

## Key Analytical Findings
- **Revenue vs. Margin Divergence by Bean Type:** **Excelsa** generated the highest revenue (**$12,318.70**, **11.0%** margin), while **Liberica** delivered the highest total profit (**$1,567.03**, **13.0%** margin) on lower unit volume. **Robusta** generated **$9,029.20** in sales at only a **6.0%** margin.
- **Bulk Pack Sizes Dominate Revenue:** The **2.5 kg** bag accounts for **52.6%** of total revenue (**$23,797.30**) across 841 units, compared to just **7.3%** (**$3,322.20**) from 0.2 kg bags.
- **Market Concentration & Growth:** The **United States** drives **79.0%** of total sales (**$35,708.20**), followed by **Ireland** (**14.8%**, **$6,710.80**) and the **United Kingdom** (**6.2%**, **$2,803.70**). Full-year revenue grew **+13.6% YoY** from 2020 (**$12,139.60**) to 2021 (**$13,794.10**).
- **Loyalty Program & CRM Gaps:** Loyalty cardholders represent **47.9%** of order lines (**$20,956.50**) with a slightly lower average order line (**$43.75** vs. **$46.58** for non-members), while **20.4%** of customers lack email addresses on file.

## Business Recommendations
1. **Optimize Product Mix & Margins:** Highlight high-margin **Liberica (13.0%)** and **Excelsa (11.0%)** in featured bundles, and audit **Robusta (6.0%)** supplier pricing or retail price points.
2. **Drive Bulk Pack Upgrades:** Target repeat **1.0 kg** buyers with multi-bag or volume-tier discounts to shift orders toward higher-ticket **2.5 kg** bags.
3. **Upgrade Loyalty Mechanics & Email Capture:** Introduce mandatory/incentivized email capture at checkout and tie loyalty perks to order size thresholds rather than flat discounts.

## Tools & Excel Functions Used
`INDEX/MATCH` · `SUMIF` · `COUNTIF` · `IFERROR` · `TRIM` · `ROUND` · `YEAR` · `TEXT` · Dynamic Charts · Conditional Formatting

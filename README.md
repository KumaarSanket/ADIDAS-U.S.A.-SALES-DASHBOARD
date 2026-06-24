# ADIDAS-U.S.A.-SALES-DASHBOARD
# 📊 Adidas US Sales Performance Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Level](https://img.shields.io/badge/Level-Beginner-22C55E?style=for-the-badge)
![Records](https://img.shields.io/badge/Records-9%2C648-0284C7?style=for-the-badge)
![Revenue](https://img.shields.io/badge/Revenue-$899.9M-1B3A8A?style=for-the-badge)

![Adidas Dashboard](adidas-dashboard.jpeg)
![Adidas Dashboard](ADIDAS%20U.S.A.%20SALES%20DASHBOARD.jpeg)


---

## 📌 Project Overview

Processed 9,648 Adidas US sales records spanning 24 months (Jan 2020–Dec 2021) through a structured Power Query ETL pipeline — achieving 100% data integrity with zero nulls across 13 columns. • Engineered 4 DAX measures and built a 12-visual interactive dashboard covering retailer performance, regional breakdown, product mix, monthly trends, and geographic distribution across 50 US states. • Analyzed $899.9M total revenue and $332.13M operating profit (42.30% avg margin), surfacing a 294.23% YoY revenue growth from 2020 to 2021 and identifying Online as the highest-margin sales channel at 38.98%.

---

## 🎯 Problem Statement

Adidas US sales data existed as a flat, unstructured Excel file with no reporting layer. Stakeholders had zero visibility into which retailers, regions, or product categories were driving revenue and profit — nor any mechanism to compare year-on-year performance, evaluate channel profitability, or identify underperforming geographies across a $899.9M revenue portfolio.

---

## 🎯 Objectives

- Transform raw Excel data into a clean, analysis-ready dataset via Power BI Power Query ETL
- Create 4 DAX measures enabling dynamic aggregation of revenue, profit, units, and margin
- Build a 12-visual interactive dashboard across retailer, region, product, channel, and geography dimensions
- Enable real-time drill-down via 3 dynamic slicers (Region, Retailer, Sales Method)
- Surface actionable insights identifying top and bottom performers across all business segments
- Deliver a portfolio-ready report with 3 custom JSON themes (Light, Dark, Mixed)

---

## 📁 Dataset

| Attribute | Detail |
|-----------|--------|
| **Name** | Adidas US Sales Dataset |
| **Source** | [Kaggle — heemalichaudhari/adidas-sales-dataset](https://www.kaggle.com/datasets/heemalichaudhari/adidas-sales-dataset) |
| **Format** | Microsoft Excel Workbook (.xlsx) |
| **Records** | 9,648 rows · 13 columns |
| **Date Range** | January 2020 – December 2021 (24 months) |
| **Geography** | 50 US States · 52 Cities · 5 Regions |
| **Null Values** | Zero — 100% complete dataset |

### Columns

| Column | Type | Description |
|--------|------|-------------|
| Retailer | Text | 6 retail partners (West Gear, Foot Locker, Sports Direct, Kohl's, Amazon, Walmart) |
| Retailer ID | Whole Number | Unique numeric identifier per retailer |
| Invoice Date | Date | Daily transaction date (Jan 2020–Dec 2021) |
| Region | Text | 5 US regions: Northeast, South, West, Midwest, Southeast |
| State | Text | 50 unique US states |
| City | Text | 52 unique cities |
| Product | Text | 6 categories across Men's/Women's Footwear & Apparel |
| Price per Unit | Decimal | Unit selling price in USD (avg $45.22) |
| Units Sold | Whole Number | Quantity sold per transaction |
| Total Sales | Decimal | Revenue = Price per Unit × Units Sold |
| Operating Profit | Decimal | Profit after operating costs |
| Operating Margin | Percentage | Profit margin per transaction (avg 42.30%) |
| Sales Method | Text | In-store / Outlet / Online |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Primary BI tool — ETL, modelling, DAX, visualisation |
| **Power Query Editor** | ETL pipeline — cleaning, type conversion, header promotion |
| **DAX** | 4 calculated measures for all KPIs |
| **Microsoft Excel (.xlsx)** | Source data format |
| **JSON Theme Files** | 3 custom portfolio themes (Light / Dark / Mixed) |

---

## ⚙️ ETL Process — Power Query (10 Steps)

Executed inside **Power BI Power Query Editor** before loading data into the model:

```
Step 01 → Get Data → Excel Workbook → selected 'Data Sales Adidas' sheet
Step 02 → Clicked 'Transform Data' to open Power Query Editor (NOT Load)
Step 03 → Home → Remove Rows → Remove Top Rows → entered 4
          (removed 'Adidas Sales Database' title + 3 blank separator rows)
Step 04 → Home → Use First Row as Headers
          (promoted correct column names from row 5)
Step 05 → Right-clicked Column1 (blank/null) → Remove
          (eliminated empty Excel index column)
Step 06 → Invoice Date column → changed type to Date
Step 07 → Operating Margin column → changed type to Percentage
Step 08 → Price per Unit, Total Sales, Operating Profit → Decimal Number
Step 09 → Units Sold → Whole Number
Step 10 → Home → Close & Apply
          (loaded 9,648 clean rows — 0 errors, 0 nulls, 0 data quality issues)
```

---

## 📐 DAX Measures Created

```dax
Total Revenue = SUM('Data Sales Adidas'[Total Sales])
-- Result: $899,902,125

Total Profit = SUM('Data Sales Adidas'[Operating Profit])
-- Result: $332,134,761

Total Units = SUM('Data Sales Adidas'[Units Sold])
-- Result: 2,478,861

Avg Margin = AVERAGE('Data Sales Adidas'[Operating Margin])
-- Result: 42.30%
```

> ⚠️ **Note:** Measure named `Total Revenue` (not `Total Sales`) to avoid Power BI naming conflict with existing column `Total Sales`.

---

## 📊 Dashboard Visuals (12 Visuals)

| # | Visual Type | Fields | Insight |
|---|-------------|--------|---------|
| 1 | KPI Card | Total Revenue | $899.9M |
| 2 | KPI Card | Total Profit | $332.13M |
| 3 | KPI Card | Total Units | 2,478,861 |
| 4 | KPI Card | Avg Margin | 42.30% |
| 5 | Clustered Bar Chart | Retailer vs Revenue | West Gear #1 at $242.96M |
| 6 | Clustered Bar Chart | Region vs Revenue | West leads at $269.94M |
| 7 | Donut Chart | Product vs Revenue | Men's Street Footwear top at $208.83M |
| 8 | Line Chart | Date vs Revenue | 294.23% YoY growth spike |
| 9 | Filled Map | State vs Revenue | NY, CA, FL top 3 states |
| 10 | Slicer | Region | Cross-filters all 9 visuals |
| 11 | Slicer | Retailer | Cross-filters all 9 visuals |
| 12 | Slicer | Sales Method | Cross-filters all 9 visuals |

---

## 📈 Key Insights & Results

### Revenue & Profitability
- Analyzed **$899,902,125** total revenue and **$332,134,761** operating profit across 9,648 transactions — delivering **42.30% avg operating margin** at **$45.22 avg unit price** across **2,478,861 units sold**.
- Identified **294.23% YoY revenue surge** from $182.08M (2020) → $717.82M (2021), with margin improving from 34.81% to 37.44% — signalling post-pandemic recovery and operational efficiency gains.

### Retailer Performance
- **West Gear ranked #1** at $242.96M revenue (27.0% share); **Sports Direct delivered highest margin at 40.74%** despite ranking 3rd in revenue ($182.47M).
- **Walmart flagged as lowest-margin retailer at 34.58%** on $74.56M revenue — profitability risk at scale; Amazon achieved 37.09% margin via Online channel efficiency ($77.70M).

### Regional Analysis
- **West Region dominated** at $269.94M (30.0% of US total); **South Region achieved highest margin at 42.26%** on $144.66M — outperforming West's 33.20% margin by **9.06 percentage points**.
- Midwest lowest revenue region at $135.80M (15.1% share) — market penetration opportunity.

### Product Mix
- **Men's Street Footwear** generated highest revenue at **$208.83M (23.2% share)** with 39.65% margin and 593,320 units — Adidas' clear US flagship category.
- **Men's Athletic Footwear** carried **lowest margin at 33.74%** — 8.56pp below portfolio average — flagging pricing pressure in the athletic segment.

### Sales Channel
- **Online delivered highest margin at 38.98%** on $247.67M and 939,093 units — highest-priority channel for margin expansion despite ranking 3rd in revenue.
- **In-store led revenue at $356.64M** (39.6% of total) but lowest margin at 35.78% — volume leader with margin drag.

### Geographic Distribution
- **New York ($64.23M), California ($60.17M), Florida ($59.28M)** contributed $183.69M — **20.4% of total US revenue** from just 3 of 50 states.
- **Nebraska ($5.93M), Minnesota ($7.38M)** — bottom 2 states collectively under $14M — flagging upper Midwest market penetration opportunity.

---

## 📊 KPI Summary Table

| KPI | Value | KPI | Value |
|-----|-------|-----|-------|
| Total Revenue | **$899,902,125** | YoY Growth | **294.23%** |
| Total Profit | **$332,134,761** | 2020 Revenue | $182,080,675 |
| Avg Margin | **42.30%** | 2021 Revenue | $717,821,450 |
| Total Units | **2,478,861** | Avg Unit Price | $45.22 |
| Top Retailer | West Gear — $242.96M | Lowest Margin Retailer | Walmart — 34.58% |
| Top Region | West — $269.94M | Highest Margin Region | South — 42.26% |
| Top Product | Men's Street — $208.83M | Lowest Margin Product | Men's Athletic — 33.74% |
| Best Margin Channel | Online — 38.98% | Highest Revenue Channel | In-store — $356.64M |
| Top State | New York — $64.23M | Lowest State | Nebraska — $5.93M |

---

## ⚡ Challenges & Solutions

**Challenge 1 — Malformed Excel Header Structure**
Raw file had 4 junk rows above actual headers causing Power BI to import 'Column1, Column2…'. • Fixed via Power Query: Remove Top Rows (4) → Use First Row as Headers — promoting correct column names before data loaded into the model.

**Challenge 2 — DAX Naming Conflict**
Creating measure named 'Total Sales' triggered error — column with same name already existed. • Resolved by renaming measure to 'Total Revenue', establishing a consistent naming convention separating source columns from calculated measures.

**Challenge 3 — Operating Margin Displaying as Raw Decimal**
Values like 0.42 displayed in visuals instead of 42%. • Fixed by changing column type to Percentage in Power Query — corrected at source level, propagating correctly to all visuals automatically.

**Challenge 4 — Blank Column Pollution**
Excel index column appeared as 'Column1' full of nulls in the field pane. • Removed in Power Query before Close & Apply — eliminated from the data model entirely, never polluting the field pane.

**Challenge 5 — Manual Formatting at Scale**
Formatting 12 visuals manually would require 60+ individual changes. • Solved by authoring 3 custom JSON theme files — single import via View → Themes → Browse instantly re-themed all visuals simultaneously.

---

## 🎓 Skills Learned

- **Power Query ETL** — 10-step cleaning pipeline; Remove Top Rows, Use First Row as Headers, data type corrections, column removal; fully repeatable via Applied Steps
- **DAX Fundamentals** — SUM(), AVERAGE() measures; measure vs column distinction; naming conflict resolution
- **Data Type Management** — Impact of Decimal vs Percentage on visual rendering; importance of fixing types at source
- **Visual Composition** — 12-visual dashboard layout balancing KPIs, comparisons, trends, geography, and filters
- **Cross-Filter Interactions** — Power BI default cross-filtering between visuals; slicer-driven multi-dimensional filtering
- **Custom JSON Theming** — Authored theme files (dataColors, visualStyles, page background) for professional portfolio aesthetics
- **Business Insight Extraction** — Translated raw transactions into executive-level findings across 4 business dimensions

---

## 🎨 Custom Themes

Three custom Power BI JSON themes included for professional dashboard styling:

| Theme | Style | Best For |
|-------|-------|---------|
| `Theme_1_Arctic_Pro_Light.json` | ☀️ Light — Navy + Sky Blue | Office, client reports, presentations |
| `Theme_2_Command_Center_Dark.json` | 🌑 Dark — Deep Navy + Cyan | TV screens, demos, executive briefings |
| `Theme_3_Fusion_Indigo_Mix.json` | 💜 Mixed — Silver + Indigo | Portfolio, unique aesthetic |

**To apply:** Power BI → View → Themes → Browse for themes → select JSON file

---

## 📂 Repository Structure

```
adidas-us-sales-dashboard/
│
├── 📊 Adidas_Sales_Dashboard.pbix          # Power BI dashboard file
├── 📁 Dataset/
│   └── Adidas_US_Sales_Datasets.xlsx       # Raw source data (Kaggle)
├── 📁 Themes/
│   ├── Theme_1_Arctic_Pro_Light.json
│   ├── Theme_2_Command_Center_Dark.json
│   └── Theme_3_Fusion_Indigo_Mix.json
├── 📄 Adidas_US_Sales_Portfolio_Documentation.pdf   # Full portfolio doc
└── 📄 README.md
```

---

## 🚀 How to Use

```
1. Download Adidas_US_Sales_Datasets.xlsx from Kaggle link above
2. Open Adidas_Sales_Dashboard.pbix in Power BI Desktop
3. If prompted, update the data source path to your local file location
4. Click Refresh to reload data
5. Apply any theme: View → Themes → Browse for themes → select JSON file
6. Use Region / Retailer / Sales Method slicers to explore the data
```

---

---

*Data Analytics · Power BI · K.S. *

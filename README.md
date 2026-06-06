# UrbanStyle Apparel — Fashion Pricing Analysis

> Analysing 1,428 t-shirt SKUs across 143 brands to uncover 
> discount manipulation, tier profitability, and brand performance 
> on Indian e-commerce.

---

## Problem Statement

Indian e-commerce platforms advertise discounts of 60–90%. 
This project investigates whether these represent genuine markdowns 
or artificially inflated MRPs — and which brands and tiers are 
actually profitable.

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| Azure SQL | Data storage and cleaning |
| SQL (UPDATE, REPLACE, TRIM, CAST) | Removing special characters from price fields |
| Power BI Desktop | Data modelling, DAX measures, dashboard design |
| Power BI Service | Publishing for live interactive access |
| DAX | 12 measures for pricing, profitability, discount analysis |


urbanstyle-apparel-pricing-analysis/
├── sql/
│   └── data_cleaning.sql     # Azure SQL cleaning queries
├── dashboard/
│   └── screenshots/          # All 3 dashboard page screenshots
├── docs/
│   ├── TShirt_Project_Documentation.pdf
│   └── UrbanStyle_LinkedIn_Document.docx
├── data/
│   └── README.md            
└── README.md

---

## Data Cleaning — Azure SQL

Both price columns (Sale Price and MRP) were stored as text 
with `?` characters embedded. Cleaned using:

```sql
UPDATE [dbo].[Men Tshirt]
SET original_price = TRIM(REPLACE(CAST(original_price AS varchar(max)), '?', ''))
WHERE original_price LIKE '%?%'
```
1,428 rows affected on both columns.

---

## Data Model

- **Star Schema** — 1 Fact table + 1 Dimension table
- **T-Shirt Products** (Fact) — 1,428 rows
- **Brand Tier Reference** (Dimension) — 143 brands
- Linked via `Brand` column (Many-to-One)

---

## Key Numbers

| Metric | Value |
|--------|-------|
| Total SKUs | 1,428 |
| Total Brands | 143 |
| Avg Sale Price | Rs.1,034 |
| Avg Discount % | 57.1% |
| MRP Inflation Ratio | 2.32x |
| Extreme Discount % (70%+) | 26.5% |
| Avg Profit Per Unit | Rs.243 |
| Luxury Profit Per Unit | Rs.1,586 |
| Budget Profit Per Unit | Rs.99 |

---

## Dashboard Screenshots

### Page 1 — Catalog Overview
![page3-brand-intelligence.png
](https://github.com/Tahseenahhamza/tshirt-market-analysis-powerbi/blob/main/Overview.png)
### Page 2 — Discount & Profitability
![Page 2](dashboard/screenshots/page2-discount-profitability.png)

### Page 3 — Brand Intelligence
![Page 3](dashboard/screenshots/page3-brand-intelligence.png)

---

## Key Findings

1. MRP is inflated **2.32x** on average — discounts are manufactured
2. **1 in 4 SKUs** carries a 70%+ discount — fake anchor pricing is widespread
3. Luxury tier earns **Rs.1,586/unit** from 58 SKUs vs Budget's Rs.99 from 560 SKUs
4. International brands earn **4x more profit** per unit than domestic brands
5. The Indian Garage Co has 184 SKUs but earns only Rs.77/unit — lowest among top 10

---

## Live Dashboard

[View Interactive Dashboard on Power BI Service](your-link-here)

---

## Author

**Tahseenah Hamza** — Data Analyst  
tahseenahhamza@gmail.com  
[LinkedIn](https://linkedin.com/in/tahseenah-hamza)

> Raw data and .pbix file not shared intentionally.  
> This repository is for portfolio display only.

---

## Project Structure

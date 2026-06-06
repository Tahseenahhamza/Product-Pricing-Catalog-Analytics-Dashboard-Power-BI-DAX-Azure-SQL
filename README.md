# 👕 UrbanStyle Apparel Analytics Dashboard

### Pricing Intelligence | Discount Analysis | Brand Profitability

An end-to-end retail analytics project built using **Azure SQL**, **Power BI**, and **DAX** to investigate pricing behaviour, discount strategies, and brand profitability across men's apparel listings on a leading Indian e-commerce platform.

---

## 🔗 Quick Access

| Resource          | Link                                                                                                             |
| ----------------- | ---------------------------------------------------------------------------------------------------------------- |
| 📊 Live Dashboard | https://app.fabric.microsoft.com/links/XqlYtGqsAd?ctid=56c1d497-700b-49cf-8f8d-3dd6b20d522f&pbi_source=linkShare |
| 💼 LinkedIn       | https://linkedin.com/in/tahseenah-hamza                                                                          |
| 💻 GitHub         | https://github.com/Tahseenahhamza                                                                                |

---

# 📌 Project Overview

Indian e-commerce platforms frequently advertise discounts ranging from **60% to 90%**. While these discounts appear attractive to customers, an important business question remains:

### Are these discounts genuine markdowns or the result of artificially inflated MRPs?

This project analyzes **1,428 T-shirt SKUs across 143 brands** to uncover pricing patterns, evaluate profitability, identify discount manipulation, and generate actionable business recommendations.

---

# 📊 Executive Summary

### Key Highlights

| Metric                           | Value  |
| -------------------------------- | ------ |
| Total Products                   | 1,428  |
| Total Brands                     | 143    |
| Average Sale Price               | ₹1,034 |
| Average Discount                 | 57.1%  |
| MRP Inflation Ratio              | 2.32x  |
| Extreme Discount Products (70%+) | 26.5%  |
| Average Profit Per Unit          | ₹243   |
| Luxury Profit Per Unit           | ₹1,586 |
| Budget Profit Per Unit           | ₹99    |

### Key Takeaways

✅ Average MRP is inflated **2.32x** above actual selling prices

✅ **1 in 4 products** carries a discount greater than **70%**

✅ Luxury products generate **16x more profit per SKU** than Budget products

✅ International brands earn **4x more profit per unit** than domestic brands

✅ High SKU volume does not necessarily translate into profitability

---

# 🖼 Dashboard Preview

## Page 1 — Catalog Overview

![Catalog Overview](https://github.com/Tahseenahhamza/tshirt-market-analysis-powerbi/blob/main/Overview.png?raw=true)

### Focus Areas

* Catalog composition
* Tier distribution
* Pricing structure
* Brand concentration
* Profitability overview

---

## Page 2 — Discount & Profitability Analysis

![Discount & Profitability](https://github.com/Tahseenahhamza/tshirt-market-analysis-powerbi/blob/main/Discount%20and%20profitability.jpg?raw=true)

### Focus Areas

* Discount behaviour
* Margin analysis
* Extreme discounting
* Tier profitability
* Pricing discipline

---

## Page 3 — Brand Intelligence

![Brand Intelligence](https://github.com/Tahseenahhamza/tshirt-market-analysis-powerbi/blob/main/Brand%20Intelligence.jpg?raw=true)

### Focus Areas

* Brand benchmarking
* Domestic vs International comparison
* Pricing strategy analysis
* Profitability benchmarking

---

# 🔍 Key Business Findings

## 1️⃣ MRP Inflation Is Systemic

The average MRP across the catalog is inflated by **2.32x** relative to actual selling prices.

This indicates that discounts are often created through artificially elevated reference prices rather than genuine markdowns.

The average displayed discount of **57.1%** reflects a pricing strategy rather than temporary promotional activity.

---

## 2️⃣ One In Four Products Relies On Extreme Discounting

**26.5% of all SKUs** carry discounts exceeding **70%**.

This means more than one out of every four products depends on aggressive discount messaging to create perceived value.

Several brands consistently operate using high-discount pricing structures.

---

## 3️⃣ Volume Does Not Equal Profitability

| Tier   | SKU Count | Profit Per Unit |
| ------ | --------- | --------------- |
| Budget | 560       | ₹99             |
| Luxury | 58        | ₹1,586          |

Luxury products generate approximately **16x more profit per SKU** than Budget products.

The analysis demonstrates that catalog volume alone is a poor indicator of business performance.

---

## 4️⃣ International Brands Significantly Outperform Domestic Brands

| Brand Type    | Avg Profit Per Unit |
| ------------- | ------------------- |
| Domestic      | ₹141                |
| International | ₹575                |

International brands generate approximately **4x higher profit per unit** while requiring lower discount levels.

This suggests that brand equity contributes more to profitability than catalog size.

---

## 5️⃣ High Catalog Presence Does Not Guarantee Returns

The Indian Garage Co contributes:

* 184 SKUs
* 12.9% of catalog volume

Despite this scale, it delivers among the lowest profit-per-unit values within the top-performing brands.

This highlights the risk of evaluating performance based solely on product count.

---

## 6️⃣ Economy Tier Shows Weak Strategic Performance

The Economy tier exhibits:

* Highest average discount levels
* Highest MRP inflation
* Low profitability
* Limited catalog representation

The tier fails to contribute meaningfully to either volume leadership or profitability leadership.

---

# 💡 Business Recommendations

## Expand Premium & Luxury Assortment

Luxury products generate significantly higher margins despite low catalog representation.

### Expected Impact

* Higher profitability
* Better margin quality
* Improved brand perception
* Stronger premium positioning

---

## Introduce MRP Inflation Controls

Implement catalog governance rules where products exceeding predefined inflation thresholds require manual review.

### Example Rule

MRP should not exceed **3x actual selling price** without justification.

### Expected Impact

* Increased pricing transparency
* Improved customer trust
* Reduced dependency on artificial discounts

---

## Reassess Economy Tier Strategy

The Economy tier demonstrates:

* High discount dependence
* Low profitability
* Limited strategic value

### Potential Actions

* Merge with Budget tier
* Remove low-performing SKUs
* Reallocate inventory investment

### Expected Impact

* Improved catalog efficiency
* Higher average margins
* Reduced complexity

---

## Increase International Brand Partnerships

International brands consistently outperform domestic competitors on profitability metrics.

### Expected Impact

* Increased profit per unit
* Improved pricing power
* Stronger premium brand mix

---

## Monitor Extreme Discount Products

Products carrying discounts above 70% should be reviewed regularly.

### Expected Impact

* Healthier pricing strategy
* Improved customer confidence
* Sustainable profitability

---

# ⚙ Technical Approach

## Data Preparation — Azure SQL

The raw dataset contained pricing fields stored as text with embedded special characters.

### Data Cleaning Activities

* Removed special characters from pricing fields
* Standardized data types
* Converted price columns to numeric format
* Prepared dataset for Power BI modelling

### SQL Techniques Used

```sql
UPDATE
REPLACE
TRIM
CAST
```

---

## Data Model

### Star Schema Design

#### Fact Table

**T-Shirt Products**

* 1,428 SKU-level records
* Product attributes
* Pricing information
* Profit metrics

#### Dimension Table

**Brand Tier Reference**

* Brand
* Tier Classification
* Brand Origin
* Domestic vs International Flag

### Relationship

```text
T-Shirt Products[Brand]
            │
            ▼
Brand Tier Reference[Brand]
```

---

## Power BI Development

### Dashboard Features

* Interactive slicers
* KPI cards
* Scatter plots
* Comparative analysis
* Dynamic filtering
* Brand benchmarking

### DAX Measures

* Total Products
* Total Brands
* Average Sale Price
* Average Discount %
* Average Profit Per Unit
* MRP Inflation Ratio
* Extreme Discount %
* Profit Margin %
* Tier Performance Metrics

---

# 🚀 Future Enhancements

## Version 2.0

* Revenue analysis using units sold
* Time-series trend analysis
* Profit forecasting
* Dynamic pricing monitoring

## Version 3.0

* Multi-category retail analysis
* Cross-platform comparison
* Predictive pricing model
* Customer segmentation analysis

---

# 🛠 Tech Stack

| Category       | Technology       |
| -------------- | ---------------- |
| Database       | Azure SQL        |
| Query Language | SQL              |
| Data Modeling  | Star Schema      |
| Visualization  | Power BI         |
| Analytics      | DAX              |
| Reporting      | Power BI Service |

---

# 🎯 Skills Demonstrated

### Analytics

* Pricing Analytics
* Profitability Analysis
* Retail Analytics
* Business Intelligence
* Data Storytelling

### Technical

* Azure SQL
* SQL Data Cleaning
* Data Modeling
* DAX
* Power BI
* Dashboard Design

### Business

* Executive Reporting
* KPI Development
* Strategic Recommendations
* Catalog Optimization
* Brand Performance Analysis

---

# 📊 Live Dashboard

### View Interactive Power BI Dashboard

https://app.fabric.microsoft.com/links/XqlYtGqsAd?ctid=56c1d497-700b-49cf-8f8d-3dd6b20d522f&pbi_source=linkShare

---

# 👩‍💻 Author

## Tahseenah Hamza

Data Analyst | SQL | Power BI | Python | Data Storytelling

📧 [tahseenahhhamza@gmail.com](mailto:tahseenahhhamza@gmail.com)

🔗 LinkedIn: https://linkedin.com/in/tahseenah-hamza

🔗 GitHub: https://github.com/Tahseenahhamza

---

> This repository is intended for portfolio and learning purposes. The Power BI dashboard is publicly accessible through the live dashboard link above.

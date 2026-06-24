# Online Retail Sales & Revenue Analysis

An end-to-end data analytics project exploring over 540,000 transactional records from a UK-based gift wholesaler. The analysis covers data cleaning, exploratory data analysis (EDA), and an interactive Power BI dashboard — built using Python and Power BI.

---

## 📁 Repository Structure

```
├── sales_performance.ipynb       # Python notebook — data cleaning & EDA & visualizations
├── clean_retail.zip              # Cleaned dataset (zipped CSV)
├── online sales dashboard.png    # Power BI dashboard screenshot
└── README.md
```

---

## 🔍 Project Overview

| Detail | Info |
|---|---|
| **Dataset** | UCI Online Retail Dataset |
| **Period** | December 2010 — December 2011 |
| **Raw rows** | 541,909 |
| **Clean rows** | 536,638 |
| **Tools** | Python, Power BI |
| **Focus** | Revenue trends, product performance, geographic analysis, time patterns, customer type |

The dataset contains transactional records for a UK-based wholesale gift supplier selling to business customers across the UK and internationally. Each row represents a single line item in an order, with columns for invoice number, product code, description, quantity, unit price, customer ID and country.

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| Python (Google Colab) | Data cleaning, EDA, visualizations |
| pandas | Data manipulation and cleaning |
| matplotlib & seaborn | Data visualization |
| Power BI | Interactive dashboard |
| DAX | KPI measures in Power BI |

---

## 🧹 Data Cleaning Summary

| Category | Issue Found | Action Taken | Rows Affected | Status |
|---|---|---|---|---|
| Missing values | 135,080 missing CustomerIDs | Retained — guest checkouts have valid revenue data | 135,080 | Kept |
| Missing values | 1,454 missing Descriptions | Filled using StockCode lookup from existing rows | 1,454 | Filled |
| Duplicates | 5,226 rows flagged | Investigated and found to be legitimate invoice line items — same InvoiceNo is expected across multiple rows as one order can contain many products. No rows removed | 5,226 | No action |
| Invalid entries | 9,288 cancellation rows (InvoiceNo starting with C) | Removed — cancellations are not real sales | 9,288 | Removed |
| Invalid entries | Rows with Quantity or UnitPrice ≤ 0 | Removed — not valid sales transactions | ~10,000 | Removed |
| Standardization | InvoiceDate stored as string, CustomerID as float | InvoiceDate parsed to datetime, CustomerID converted to integer | All rows | Applied |
| Feature engineering | No Revenue, YearMonth, DayOfWeek, Hour or CustomerType columns | Derived columns created from existing fields | All rows | Applied |

---

## 📊 Key Insights

**Revenue & Sales Trends**
- Total revenue over the 13-month period was **£10.6M**
- Revenue followed a clear seasonal pattern with a significant Q4 spike
- **November 2011** was the strongest month at approximately **£1.5M**, driven by Black Friday and pre-Christmas demand
- Average order value was stable at **£430–£580** per month, spiking to **£780** in December

**Geography**
- The **United Kingdom** dominates revenue — consistent with the business being a UK-based wholesaler
- Top international markets are **Netherlands, EIRE (Ireland), Germany and France**

**Products**
- **DOTCOM POSTAGE** appears as the top product by revenue but is a shipping charge, not a real product
- **PAPER CRAFT, LITTLE BIRDIE** leads both revenue and quantity sold (~80,000 units) — a high-volume, high-value product
- **REGENCY CAKESTAND 3 TIER** is a premium item with high revenue but lower volume

**Operations & Time Patterns**
- The business operates **Monday to Friday only** — no transactions on Saturdays, consistent with a B2B wholesale model
- **Thursday** is the busiest day for orders
- **Peak ordering time is 12 noon**, with activity starting at 6am and tapering off after 8pm

**Customer Type**
- **Registered customers** account for ~£8.9M (**84%**) of total revenue
- **Guest checkouts** contribute ~£1.7M (**16%**) — a meaningful share that should not be ignored

---

## 📈 Visualizations (Python)

The following charts were produced in Python using matplotlib and seaborn:

1. Monthly Revenue
2. Average Order Value by Month
3. Orders by Day of Week
4. Orders by Hour of Day
5. Weekly Revenue Heatmap (Day vs Week)
6. Top 11 Countries by Revenue
7. Top 10 Countries by Revenue (excl. UK)
8. Revenue by Country — Guest vs Registered
9. Top 10 Products by Revenue
10. Top 10 Products by Quantity Sold
11. Invoice Revenue Distribution (log scale)
12. Guest vs Registered Customer Revenue

---

## 🖥️ Dashboard Preview

![Online Retail Sales Dashboard](online%20sales%20dashboard.png)

The Power BI dashboard is structured across 3 pages:

**Page 1 — Revenue Overview**
KPI cards, Monthly Revenue line chart with average line, Waterfall chart and Decomposition tree

**Page 2 — Product & Country Analysis**
Filled map, Treemap, Top products by revenue and quantity

**Page 3 — Time & Operations**
Matrix heatmap (Day vs Hour), Orders by day and hour, Guest vs Registered breakdown

---

## ▶️ How to Run

**Python Notebook**
1. Open `sales_performance.ipynb` in Google Colab or Jupyter Notebook
2. Upload `clean_retail.zip` and unzip to get `clean_retail.csv`
3. Run all cells in order — the notebook covers loading, cleaning, EDA and visualizations

**Requirements**
```
pandas
numpy
matplotlib
seaborn
```

Install with:
```bash
pip install pandas numpy matplotlib seaborn
```

---

## 📦 Dataset

- **Source:** [UCI Machine Learning Repository — Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/online+retail)
- **Citation:** Dr Daqing Chen, Course Director: MSc Data Science, School of Engineering, London South Bank University

---

*Analysis conducted using Python and Power BI*

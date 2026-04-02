# 🛒 Global Electronics Retailer — Sales Analytics Dashboard

A dynamic, end-to-end sales analytics project built for a global electronics retailer. Developed using Python, PostgreSQL, and Power BI — covering the complete analytics pipeline from raw multi-source data to an interactive business intelligence dashboard.

---

## 2. Short Description / Purpose

This project integrates 6 real-world datasets (Sales, Products, Customers, Stores, Exchange Rates, and Data Dictionary) into a single master dataset of 24,344 records. The goal is to analyze global sales performance across products, customers, stores, and regions — and deliver actionable business insights through an interactive Power BI dashboard.

---

## 3. Tech Stack

The project was built using the following tools and technologies:

- 🟢 **Excel** — Initial data exploration and sanity checks across all 6 datasets.
- 🐍 **Python (Pandas, NumPy, Matplotlib, Seaborn)** — Data cleaning, transformation, merging, EDA, and currency normalization.
- 🐘 **PostgreSQL** — Data querying, aggregations, and relational data exploration.
- 📊 **Power BI Desktop** — Star schema data model, DAX measures, KPI cards, and interactive dashboard.
- 🗂️ **File Formats** — `.csv` for raw/cleaned data, `.pbit` for the dashboard template, `.png` for preview.

---

## 4. Data Source

- **Dataset:** Global Electronics Retailer (publicly available)
- **Number of Source Files:** 6 CSV files
- **Final Master Dataset:** 24,344 rows × 27 columns
- **Data Coverage:** Sales transactions, product catalog, customer demographics, store locations, and daily currency exchange rates

| File | Rows | Description |
|------|------|-------------|
| `Sales.csv` | 62,884 | Core transactional fact data |
| `Products.csv` | 2,517 | Product details, categories, pricing |
| `Customers.csv` | 15,266 | Customer demographics and location |
| `Stores.csv` | 67 | Store location and size |
| `Exchange_Rates.csv` | 11,215 | Daily currency exchange rates (to USD) |
| `Data_Dictionary.csv` | 37 | Field descriptions and metadata |

---

## 5. Features / Highlights

**Business Problem:** A global electronics retailer operating across multiple countries and currencies needed a unified view of sales performance — by product, region, store, and customer segment — to support data-driven decisions.

**Goal of the Dashboard:** To deliver an interactive Power BI report that tracks revenue, identifies top-performing products and regions, and reveals customer purchasing patterns — all normalized to USD for fair comparison.

**Walkthrough of Key Visuals:**

- **KPI Cards (Top Row):**
  - Total Sales (USD): **$22M**
  - Average Order Value: **$2K**
  - Total Orders: **10K**
  - Unique Customers: **7K**
  - Unique Products: **2K**

- **Monthly Sales Trend (Line Chart):** Sales declined steadily over the period — a key business insight highlighting the need for strategic intervention.

- **Sales by Product Category (Bar Chart):** Computers lead with **$7.7M**, followed by Home Appliances ($4.5M), Cameras ($2.6M), Cell Phones ($2.5M), and TV & Video ($2.3M).

- **Top 10 Products by Revenue (Bar Chart):** Adventure Works Desktop and WWI Desktop PC series dominate the top 10, each contributing up to **$0.3M** individually.

- **Sales by Customer Gender (Donut Chart):** Near-equal split — Female: **$11.242M (50.07%)** vs Male: **$11.212M (49.93%)**.

- **Slicers:** Interactive filters for Order Date, Category, Country (Store), and Brand — enabling dynamic exploration of all visuals.

- **Insight Banner (Bottom):** *"Sales declined steadily over the period, with the Computers category contributing the highest share of total revenue."*

**Business Impact & Insights:**
- **Computers** is the single highest-revenue category at $7.7M — a clear priority for inventory and marketing investment.
- Sales show a **steady decline** over the period — warrants investigation into pricing, competition, or demand shifts.
- Gender split is nearly **50/50** — marketing strategies should target both segments equally.
- **Adventure Works** and **WWI** brands dominate the top products list.

---

## 6. Project Pipeline

| Phase | Tool | Description |
|-------|------|-------------|
| 1. Data Understanding | Excel | Explored all 6 datasets — structure, columns, relationships, and data types |
| 2. Data Cleaning | Python (Pandas) | Fixed dates, removed `$` from price columns, handled missing values, standardized column names |
| 3. Data Storage & Querying | PostgreSQL | Relational exploration using SQL joins and aggregations |
| 4. Data Transformation | Python | Merged all 6 datasets, applied currency conversion to USD, created `Final_Sales_Master.csv` |
| 5. Exploratory Analysis | Python (Matplotlib, Seaborn) | Visualized sales by category, time trends, and customer behaviour |
| 6. Dashboard Creation | Power BI | Built star schema model, DAX measures, KPI cards, and interactive visuals |

---

## 7. Data Model (Star Schema — Power BI)

```
Dim_Customers  ──┐
Dim_Products   ──┼──► Fact_Sales
Dim_Stores     ──┘
```

**Fact Table:** `Fact_Sales` — order_number, order_date, quantity, currency_code, sales_value_local, sales_value_usd

**Dimension Tables:**
- `Dim_Customers` — customerkey, gender, city, state, country, continent
- `Dim_Products` — productkey, product_name, brand, category, subcategory
- `Dim_Stores` — storekey, state, country, square_meters, open_date

---

## 8. DAX Measures

```dax
Total Sales (USD) = SUM(Fact_Sales[sales_value_usd])
Total Orders = DISTINCTCOUNT(Fact_Sales[order_number])
Average Order Value = DIVIDE([Total Sales (USD)], [Total Orders])
Total Quantity = SUM(Fact_Sales[quantity])
Unique Customers = DISTINCTCOUNT(Fact_Sales[customerkey])
Unique Products = DISTINCTCOUNT(Fact_Sales[productkey])
```

---

## 9. Key Business Questions Answered

1. What is the total revenue generated across all stores and regions?
2. Which product categories and brands contribute the most to sales?
3. Who are the top 10 revenue-generating products?
4. How do sales trend over time — monthly and yearly?
5. Which countries and regions perform best?
6. What is the average order value and what does it tell us about customer behaviour?
7. How does revenue break down by customer gender?
8. Which currencies contribute the most to sales volume?

---

## 10. Screenshots / Demo

![Global Electronics Retailer Dashboard](Global_Electronics_Retailer.png)

---

## 11. Files in This Repository

| File | Description |
|------|-------------|
| `Sales.csv` | Raw sales transactions dataset |
| `Products.csv` | Raw products dataset |
| `Customers.csv` | Raw customers dataset |
| `Stores.csv` | Raw stores dataset |
| `Exchange_Rates.csv` | Raw exchange rates dataset |
| `Data_Dictionary.csv` | Field descriptions and metadata |
| `Final_Sales_Master.csv` | Cleaned and merged master dataset (24,344 rows × 27 cols) |
| `Global_Electronics_Retailer.pbit` | Power BI Template file |
| `Global_Electronics_Retailer.png` | Dashboard screenshot |
| `README.md` | Project documentation |

---

## 12. Tools & Skills Demonstrated

`Data Cleaning` · `Data Transformation` · `Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `PostgreSQL` · `SQL Joins` · `EDA` · `Currency Normalization` · `Power BI` · `DAX` · `Star Schema` · `Data Modelling` · `Dashboard Design` · `Storytelling with Data`

---

*Dashboard by Sushant Tomar | MCA Graduate | Aspiring Data Analyst*

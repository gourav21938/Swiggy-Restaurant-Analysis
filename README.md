# 🍔 Swiggy Restaurant Analysis — SQL Project

Analyzed 100,000+ restaurants listed on Swiggy across India using SQL.  
Uncovered insights on pricing, ratings, cuisine trends, and city-wise food culture.  
This is **Project 3** of my Data Analyst portfolio.

---

## 📌 Project Overview

| Detail | Info |
|---|---|
| Dataset | Swiggy Restaurants — all restaurants listed on Swiggy India |
| Source | [Kaggle — Swiggy Restaurants Dataset](https://www.kaggle.com/datasets/ashishjangra27/swiggy-restaurants-dataset) |
| Tool | DB Browser for SQLite |
| Rows analyzed | 100,000+ restaurants |
| Cities covered | 800+ cities across India |
| Queries written | 10 |

---

## 💡 Key Insights

| # | Question | Finding |
|---|---|---|
| 1 | Most expensive cities | Khan Market Delhi, Bandra West Mumbai, Jubilee Hills Hyderabad top the list |
| 2 | Best rated cities | Tier-1 cities dominate average ratings |
| 3 | Top cuisines | North Indian, Chinese, and Fast Food are the most listed cuisines |
| 4 | Chain restaurants | A handful of chains appear across the most cities nationwide |
| 5 | Data quality | Found an outlier of ₹18,962 avg cost — cleaned before analysis |

---

## 🧹 Data Cleaning Performed

The dataset had several real-world data quality issues that needed fixing before analysis:

**Issue 1 — Cost column had ₹ symbol and commas**
```sql
CAST(REPLACE(REPLACE(cost, '₹ ', ''), ',', '') AS INTEGER)
```
Solution: Used nested REPLACE to strip symbols, then CAST to convert text to number.

**Issue 2 — Rating column had '--' placeholders**
```sql
WHERE rating != '--' AND rating IS NOT NULL
```
Solution: Filtered out placeholder values and NULLs before any rating calculations.

**Issue 3 — Outlier in cost data**
One entry showed ₹18,962 average cost — clearly a data entry error.  
Solution: Added `WHERE cost < 2000` to filter unrealistic values.

---

## 📊 Queries Written

| Query | Business Question |
|---|---|
| Q1 | How many restaurants are listed on Swiggy? |
| Q2 | Which cities have the most restaurants? |
| Q3 | What are the most popular cuisines across India? |
| Q4 | Which cities have the highest average cost for two? |
| Q5 | Which restaurants have the highest ratings? |
| Q6 | Which cities have the best average restaurant ratings? |
| Q7 | Which restaurant chains are present in the most cities? |
| Q8 | Which budget restaurants (under ₹300) have great ratings? |
| Q9 | Which cities have the most diverse cuisine variety? |
| Q10 | Which restaurants are underperforming despite significant reviews? |

---

## 🧠 SQL Concepts Used

- `SELECT`, `WHERE`, `ORDER BY`, `LIMIT` — filtering and sorting
- `GROUP BY` + `COUNT`, `AVG`, `ROUND` — aggregations
- `CAST` — converting text to numbers for calculations
- `REPLACE` — cleaning currency symbols and commas from data
- `COUNT(DISTINCT ...)` — counting unique values per group
- `IS NOT NULL` + `!=` — handling missing and placeholder values
- Outlier detection and filtering

---

## 📁 Files in This Repo

| File | Description |
|---|---|
| `swiggy_analysis.sql` | All 10 SQL queries with comments |
| `top_cities_cost.png` | Bar chart — most expensive cities by avg cost |
| `top_cuisines.png` | Bar chart — most popular cuisines on Swiggy |

---

## 📸 Charts

### Most Expensive Cities
![Top Cities by Cost](top_cities_cost.png)

### Most Popular Cuisines
![Top Cuisines](top_cuisines.png)

---

## 🛠️ How to Run This Yourself

1. Download [DB Browser for SQLite](https://sqlitebrowser.org) — free
2. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/ashishjangra27/swiggy-restaurants-dataset)
3. Open DB Browser → New Database → File → Import → Table from CSV
4. Make sure **"Column names in first line"** is checked when importing
5. Copy any query from `swiggy_analysis.sql` → paste into Execute SQL tab → press Play

---

## 🗺️ My Data Analyst Roadmap

| Status | Project |
|---|---|
| ✅ Done | Project 1 — Excel/Sheets Sales Dashboard |
| ✅ Done | Project 2 — SQL E-Commerce Analysis (Northwind) |
| ✅ Done | Project 3 — Swiggy Restaurant Analysis ← this project |
| ⬜ Next | Project 4 — Netflix Data Analysis |

---

## 🤝 Connect

Learning data analytics in public — one project at a time.  
Connect with me on [LinkedIn](#) if you're on the same journey!

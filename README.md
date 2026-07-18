# superstore-powerbi-dashboard
Sales Analytics Dashboard built with Power BI and Kaggle Superstore data
# 📊 Superstore Sales Dashboard — Power BI

An interactive sales analytics dashboard built using **Microsoft Power BI Desktop** and the **Kaggle Superstore dataset**, featuring dynamic KPI cards, trend charts, and region/category slicers.

---

## 🖼️ Dashboard Preview

![Dashboard Overview 1](images/dashboard(1).png)
![Dashboard Overview 2](images/dashboard(2).png)

---

## 📁 Repository Structure

```
📁 superstore-powerbi-dashboard/
├── superstore-dataset.csv          ← Processed Kaggle Superstore dataset
├── superstore-sales-dashboard.pbix ← Power BI Desktop project file
├── dashboard(1).png                ← Dashboard screenshot (page 1)
├── dashboard(2).png                ← Dashboard screenshot (page 2)
└── README.md                       ← Project documentation
```

---

## 📌 Project Overview

This project demonstrates end-to-end Business Intelligence development — from raw data ingestion and transformation in Power Query, to DAX measure creation, to a fully formatted interactive dashboard.

| Property | Details |
|---|---|
| **Dataset** | Kaggle Superstore Sales |
| **Rows** | 9,994 orders |
| **Date Range** | 2019 – 2022 |
| **Tool** | Microsoft Power BI Desktop |
| **Techniques** | Power Query, DAX, Star Schema, Data Modelling |

---

## 📊 Visuals Included

| Visual | Fields Used | Insight |
|---|---|---|
| KPI Card — Total Revenue | `SUM(Orders[Sales])` | Overall revenue at a glance |
| KPI Card — Total Orders | `COUNTROWS(Orders)` | Volume of transactions |
| KPI Card — Avg Order Value | `Revenue / Orders` | Revenue per order |
| KPI Card — Total Profit | `SUM(Orders[Profit])` | Overall profitability |
| Line Chart | Month Name × Total Revenue | Monthly revenue trend |
| Donut Chart | Segment × Total Revenue | Consumer vs Corporate vs Home Office |
| Bar Chart | Sub-Category × Total Revenue | Top revenue-generating sub-categories |
| Column Chart | Region × Total Profit | Profit comparison across regions |
| Scatter Chart | Discount × Profit Margin % | Impact of discounts on profitability |
| Area Chart | Quarter × Revenue + Profit | Quarterly performance vs trend |
| Table | Product, Category, Revenue, Margin | Top products ranked by revenue |

---

## 🎛️ Slicers / Interactive Filters

- 📅 **Year** — Filter all visuals by order year
- 📦 **Category** — Furniture / Technology / Office Supplies
- 🌍 **Region** — West / East / Central / South

All slicers cross-filter every visual on the page simultaneously.

---

## 🧮 DAX Measures

```dax
Total Revenue    = SUM(Orders[Sales])
Total Profit     = SUM(Orders[Profit])
Total Orders     = COUNTROWS(Orders)
Avg Order Value  = DIVIDE([Total Revenue], [Total Orders])
Profit Margin %  = DIVIDE([Total Profit], [Total Revenue]) * 100
YoY Revenue %    = DIVIDE([Total Revenue] - [Prev Year Rev], [Prev Year Rev]) * 100
Prev Year Rev    = CALCULATE([Total Revenue], SAMEPERIODLASTYEAR(Calendar[Date]))
Discount Impact  = SUMX(Orders, Orders[Sales] * Orders[Discount])
Running Total    = CALCULATE([Total Revenue], DATESYTD(Calendar[Date]))
```

---

## 🗂️ Data Model

The project follows a **Star Schema** with two tables:

```
Calendar (Date Table)
    └── Date (1) ──────── (*) Order Date (Orders Table)
```

**Calendar Table columns:** Date, Year, Month Number, Month Name, Quarter, Week Number

**Orders Table key columns:** Order ID, Order Date, Ship Date, Customer Name, Segment, Region, Category, Sub-Category, Product Name, Sales, Quantity, Discount, Profit

---

## 🔧 How to Use

1. **Download** `superstore-sales-dashboard.pbix` from this repository
2. Open it in **Power BI Desktop** (free download at [powerbi.microsoft.com](https://powerbi.microsoft.com/desktop))
3. If prompted to refresh data, point it to the `superstore-dataset.csv` file in this repo:
   - Home → Transform Data → Data Source Settings → Change Source → browse to the CSV
4. Click **Close & Apply**
5. Explore the dashboard using the slicers at the top

---

## 📦 Dataset

| Property | Details |
|---|---|
| **Source** | [Kaggle — Superstore Dataset by vivek468](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final) |
| **File** | `superstore-dataset.csv` |
| **Records** | 9,994 rows · 21 columns |
| **License** | Public / Community dataset |

---

## 🛠️ Tools & Technologies

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Microsoft Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)


- **Power BI Desktop** — Dashboard development
- **Power Query (M)** — Data cleaning and transformation
- **DAX** — Calculated measures and KPIs
- **Git & GitHub** — Version control and project hosting

---

## 👤 Author

Feel free to fork this repository, open issues, or reach out if you have questions!

---
Name: Nancy     email: nancybhatia1397@gmail.com     LinkedIn: www.linkedin.com/in/nancy-bhatia-an1397
⭐ *If you found this project helpful, consider giving it a star!*

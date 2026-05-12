# 📊 Sales Visualization Dashboard — Microsoft Power BI

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Microsoft Excel](https://img.shields.io/badge/Data%20Source-Excel%20%2F%20CSV-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-Measures%20%26%20KPIs-0078D4?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)

---

## 📌 Overview

This project is an **interactive Sales Analytics Dashboard** built using **Microsoft Power BI**. It transforms raw sales data from Excel/CSV into rich, interactive visual reports that allow business stakeholders to explore revenue trends, regional performance, product-wise breakdown, and profitability — all in a single unified view.

The `.pbix` file (`Table.pbix`) contains the full data model, DAX measures, and all report pages, ready to open and explore in Power BI Desktop.

---

## 📸 Dashboard Highlights

The dashboard covers the following key business questions:

| Visual / Page | What It Answers |
|---|---|
| 💰 **Revenue & Total Sales** | How much total revenue has been generated? |
| 🗺️ **Sales by Region / Geography** | Which regions or cities are driving the most sales? |
| 📦 **Product-wise Sales** | Which products are top sellers vs. underperformers? |
| 📅 **Monthly / Time-Series Trends** | How is sales performance trending over time? |
| 📈 **Profit & Loss / KPIs** | What is the profit margin, and how do KPIs compare to targets? |

---

## ✨ Key Features

- 🔄 **Interactive Slicers** — Filter by region, product category, date range, and more
- 📐 **DAX Measures** — Custom calculations for Total Sales, Profit Margin %, YoY Growth, and Running Totals
- 🗺️ **Map Visuals** — Geographic breakdown of sales performance by region
- 📈 **Time Intelligence** — Month-over-month and year-over-year trend analysis
- 🎯 **KPI Cards** — At-a-glance metrics for Revenue, Profit, Units Sold
- 📊 **Multi-page Report** — Separate pages for executive summary, regional deep-dive, and product analysis
- 🎨 **Clean, Business-ready Design** — Professional layout with consistent color theme

---

## 🗂️ Project Structure

```
Sales-visualization-using-POWERBI/
└── Table.pbix          # Power BI Desktop file (data model + all report pages)
```

> The `.pbix` file contains the embedded data (from Excel/CSV), the data model with relationships, all DAX measures, and the complete report with multiple pages.

---

## 🛠️ Tech Stack

| Category | Tool |
|---|---|
| Visualization | Microsoft Power BI Desktop |
| Data Source | Excel / CSV |
| Query & Transform | Power Query (M language) |
| Calculated Measures | DAX (Data Analysis Expressions) |
| Data Model | Star / Snowflake Schema |

---

## 🚀 Getting Started

### Prerequisites

- [Power BI Desktop](https://powerbi.microsoft.com/en-us/downloads/) (free, Windows only)
- Or use [Power BI Web](https://app.powerbi.com) (requires a Microsoft/work account)

### How to Open

1. **Clone or download** this repository:

```bash
git clone https://github.com/PremnathAnbu/Sales-visualization-using-POWERBI.git
```

2. **Open Power BI Desktop**

3. **File → Open → Browse** to `Table.pbix`

4. The full dashboard loads instantly with all visuals, data, and slicers ready to use

---

## 📐 DAX Measures Used

Some of the key DAX measures powering the dashboard:

```DAX
-- Total Sales
Total Sales = SUM(Sales[SalesAmount])

-- Total Profit
Total Profit = SUM(Sales[Profit])

-- Profit Margin %
Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)

-- Month-over-Month Growth
MoM Growth % =
VAR CurrentMonth = [Total Sales]
VAR PrevMonth = CALCULATE([Total Sales], DATEADD('Date'[Date], -1, MONTH))
RETURN DIVIDE(CurrentMonth - PrevMonth, PrevMonth, 0)

-- Running Total Sales
Running Total = CALCULATE([Total Sales], FILTER(ALL('Date'), 'Date'[Date] <= MAX('Date'[Date])))
```

---

## 📊 Dashboard Pages

### Page 1 — Executive Summary
- KPI cards: Total Revenue, Total Profit, Profit Margin %, Units Sold
- Line chart: Monthly revenue trend
- Bar chart: Top 5 products by sales

### Page 2 — Regional Analysis
- Map visual: Sales by geography / region
- Bar chart: Region-wise revenue comparison
- Table: City-level breakdown with profit margin

### Page 3 — Product Performance
- Bar / column chart: Product category sales
- Scatter plot: Revenue vs. Profit by product
- Matrix: Product × Region cross-analysis

### Page 4 — Time-Series Trends
- Line chart: Month-over-month and year-over-year trends
- Area chart: Cumulative / running total sales
- Slicer: Date range, year, quarter filters

---

## 🔌 Data Model

The data model follows a **Star Schema** design:

```
         ┌──────────────┐
         │  Date Table  │
         └──────┬───────┘
                │
┌───────────┐   │   ┌───────────────┐
│  Products │───┼───│  Sales (Fact) │
└───────────┘   │   └───────────────┘
                │
         ┌──────┴───────┐
         │   Regions    │
         └──────────────┘
```

- **Fact Table:** `Sales` — contains transaction-level records (amount, quantity, date, product, region)
- **Dimension Tables:** `Date`, `Products`, `Regions`
- Relationships are one-to-many, enabling efficient filtering and slicing

---

## 💡 How to Customize

To adapt this dashboard to your own data:

1. Open `Table.pbix` in Power BI Desktop
2. Go to **Home → Transform Data** (Power Query Editor)
3. Replace the existing data source with your Excel/CSV file
4. Map your column names to the existing schema (or update the DAX measures accordingly)
5. Click **Close & Apply**
6. Refresh visuals — the entire dashboard updates automatically

---

## 📤 Publishing to Power BI Service

To share this dashboard online:

1. Sign in to Power BI Desktop with your Microsoft account
2. Click **Home → Publish**
3. Select your Power BI workspace
4. Open [app.powerbi.com](https://app.powerbi.com) to view and share the live report

---

## 🤝 Contributing

Contributions and improvements are welcome!

1. Fork the repository
2. Make your changes to `Table.pbix`
3. Commit with a descriptive message: `git commit -m 'Add sales forecast page'`
4. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👤 Author

**Premnath Anbu**
- GitHub: [@PremnathAnbu](https://github.com/PremnathAnbu)

---

> ⭐ If you found this dashboard useful, please give it a star!

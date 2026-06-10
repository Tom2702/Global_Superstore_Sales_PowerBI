# Global Superstore Sales Analytics | PowerBI

> A Power BI analytics project that evaluates global retail sales performance, market growth, product profitability, order trends, and return behavior through an interactive dashboard built with a Design Thinking approach.

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-0F6B78?style=for-the-badge)
![Data Modeling](https://img.shields.io/badge/Data%20Modeling-Star%20Schema-2E7D32?style=for-the-badge)

## Project Overview

This project analyzes Global Superstore sales performance using Power BI. The dashboard is designed to help business stakeholders monitor revenue, profit, profit margin, order volume, product performance, market performance, and return rate in one centralized analytical report.

The dashboard flow is designed to move from a high-level business summary to deeper market and product analysis:

1. **Executive Summary**: Understand overall sales performance, profitability, order trends, and return rate.
2. **Market Analysis**: Compare markets by revenue, profit, margin, growth, average order value, and return behavior.
3. **Product Analysis**: Evaluate category and sub-category performance, best-selling products, profit contribution, and return rate.

## Business Objectives

The main objective is to transform Global Superstore sales data into actionable insights for revenue growth, profitability improvement, market prioritization, product optimization, and return-rate monitoring.

This project focuses on answering the following business questions:

- How much revenue and profit does the business generate?
- How have revenue, profit, orders, and return rate changed over time?
- Which markets contribute the most to revenue and profit?
- Which markets show strong growth but weak profitability?
- Which product categories and sub-categories drive the largest revenue?
- Which sub-categories create profit risk or negative margin?
- Which categories have high order volume and high return rate?
- What business actions can improve profitability and reduce return risk?

## Data Model

The Power BI report uses a star-schema-style model with a central order fact table connected to supporting dimension tables.

<!-- Insert or replace the Power BI data model screenshot below. -->

<img width="1266" alt="Global Superstore Power BI data model" src="assets/data-model.png" />

| Table | Description |
|---|---|
| `fact_orders` | Order-line fact table containing sales amount, profit, quantity, order date, order ID, customer, market, region, category, and sub-category fields |
| `dim_date` | Calendar dimension used for day, month, year, and time-based analysis |
| `dim_people` | Regional manager lookup table mapped to regions |
| `dim_returns` | Returned order lookup table used to identify returned orders and calculate return rate |

Model highlights:

- Centralized order fact table for sales, profit, quantity, and order analysis
- One-to-many relationships from dimensions to order transaction data
- Dedicated date table for year-based and time-based reporting
- Return lookup table for return-rate analysis at order, category, and market level
- Region manager mapping to support regional accountability
- DAX measures used for KPI cards, growth indicators, margins, orders, average order value, and return metrics

## Dataset

| File | Role | Description |
|---|---|---|
| `Orders.csv` | Fact source | 51,290 order-line records containing order, customer, market, product, sales, quantity, and profit information |
| `Returns.csv` | Return lookup | 1,172 returned order records |
| `People.csv` | People lookup | 13 regional managers mapped to regions |

Dataset coverage:

- Date range: **2011-01-01 to 2014-12-31**
- Total orders: **25,035**
- Customers: **1,590**
- Countries: **147**
- Markets: **Africa, APAC, Canada, EMEA, EU, LATAM, US**
- Categories: **Furniture, Office Supplies, Technology**
- Sub-categories: **17**

## Design Thinking Approach

The dashboard was developed using a Design Thinking framework to ensure the final report is not only visually clear, but also aligned with business users' real decision-making needs.

### 1. Empathize

The first step focused on understanding the target users and the decisions they need to make from the dashboard.

Target users:

- Executive stakeholders who need a fast business overview
- Sales and regional managers who monitor market performance
- Product/category managers who evaluate product profitability
- Operations teams who track order volume and return behavior
- Business analysts who need interactive exploration across time, market, and product dimensions

Key user pain points:

- Revenue, profit, margin, order volume, and return metrics are difficult to compare across markets and categories without a unified dashboard.
- Business users need to identify both high-growth markets and low-margin risk areas quickly.
- Product performance requires both sales contribution and profitability context.
- Return behavior needs to be monitored across time, markets, and product categories.
- Stakeholders need a simple flow from executive KPIs to deeper market and product-level analysis.

<!-- Optional: insert Design Thinking Empathize slide screenshot here. -->

### 2. Define

The core problem was defined as:

> Global Superstore stakeholders need an interactive dashboard that connects sales performance, profitability, market growth, product contribution, and return behavior so they can identify growth opportunities, margin risks, and operational issues faster.

<!-- Optional: insert Design Thinking Define slide screenshot here. -->

### 3. Ideate

The dashboard pages were organized into a business analysis flow:

1. **Executive Summary**: Start with global KPIs, yearly trends, market/category comparison, order trends, and return rate.
2. **Market Analysis**: Move into market-level revenue, profit, margin, growth, average order value, order volume, and return-rate analysis.
3. **Product Analysis**: End with category and sub-category performance, Pareto revenue, best-selling products, margin analysis, and return-rate comparison.

<!-- Optional: insert Design Thinking Ideate slide screenshot here. -->

## Detailed Dashboard

### 1. Executive Summary

The Global Superstore business generated approximately **$12.64M** in total revenue, **$1.47M** in total profit, **25K orders**, and an overall **11.6% profit margin**.

<!-- Insert or replace the Executive Summary page screenshot below. -->

<img width="2890" alt="Executive Summary dashboard page" src="assets/executive-summary.png" />

**Key observations:**

- Total revenue reached approximately **$12.64M**, while total profit reached approximately **$1.47M**.
- Revenue increased from about **$2.3M in 2011** to about **$4.3M in 2014**, showing strong growth over the analysis period.
- Profit increased from about **$0.2M in 2011** to about **$0.5M in 2014**.
- Profit margin stayed around **11.6%**, with the highest yearly margin appearing around **2013**.
- Total orders increased from about **9.0K in 2011** to about **17.5K in 2014**.
- Return rate was approximately **4.7%**, with category-level differences visible across the dashboard.

**Business interpretation:**

- The business shows strong revenue and order growth, but margin improvement should remain a priority.
- Growth should be evaluated together with return rate and profit margin to avoid scaling low-quality revenue.

### 2. Market Analysis

The Market Analysis page shows that **APAC** is the largest revenue market with approximately **$3.59M**, followed by **EU** at approximately **$2.94M** and **US** at approximately **$2.30M**.

<!-- Insert or replace the Market Analysis page screenshot below. -->

<img width="2890" alt="Market Analysis dashboard page" src="assets/market-analysis.png" />

Market performance:

| Market | Revenue | Profit | Profit Margin |
|---|---:|---:|---:|
| APAC | `$3.59M` | `$436K` | `12.2%` |
| EU | `$2.94M` | `$373K` | `12.7%` |
| US | `$2.30M` | `$286K` | `12.5%` |
| LATAM | `$2.16M` | `$222K` | `10.2%` |
| EMEA | `$0.81M` | `$44K` | `5.4%` |
| Africa | `$0.78M` | `$89K` | `11.3%` |
| Canada | `$0.07M` | `$18K` | `26.6%` |

**Key observations:**

- **APAC** is the top revenue market, contributing the largest share of total sales.
- **EU** and **US** show strong revenue scale and relatively healthy margins above **12%**.
- **Canada** has the highest profit margin at about **26.6%**, but its revenue base is much smaller than other markets.
- **EMEA** shows strong revenue growth but weak profitability, with a margin of about **5.4%**.
- LATAM has high order volume but a lower margin than APAC, EU, and US.
- Return rates are higher in several large markets, which may reduce the quality of growth.

**Business interpretation:**

- APAC, EU, and US should remain core revenue markets because they combine scale with stable profitability.
- Canada may provide a useful profitability benchmark, but it needs scale validation before expansion.
- EMEA requires margin review because growth without profitability can reduce overall business quality.

### 3. Product Analysis

The Product Analysis page shows that **Technology** is the strongest category by revenue and profit, while **Furniture** has the weakest profit margin among the three categories.

<!-- Insert or replace the Product Analysis page screenshot below. -->

<img width="2890" alt="Product Analysis dashboard page" src="assets/product-analysis.png" />

Category performance:

| Category | Revenue | Profit | Profit Margin |
|---|---:|---:|---:|
| Technology | `$4.74M` | `$664K` | `14.0%` |
| Office Supplies | `$3.79M` | `$518K` | `13.7%` |
| Furniture | `$4.11M` | `$285K` | `6.9%` |

Top sub-categories by revenue:

| Rank | Sub-Category | Revenue | Profit | Quantity |
|---:|---|---:|---:|---:|
| 1 | Phones | `$1.71M` | `$217K` | `11.9K` |
| 2 | Copiers | `$1.51M` | `$259K` | `7.5K` |
| 3 | Chairs | `$1.50M` | `$140K` | `12.3K` |
| 4 | Bookcases | `$1.47M` | `$162K` | `8.3K` |
| 5 | Storage | `$1.13M` | `$108K` | `16.9K` |

**Key observations:**

- **Technology** generated the highest revenue and profit, with a margin of about **14.0%**.
- **Office Supplies** generated slightly lower revenue than Furniture but delivered much stronger profit.
- **Furniture** generated about **$4.11M** in revenue but only about **$285K** in profit, resulting in the lowest category margin.
- **Tables** is the weakest sub-category by profit, with approximately **-$64K** in profit.
- **Phones, Copiers, Chairs, Bookcases, and Storage** are the top revenue-generating sub-categories.
- **Binders** is the best-selling sub-category by quantity, with approximately **21K units sold**.

**Business interpretation:**

- Technology and Office Supplies should be prioritized for profitable growth because they combine strong revenue with healthier margins.
- Furniture requires pricing, discount, cost, or product-mix review because revenue scale is not converting efficiently into profit.
- Tables should be investigated as a profit-risk area before further promotion or expansion.

## Key Metrics

| Metric | Value |
|---|---:|
| Total Revenue | `$12.64M` |
| Total Profit | `$1.47M` |
| Profit Margin | `11.6%` |
| Total Orders | `25K` |
| Total Quantity | `178K` |
| Return Rate | `4.7%` |

Core DAX measures:

```DAX
Total Revenue = SUM(fact_orders[Sales])

Total Profit = SUM(fact_orders[Profit])

Profit Margin = DIVIDE([Total Profit], [Total Revenue])

Total Orders = DISTINCTCOUNT(fact_orders[Order ID])

Total Quantity = SUM(fact_orders[Quantity])

AVG Order Value = DIVIDE([Total Revenue], [Total Orders])
```

## Business Recommendations

- **Prioritize profitable growth markets**: Focus on APAC, EU, and US because they combine strong revenue scale with stable profit margins.
- **Investigate low-margin markets**: Review EMEA and LATAM pricing, discounting, shipping cost, or product mix to improve profitability.
- **Scale high-margin opportunities carefully**: Canada shows the highest margin, but its small revenue base should be validated before major investment.
- **Improve Furniture profitability**: Analyze discounts, shipping costs, supplier costs, and product mix because Furniture has the lowest category margin.
- **Review loss-making sub-categories**: Tables should be investigated as a priority because it generates negative profit.
- **Protect high-performing sub-categories**: Phones, Copiers, Chairs, Bookcases, and Storage drive major revenue and should remain key commercial focus areas.
- **Monitor return behavior**: Track return rate by market, category, and sub-category to reduce revenue leakage and improve customer experience.

## How to Use

1. Open `Superstore Sales.pbix` in Power BI Desktop.
2. Check the data source paths in Power Query if the CSV files are stored in a different location.
3. Refresh the dataset.
4. Use the `Year`, `Market`, `Category`, and `Sub-Category` slicers to explore the report.
5. Export the report to PDF if needed. The exported version is available as `Superstore Sales.pdf`.

## Project Structure

```text
.
├── Dataset/
│   ├── Orders.csv
│   ├── People.csv
│   └── Returns.csv
├── assets/
│   ├── executive-summary.png
│   ├── market-analysis.png
│   ├── product-analysis.png
│   └── data-model.png
├── Design Thinking.xlsx
├── Global_Superstore_Design_Thinking_3_Slides_EN.pptx
├── Superstore Sales.pbix
├── Superstore Sales.pdf
└── README.md
```

## Tools Used

- Power BI Desktop: data modeling, DAX measures, and report design
- Power Query: data cleaning and transformation
- DAX: KPI calculations, margins, rates, and business measures
- CSV dataset: Orders, Returns, and People
- Design Thinking: problem framing, stakeholder analysis, insight development, and dashboard flow

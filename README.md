[Insights_summary.md](https://github.com/user-attachments/files/20961221/Insights_summary.md)[DAX_measures.md](https://github.com/user-attachments/files/20961218/DAX_measures.md)
# 🚀 Supersales Dashboard (Power BI)

An end-to-end data analysis and visualization project built in **Power BI**, focused on eCommerce sales performance using Superstore-style data.

---

## 📦 Dataset Overview

This dashboard analyzes sales records, shipping performance, profit margins, and customer behavior based on:

- Order & delivery dates
- Customer and product segmentation
- Sales, profit, and shipping cost metrics
- Regions, categories, and sub-categories

---

## 📊 Key KPIs Tracked

| KPI                          | Description |
|-----------------------------|-------------|
| **Total Sales**             | Total revenue from orders |
| **Profit Margin (%)**       | (Profit ÷ Sales) × 100 |
| **Average Order Value (AOV)** | Sales ÷ No. of Orders |
| **Running Total Sales**     | Cumulative sales over time |
| **Average Delivery Time**   | Avg. days from order to delivery |
| **Late Delivery %**         | % of orders shipped after expected date |
| **Top N Products by Sales** | Dynamically filtered top products |
| **ASPC**                    | Average Selling Price per Customer |
| **Orders per Customer**     | Order frequency |

---

## 🛠 Tools Used
- **MYSQL**
- **Power BI**
- **DAX**



[Upload
# 📊 DAX Measures for Supersales / Novamart Power BI Dashboard

This file documents the core DAX measures used in the Power BI project.

## 🔹 1. Total Sales
```dax
Total_Sales = SUM(fact_sales[SalesAmount])
```

## 🔹 2. Total Orders
```dax
Total_Orders = DISTINCTCOUNT(fact_sales[OrderID])
```

## 🔹 3. Total Profit
```dax
Total_Profit = SUM(fact_sales[SalesAmount]) - SUM(fact_sales[CostAmount])
```

## 🔹 4. Profit Margin (%)
```dax
Profit_Margin_% = DIVIDE([Total_Profit], [Total_Sales], 0) * 100
```

## 🔹 5. Average Order Value (AOV)
```dax
AOV = DIVIDE([Total_Sales], [Total_Orders], 0)
```

## 🔹 6. Average Profit per Order
```dax
Avg_Profit_per_Order = DIVIDE([Total_Profit], [Total_Orders], 0)
```

## 🔹 7. Average Delivery Time (Days)
```dax
Avg_Delivery_Time = 
DIVIDE(
    SUMX(fact_orders, DATEDIFF(fact_orders[OrderDate], fact_orders[DeliveryDate], DAY)),
    COUNTROWS(fact_orders),
    0
)
```

## 🔹 8. ASPC (Avg Selling Price per Customer)
```dax
ASPC = DIVIDE([Total_Sales], DISTINCTCOUNT(fact_sales[CustomerID]), 0)
```

## 🔹 9. Orders per Customer
```dax
Orders_per_Customer = DIVIDE([Total_Orders], DISTINCTCOUNT(fact_sales[CustomerID]), 0)
```

[Uploading
# 🔍 Business Insights from Supersales / Novamart Dashboard

This section summarizes key insights uncovered using the Power BI visualizations.

## 🛍️ Sales Insights
- 📈 **Total Sales** are highest in the **West** and **Central** regions.
- 🔝 **Top-selling products** are from the **Electronics** and **Office Supplies** categories.
- 🕐 **Sales spike in Q4** indicating seasonal demand or holiday campaigns.

## 📦 Fulfillment & Delivery
- 🚚 **Average Delivery Time** is 2.5 days, but some regions face delays > 5 days.
- ❗ **Late Deliveries** account for ~18% — especially high in the South region.
- 📦 **Standard Class shipping** has the most delays, suggesting logistic issues.

## 💰 Profitability Metrics
- 💹 **Profit Margin** is strong (~29%) but varies across categories — Furniture underperforms.
- 💸 **Average Profit per Order** is ₹266 — could be improved by bundling offers or upselling.
- 📊 **High returns/discounts** in some categories are pulling margins down.

## 🧍 Customer Behavior
- 💳 **ASPC (Average Selling Price per Customer)** is ₹1,100 — varies significantly by segment.
- 📦 Customers in urban regions tend to place higher-value, more frequent orders.

## 📊 Summary Recommendations
- Improve delivery logistics in southern region to reduce late orders.
- Promote high-margin categories (like tech accessories).
- Run targeted campaigns for repeat buyers and high ASPC segments.
 Insights_summary.md…]()


## 🧠 Insights Enabled

- 🔍 Identify best-selling products and underperformers
- 📦 Analyze shipping performance and delays
- 🧍 Understand customer buying behavior
- 🌍 Evaluate regional sales trends

![Screenshot 2025-06-28 192202](https://github.com/user-attachments/assets/7f9311c9-6ee3-42c1-a6bc-e532dc6fc8e6)

![Screenshot 2025-06-28 192230](https://github.com/user-attachments/assets/0e328b44-4043-455f-a0da-7df6c9db822d)

![Screenshot 2025-06-28 192243](https://github.com/user-attachments/assets/b028c865-19f9-4b7e-a2b2-689c41ccc603)

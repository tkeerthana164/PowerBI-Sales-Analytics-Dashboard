📊 Power BI Sales Analytics Dashboard

An interactive Power BI Sales Analytics Dashboard developed as part of a Power BI Module End Evaluation.

The project focuses on data cleaning, transformation, DAX calculations, interactive visualizations, and business analysis using sales data.

🎯 Project Overview

The report provides a multi-page analysis of:

Sales performance

Profitability

Order trends

Product and category performance

Regional performance

Sales and cost trends

Profit margin

🗂️ Dataset

Dataset: SalesData_1000Rows_WithIssues.csv

Details

Value

Original Records

1,020

Records After Duplicate Removal

1,002

Number of Columns

11

Data Source

CSV

Main Tool

Power BI

🧹 Data Cleaning & Preparation

The following steps were performed using Power Query:

Missing values were identified using Column Quality and Column Statistics.

Missing CustomerName, Region, and Product values were replaced with "Unknown".

Missing UnitPrice was calculated using Sales ÷ Quantity.

Missing Sales was calculated using Quantity × UnitPrice.

Missing Cost was calculated using Sales − Profit.

Missing Profit was calculated using Sales − Cost.

The two missing OrderDate values were filled using the previous available date.

Duplicate records were removed across all columns.

The dataset was reduced from 1,020 rows to 1,002 unique rows.

OrderDate was converted to the Date data type.

📈 Dashboard Pages

1. Executive Sales Overview

Provides a high-level summary of overall business performance.

Includes:

Total Sales

Total Profit

Total Orders

Total Quantity

Profit Margin %

Sales vs Profit by Region

Profit Trend Over Time

Order Distribution by Region

Region and Product slicers

Key business insights

2. Product & Category Analysis

Analyzes product and category-level performance.

Includes:

Sales by Category and Product

Category → Product hierarchy

Treemap

Trending products by orders

Top products by profit

Total quantity by product

Category slicer

Product slicer

3. Regional Performance Analysis

Compares sales, profit, and order performance across regions.

Includes:

Sales by Region

Profit by Region

Order Distribution by Region

Monthly Sales Trend by Region

Region slicer

4. Profitability & Trend Analysis

Analyzes how sales, cost, and profit change over time.

Includes:

Profit Trend Over Time

Sales Trend Over Time

Sales vs Cost

Profit Margin %

Date slicer

Date hierarchy drill-down

Time hierarchy:

Year → Quarter → Month

🧮 DAX Calculations

East Region Orders

EastRegionOrders =
FILTER(
    SalesData_1000Rows_WithIssues_copy,
    SalesData_1000Rows_WithIssues_copy[Region] = "East"
)

Profit Cost Difference

ProfitCostDifference =
SalesData_1000Rows_WithIssues_copy[Profit]
-
SalesData_1000Rows_WithIssues_copy[Cost]

Total Profit

TotalProfit =
SUM(SalesData_1000Rows_WithIssues_copy[Profit])

Profit Margin

Profit Margin % =
DIVIDE([TotalProfit], [Total Sales], 0)

📊 Power BI Features Used

Power Query Editor

Data Cleaning

Missing Value Handling

Duplicate Removal

Data Type Transformation

KPI Cards

Slicers

Treemap

Pie/Donut Charts

Clustered Column Charts

Bar Charts

Line Charts

Area Charts

Gauge

DAX Calculated Table

DAX Calculated Column

DAX Measures

Drill-down

Date Hierarchy

Multi-page Dashboard Navigation

🎨 Dashboard Design

A consistent dark green, teal, and light green theme is used across the report.

The design uses:

Dark green for navigation and major headings

Deep teal for primary chart elements

Light green for secondary metrics

White/light backgrounds for readability

Consistent typography and spacing

💡 Key Insights

The dashboards provide insights into:

Regional differences in sales and order contribution.

Product-level differences in sales, profit, and quantity.

Sales and profit changes over time.

Comparison between sales and cost.

Overall profitability and profit margin.

Interactive slicers allow users to explore the data by region, product, category, and date.

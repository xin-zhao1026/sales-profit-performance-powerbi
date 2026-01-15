# End-to-End Sales Performance Analysis Dashborad

## Dashboard Link:

[End-to-End Sales Performance Analysis Dashboard](https://app.powerbi.com/view?r=eyJrIjoiMDA0YWE3MzEtODZmNi00YmJhLTk0YTEtYzY1NTg1OTJhMDkxIiwidCI6IjgyMzQxNTljLTBjYjctNDI4NC1hMDI3LTA0MWFjZjllNmQwNiIsImMiOjZ9)

## Purpose & Description

#### Purpose:

This dashboard is designed to provide a comprehensive view of a Plant's sales and quantity performance across time, geography, and customer accounts.
It enables business users to monitor **Year-to-Date(YTD) performance**, compare it with **Prior Year-to-Date(PYTD)**, and analyze profitability trends by product, country, and account.

#### Description:

The dashboard integrates transactional sales date, customer account information, and product hierarchy data to support both **operational monitoring** and **strategic performance analysis**.

Key business questions addressed include：
+ How is current YTD performance trending compared to last year?
+ Which countries and accounts are underperforming or overperforming?
+ How does gross profit evolve month over month?
+ Which custmers fall into high/low profitability segments?

Interactive slicers allow users to dynamically switch between **Sales, Quantity**, and **Gross Profit**, making the dashboard adaptable for differernt analytical perspectives.


## Key Metrics Definition:

- [x] Sales ： Total revenue generated from product sales.
- [x] Quantity : Total units sold.
- [x] COGS (Cost of Goods Sold) : Direct costs associated with producing the sold products.
- [x] Gross Profit : Used to evaluate profitability performance across time, geography, and accounts.

    ``` Gross Profit = Sales - COGS```
- [x] YTD (Year-to-Date) : Cumulative performance from the start of the selected year up to the lasted date.
- [x] PYTD (Prior Year-to-Date) : Cumulative performance for the same period in the previous year, aligned by date.
- [x] YTD vs. PYTD : Absolute difference between current YTD and prior year YTD.
- [x] GP% (Growth Percentage) : Used to measure year-over-year growth or decline.
      
    ``` GP% = Gross Profit / Sales ```


## Visuals Explanation
#### 1. Slicer - Year & Business Metric
   + **Year Slicer** allows selection between 2023 and 2024.
   + **Business metric slicer** enables dynamic switching between:
     + Sales
     + Quantity
     + Gross Profit

All visuals and KPIs respond consistentlly to slicer selections.

#### 2. KPI Cards
Cards display:
+ YTD
+ PYTD
+ YTD vs. PYTD
+ GP%

These provide an at-a-glance summary of overall business performance.

#### 3. Filled Map - Bottom 10 Countries
##### **Bottom 10 YTD vs. PYTD by Country**

This visualization highlights underperforming countries based on YTD vs. PYTD comparison, helping identify geographic areas requiring attention.

#### 4. Waterfall Chart - Monthly Gross Profit Change
##### **Gross Profit YTD vs. PYTD | Month - Country**

The waterfall chart explains how monthly changes contribute to the overall difference between YTD and PYTD, making performace drivers transparent.

#### 5. Line & Stacked Column Chart
##### **Gross Profit YTD & PYTD | Month**

This chart clearly shows trend differences and seasonality effects between current and prior years.

#### 6. Scatter Chart - Account Profitability Segmentation
##### **GP% vs. Gross Profit by Account**

This chart segments customer accounts into:
+ High profit / High growth
+ High profit / Low growth
+ Low profit / High growth
+ Low profit / Low growth

It supports strategic decisions such as account priotitization and targeted sales actions.


## PowerBI Dashboard Creation：

The dashboard is created using PowerBI. It leverages various data sources to provide real-time insights into your business's sales performance.


## How to Use:

1. **Accessing the Dashboard**: Click on the provded dashboard link to access the End-to-End Sales Performance Analytic Dashboard, or clone the repo.
2. **Navigation**: Navigate through different sections using the interactive features such as filters, slicers, and drill-down options.
3. **Interacting with Data**: Hover over data points to view detailed information. Use filters to customize the view based on specific metrics, time periods, or countries/accounts.
4. **Analyzing Trends**: Identify trends, patterns, and outliers to make informed decisions. Compare KPIs across different segments and time frames.
5. **Actionable Insights**: Use the insights gained from the dashboard to find out growth enabler, optimize strategies, allocate resources effectively, and drive profitability.

# End-to-End Sales Performance Analysis Dashborad

### Dashboard Link:

XXX
## Purpose & Description

### Purpose:

This dashboard is designed to provide a comprehensive view of a Plant's sales and quantity performance across time, geography, and customer accounts.
It enables business users to monitor **Year-to-Date(YTD) performance**, compare it with **Prior Year-to-Date(PYTD)**, and analyze profitability trends by product, country, and account.

### Description:

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
### 1. Slicer - Year & Business Metric
   + **Year Slicer** allows selection between 2023 and 2024.

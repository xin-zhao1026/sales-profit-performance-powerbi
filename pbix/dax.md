## DAX Design Overview

This document describes the DAX design principles and calculation logic used in the **Sales & Profit Performance Analytics** Power BI project.

Rather than listing every individual formula, the focus is on explaining how measures are structured, why specific time intelligence patterns were chosen, and how the model supports scalable analytics.

---

### 📁 Measure Organization Strategy

All measures are organized under a logical `_Measures` structure with clear functional separation:

- **Base Measures** – core aggregations from the fact table  
- **YTD Measures** – current year cumulative performance  
- **PYTD Measures** – prior-year comparable period calculations  
- **Profitability Metrics** – margin and ratio-based measures  
- **Dynamic SWITCH Measures** – metric selection logic for report interactivity  

This layered approach ensures:
- High reusability
- Consistent calculations across visuals
- Easier debugging and future extension

---

### 1️⃣ Base Measures

Base measures represent the most granular business metrics, such as Sales, Quantity, COGS, and Gross Profit.

Design principles:
- Calculated directly from `Fact_Sales`
- No time intelligence logic
- Serve as building blocks for all derived measures

This separation avoids duplicated logic and keeps higher-level measures clean and readable.

---

### 2️⃣ Year-to-Date (YTD) Logic

YTD measures calculate cumulative performance from the beginning of the selected year up to the current reporting date.

Key characteristics:
- Implemented using built-in DAX time intelligence functions
- Fully driven by the date context provided by `Dim_Date`
- Automatically responds to year and month slicers

This approach ensures consistency across all YTD-based visuals and KPIs.

---

### 3️⃣ Prior Year-to-Date (PYTD) Logic

PYTD measures calculate performance for the same year-to-date period in the prior year.

The logic combines:
- Date context shifting to the previous year
- A custom date flag (`Dim_Date[Inpast]`) to restrict calculations to valid historical periods

#### Why use an `Inpast` flag?

The dataset’s latest transaction date does not align with the calendar year-end.  
Using the `Inpast` flag ensures that PYTD calculations:
- Exclude incomplete or future dates
- Compare equivalent periods (e.g., Jan–Apr current year vs. Jan–Apr prior year)
- Avoid overstating prior-year performance

This design improves the accuracy and credibility of YoY comparisons.

---

### 4️⃣ Profitability Metrics

Profitability measures (e.g., Gross Profit %) are calculated using reusable base measures.

Best practices applied:
- Ratio calculations built on top of absolute metrics
- Safe division logic to prevent errors or misleading results
- Fully compatible with dynamic metric selection

---

### 5️⃣ Dynamic Metric Switching (SWITCH Logic)

To enhance report usability, the dashboard allows users to switch between Sales, Quantity, and Gross Profit using a slicer.

Implementation highlights:
- Uses a disconnected slicer table
- Centralized SWITCH logic determines the active metric
- Eliminates the need for duplicated visuals

This design provides a cleaner user experience while keeping the model maintainable.

---

### 🧠 Key Design Decisions

- Centralized business logic using base measures
- Consistent time intelligence across all KPIs
- Explicit handling of partial-year data using custom date flags
- Clear separation between calculation layers and presentation logic

---

### 🔄 Extensibility

The current DAX structure is designed for easy extension, including:
- Budget vs. Actual comparisons
- Rolling 12-month metrics
- Forecast or target-based KPIs

Minimal refactoring would be required to support these enhancements.

---


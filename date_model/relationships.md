## Data Model Relationships

This project follows a **star schema** data modeling approach, with a central fact table (`Fact_Sales`) connected to multiple dimension tables.  
The model is designed to support efficient filtering, accurate time intelligence (YTD / PYTD), and scalable analytics.

---

### ⭐ Model Overview

- **Fact Table**
  - `Fact_Sales`: Contains transactional sales data including sales amount, quantity, COGS, and transaction date.

- **Dimension Tables**
  - `Dim_Product`: Product hierarchy and attributes
  - `Dim_Account`: Customer and geographic information
  - `Dim_Date`: Calendar table used for time intelligence calculations

All relationships are **many-to-one (M:1)** with single-direction filtering from dimensions to the fact table.

---

### 🔗 Relationship Details

#### 1️⃣ Product Relationship


- **Cardinality:** Many-to-One (M:1)
- **Cross Filter Direction:** Single
- **Purpose:**
  - Enables analysis by product family, group, name, size, and type
  - Supports drill-down across product hierarchy levels
- **Design Rationale:**
  - `Fact_Sales` contains transactional-level product references
  - `Dim_Product` acts as a lookup table with descriptive attributes

---

#### 2️⃣ Date Relationship


- **Cardinality:** Many-to-One (M:1)
- **Cross Filter Direction:** Single
- **Purpose:**
  - Enables robust time intelligence calculations
  - Supports YTD, PYTD, and year-based slicing
- **Design Rationale:**
  - A dedicated `Dim_Date` table is required for DAX time intelligence functions
  - Centralizes calendar logic such as year filtering and historical period control

---

#### 3️⃣ Account Relationship


- **Cardinality:** Many-to-One (M:1)
- **Cross Filter Direction:** Single
- **Purpose:**
  - Enables customer-level and geographic analysis
  - Supports profitability segmentation and regional insights
- **Design Rationale:**
  - Keeps customer attributes separated from transactional data
  - Improves model clarity and performance

---

### 🧠 Modeling Best Practices Applied

- ✅ Star schema design for simplicity and performance
- ✅ Dimension-to-fact single-direction filtering
- ✅ No many-to-many relationships
- ✅ Time intelligence enabled via a dedicated date table
- ✅ Optimized for YTD / PYTD and profitability analysis

---

### 📌 Notes

- All measures are created using DAX and stored separately under the `_Measures` structure.
- The data model is optimized for analytical queries rather than transactional updates.
- This structure allows easy extension (e.g., adding Budget or Forecast fact tables).


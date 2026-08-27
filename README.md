# Power BI Assignment 1 – Data Transformation & Data Modeling
## E-Commerce Sales Analysis

This project uses Power BI to import, clean, transform, and model e-commerce sales data, and to build relationships across multiple data sources for analysis.

---

## 📁 Data Files

| File | Description |
|---|---|
| `List of Orders.csv` | Order-level details including customer, location, and order date |
| `Order Details.csv` | Line-item details for each order (Amount, Profit, Category, Sub-Category, etc.) |
| `Sales target.csv` | Monthly sales targets by category |

---

## 🔧 Project Steps

### 1. Import Data
- Import `List of Orders.csv` into Power BI.
- Open it in **Power Query Editor** via `Transform Data`.
- Import `Order Details.csv` and `Sales target.csv` into Power Query Editor.

### 2. Data Transformation
- Restrict **List of Orders** to the first **500 rows**.
- Set **Order Date** column data type to `Date`.
- Set **Amount** and **Target** columns to `Fixed Decimal Number`.
- Convert **CustomerName** to **Proper Case** (consistent word capitalization).
- Merge **State** and **City** into a new column **Location**, formatted as `City, State`.
- Add a custom column **Profit Margin** = `Profit / Amount` (as a percentage).
- Add a conditional column **Profit Status**:
  | Condition | Label |
  |---|---|
  | Profit < 0 | Loss |
  | Profit = 0 | Break-Even |
  | Profit > 0 | Profit |

### 3. Merging Data (Joins)
- Merge **List of Orders** and **Order Details** into a new table named **Orders Data**, joined on **Order ID**.

### 4. Handling Missing & Duplicate Data
- Identify missing values across tables and define a handling strategy (e.g., remove, replace with default/average, or flag for review).
- Identify duplicate rows and define a strategy (e.g., remove exact duplicates, or investigate/keep based on business rules).

### 5. Sorting & Filtering (on "Orders Data")
- Sort orders by **Order Date** in **descending order** to surface recent trends.
- Filter orders to a specific **State** (e.g., *Tamil Nadu*) for regional analysis.

### 6. Grouping & Aggregating Data
- Duplicate **Order Details** table:
  - Count of Orders per **Order ID**
  - Average **Profit** by **Category**
  - Total **Amount** by **Sub-Category**
- Duplicate **Sales Target** table:
  - Aggregate total **Target Amount** by **Month** of Order Date.

### 7. Data Modeling
- Relationship: **List of Orders** ↔ **Order Details** on `Order ID`.
- Relationship: **Order Details** ↔ **Sales Target** on `Category`.
- Confirm relationships in **Manage Relationships** and ensure the Category relationship is **Active**.

---

## ✅ Deliverables Checklist
- [ ] Data imported and Power Query transformations applied
- [ ] "Location" and "Profit Margin" custom columns created
- [ ] "Profit Status" conditional column created
- [ ] "Orders Data" merged table created
- [ ] Missing values & duplicates identified and handled
- [ ] Sorting and filtering applied on "Orders Data"
- [ ] Grouped/aggregated summary tables created
- [ ] Relationships established and active in the Data Model

---

## 🛠 Tool
- **Power BI Desktop** (Power Query Editor + Data Modeling view)

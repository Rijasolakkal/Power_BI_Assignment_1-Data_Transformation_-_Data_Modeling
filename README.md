# Power_BI_Assignment_1-Data_Transformation_-_Data_Modeling
Power BI - Data Transformation &amp; Data Modeling
# Power BI Assignment 1 – Data Transformation & Data Modeling

## Overview

In this exercise, Power BI was used to import, transform, clean, merge, analyze, and model the provided data.

The main tables used in this assignment are:

- List of Orders
- Order Details
- Sales Target

---

## 1. Import Data

The following CSV files were imported into Power BI:

- List of Orders.csv
- Order Details.csv
- Sales target.csv

The tables were opened in Power Query Editor for data transformation and preparation.

---

## 2. Data Transformation

### List of Orders

The following transformations were performed on the `List of Orders` table:

- Restricted the table to the first **500 rows**.
- Changed the `Order Date` column to the **Date** data type.
- Changed the `Amount` column to **Fixed Decimal Number**.
- Formatted the `CustomerName` column using **Proper Case** for consistent capitalization.
- Merged the `State` and `City` columns to create a new `Location` column.
- The `Location` column was created in the format:

  `City, State`

### Sales Target

- Changed the `Target` column to **Fixed Decimal Number**.
- Changed `Month of Order Date` to the appropriate **Date** data type.

---

## 3. Profit Margin

A custom column named **Profit Margin** was created using the following calculation:

`Profit Margin = Profit / Amount`

This was created using a Custom Column in Power Query.

---

## 4. Profit Status

A conditional column named **Profit Status** was created based on the values in the `Profit` column.

The conditions were:

- If Profit < 0 → **Loss**
- If Profit = 0 → **Break-Even**
- If Profit > 0 → **Profit**

---

## 5. Merging Data

The `List of Orders` and `Order Details` tables were merged using the common:

**Order ID**

The merged query was named:

**Orders Data**

The required columns from `Order Details` were expanded into the merged table.

---

## 6. Handling Missing Data and Duplicate Data

The data was checked for:

- Missing values
- Duplicate rows

Appropriate strategies were used to address the identified data-quality issues.

Repeated `Order ID` values in the `Orders Data` table were retained where they represented multiple order-detail records belonging to the same order.

---

## 7. Sorting and Filtering Data

### Sorting

The `Orders Data` table was sorted by:

**Order Date – Descending**

This allows the most recent orders to appear first.

### Filtering

The `Orders Data` table was filtered using the `State` column.

The selected state was:

**Tamil Nadu**

This was used for regional analysis.

---

## 8. Grouping and Aggregating Data

### Count of Each Order ID

The `Order Details` table was duplicated.

The duplicated table was grouped by:

**Order ID**

Operation:

**Count Rows**

This was used to determine the number of records associated with each Order ID.

---

### Average Profit by Category

The `Order Details` table was duplicated and grouped by:

**Category**

The following aggregation was performed:

- Operation: **Average**
- Column: **Profit**

The resulting column was named:

**Average Profit**

The categories included:

- Furniture
- Clothing
- Electronics

---

### Total Target by Month

The `Sales Target` table was duplicated.

The table was grouped by:

**Month of Order Date**

The following aggregation was performed:

- Operation: **Sum**
- Column: **Target**

The resulting column was named:

**Total Target**

This provides the total target amount for each month.

---

## 9. Data Modeling

Relationships were established between the tables using the required columns.

### Order ID Relationship

A relationship was established between:

**Order Details → List of Orders**

Using:

**Order ID**

Relationship:

- Cardinality: **Many-to-One (*:1)**
- Status: **Active**

---

### Category Relationship

A relationship was established between:

**Order Details → Sales Target**

Using:

**Category**

Relationship:

- Cardinality: **Many-to-Many (*:*)**
- Status: **Active**
- Cross-filter direction: **Both**

---

## 10. Final Tables / Queries

The Power BI model contains the following main tables and queries:

- **List of Orders**
- **Order Details**
- **Sales Target**
- **Orders Data**
- **Profit by Category**
- **Sales Target by Month**

The transformed data is prepared for further analysis and visualization.

---

## 11. Tools and Features Used

- Microsoft Power BI Desktop
- Power Query Editor
- Data Type Transformation
- Proper Case Formatting
- Merge Columns
- Custom Columns
- Conditional Columns
- Merge Queries
- Expand Columns
- Duplicate Queries
- Group By
- Aggregation
- Sorting
- Filtering
- Data Modeling
- Relationships

---

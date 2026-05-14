# Excel Data Cleaning & Transformation Pipeline using Power Query

## Project Overview

This project demonstrates the development of a refreshable ETL (Extract, Transform, Load) workflow in Microsoft Excel using Power Query and the Olist Brazilian E-Commerce dataset.

The objective of the project was to simulate a real-world data preparation process by importing, cleaning, transforming, validating, and merging multiple raw transactional datasets into a single analysis-ready table.

The project focuses on data quality, transformation logic, relational joins, and validation processes commonly used in business intelligence and data analytics workflows.

---

## Project Objectives

- Import and manage multiple raw datasets using Power Query
- Clean and standardise inconsistent data
- Handle missing values and invalid records
- Create calculated and derived columns
- Merge multiple datasets into a consolidated analytical table
- Perform validation and quality assurance checks
- Build a refreshable ETL pipeline within Excel

---

## Tools & Skills Used

- Microsoft Excel
- Power Query
- Data Cleaning & Transformation
- ETL Workflow Design
- Multi-Table Joins
- Data Validation
- Data Modelling Concepts
- Analytical Table Design
- Data Quality Assessment

---

## Dataset

Dataset used:
- Olist Brazilian E-Commerce Public Dataset

Source:
- Kaggle

Tables used in this project:
- `olist_orders_dataset.csv`
- `olist_order_items_dataset.csv`
- `olist_products_dataset.csv`
- `olist_customers_dataset.csv`
- `olist_order_payments_dataset.csv`

---

## Data Preparation & Transformation

### Data Cleaning

The following cleaning processes were applied:

- Standardised text formatting
- Corrected and validated data types
- Handled missing and null values
- Removed duplicate records where appropriate
- Standardised city and payment category naming
- Replaced transformation errors with null values
- Applied delivery and payment quality checks

---

### Derived Columns Created

The following calculated fields were created during transformation:

| Column | Purpose |
|---|---|
| Delivery Days | Days between purchase and customer delivery |
| Total Value | Product price plus freight value |
| Size | Product size classification based on weight |
| Payment Category | Standardised grouping of payment methods |

---

## Merge Architecture

The final analytical table was created using multiple relational merges within Power Query.

### Merge Sequence

```text
Orders
   ↓
Customers
   ↓
Order_Items
   ↓
Products
   ↓
Payments

## Join Keys Used

| Merge | Join Key |
|---|---|
| Orders → Customers | customer_id |
| Orders → Order_Items | order_id |
| Order_Items → Products | product_id |
| Orders → Payments | order_id |

```markdown
...
```

## Final Analytical Table

The final output table contains:

- Customer information
- Product information
- Order details
- Payment details
- Shipping metrics
- Delivery performance metrics

### Final Dataset Size
- 118,434 rows

---

## Validation & Quality Checks

Validation checks were performed to ensure data quality and transformation integrity.

### Validation Areas

- Missing value checks
- Negative value checks
- Delivery anomaly checks
- Potential duplicate transaction checks
- Row count verification

### Validation Results

| Check | Result |
|---|---|
| Missing Order IDs | 0 |
| Missing Customer IDs | 0 |
| Missing Product IDs | 830 |
| Missing Payment Values | 3 |
| Negative Prices | 0 |
| Negative Freight Values | 0 |
| Negative Payment Values | 0 |
| Delivery Days < 0 | 0 |
| Delivery Days > 60 | 327 |

### Notes

- Some records contained missing Product IDs due to incomplete source relationships after merge operations.
- Orders exceeding 60 delivery days were retained and flagged as potential operational outliers rather than removed.
- Potential duplicate transaction combinations may represent legitimate repeat purchases or multi-item orders.

---

## Data Dictionary

A separate Data Dictionary sheet was created to document:

- Column definitions
- Data types
- Source tables
- Custom calculated fields

---

## Key Outcomes

This project demonstrates:

- Advanced Excel and Power Query capability
- Real-world data transformation workflows
- Relational merge logic
- ETL pipeline design principles
- Data quality validation processes
- Analytical modelling concepts

---

## Future Improvements

Potential future enhancements include:

- Power BI integration
- SQL database implementation
- Automated refresh workflows
- Dashboard layer for reporting and analytics
- Advanced anomaly detection

---

## Contact

If you would like to discuss this project or opportunities in data analytics, feel free to connect.

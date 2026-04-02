# data-warehouse-analytics-project
SQL-based business analytics project built on a data warehouse (medallion architecture), featuring customer and product KPI reports.

The gold layer provides clean, analytics-ready data, which is used here to create customer and product reports with key performance indicators (KPIs) and segmentation logic.

This repository focuses on the **analytics layer**, where complex SQL queries are used to extract meaningful insights from the warehouse.

---

## Data Source
The data used in this project comes from my Data Warehouse project:

[https://github.com/TasneemY23/data-warehouse-project](https://github.com/TasneemY23/sql-data-warehouse-project)

### Warehouse Layers overview:
- **Bronze layer:** Raw data ingestion from CSV files  
- **Silver layer:** Data cleaning and transformation  
- **Gold layer:** Star schema (fact + dimension tables) ready to be used for analytics

---

## Reports Included

### Customer Report ('gold.report_customers')

This report consolidates key customer metrics and behaviors.

#### Features:
- Customer segmentation:
  - **VIP**
  - **Regular**
  - **New**
- Age grouping:
  - Under 20, 20–29, 30–39, 40–49, 50+

#### KPIs:
- Total orders  
- Total sales  
- Total quantity purchased  
- Total distinct products  
- Customer lifespan (months)  
- Recency (months since last order)  
- Average order value (AOV)  
- Average monthly spend  

**Purpose:** Understand customer behavior, engagement, and value.

---

### Product Report ('gold.report_products')

This report analyzes product performance and revenue contribution.

#### Features:
- Product segmentation:
  - **High-Performer**
  - **Mid-Range**
  - **Low-Performer**

#### KPIs:
- Total orders  
- Total sales  
- Total quantity sold  
- Total unique customers  
- Product lifespan (months)  
- Recency (months since last sale)  
- Average selling price  
- Average order revenue (AOR)  
- Average monthly revenue  

**Purpose:** Evaluate product performance and identify top-performing products.

---

## Technologies Used

- **SQL Server (SSMS)**
- **T-SQL**
  - CTEs
  - Aggregations
  - CASE statements
- **Data Warehouse Modeling**
  - Star schema (fact + dimensions)
- **ETL Pipeline**
  - Bronze -> Silver -> Gold architecture

---

## How to Use

1. Ensure the Data Warehouse is created and populated  
2. Run the Gold layer views:

```sql
SELECT * FROM gold.report_customers;
SELECT * FROM gold.report_products;

# 🚀 Olist E-Commerce Data Engineering Project(azure-adls-databricks-pipeline)


## 📌 Project Overview

This project demonstrates an end-to-end Data Engineering pipeline built using Azure Data Lake Storage Gen2 (ADLS Gen2), Databricks, PySpark, SQL, and Delta Lake following the Medallion Architecture (Bronze → Silver → Gold).

The pipeline processes Olist E-Commerce data, performs data quality checks, applies business transformations, and generates analytical datasets for reporting and business insights.

---

## 🛠️ Technology Stack

- Azure Data Lake Storage Gen2 (ADLS Gen2)
- Azure Databricks
- PySpark
- SQL
- Delta Lake
- Databricks Dashboard

---

## 🏗️ Architecture

```text
Olist CSV Files
        │
        ▼
Azure Data Lake Storage Gen2
        │
        ▼
Bronze Layer
(Raw Data Ingestion)
        │
        ▼
Silver Layer
(Data Cleaning, Validation,
Joins, Feature Engineering,
Window Functions)
        │
        ▼
Gold Layer
(Business Analytics &
Aggregated KPIs)
        │
        ▼
Dashboard & Insights
```

---

## 🥉 Bronze Layer

### Objective

Ingest raw CSV files into Databricks and store them as Delta tables.

### Activities

- Read CSV files from ADLS Gen2
- Schema validation
- Data exploration
- Record count validation
- Delta table creation

### Bronze Tables

- bronze_customer
- bronze_order
- bronze_order_item
- bronze_order_payment
- bronze_product

---

## 🥈 Silver Layer

### Objective

Transform raw data into analytics-ready datasets.

### Data Quality Checks

- Null value analysis
- Missing value handling
- Duplicate checks
- Data validation
- Data standardization

### Transformations

- Multi-table joins
- Feature engineering
- Customer segmentation
- Customer ranking
- Product ranking
- Seller ranking
- Window functions

### Silver Tables

- silver_sales_ecom
- silver_customer_rank
- silver_customer_segmentation

---

## 🥇 Gold Layer

### Objective

Create business-focused analytical datasets for reporting and dashboarding.

### Gold Tables

#### Customer Analytics

- Total Orders
- Total Spend
- Average Order Value

Table:
- gold_customer_analytics

#### Product Analytics

- Product Revenue Analysis
- Product Performance Analysis

Table:
- gold_product_analytics

#### Payment Analytics

- Revenue by Payment Type
- Payment Method Analysis

Table:
- gold_payment_analytics

#### Monthly Revenue Analytics

- Monthly Revenue Trend
- Revenue Monitoring

Table:
- gold_monthly_revenue

#### KPI Dashboard

- Total Revenue
- Total Customers
- Average Order Value

Table:
- gold_kpi_dashboard

---

## 📊 Dashboard

Created an interactive dashboard using Gold Layer tables.

### KPIs

- Total Revenue
- Total Customers
- Average Order Value

### Analytics

- Monthly Revenue Trend
- Top Product Categories
- Payment Method Analysis
- Customer Analytics

---

## ⚡ Delta Lake Features Implemented

### Describe History

```sql
DESCRIBE HISTORY bronze_customer;
```

### Describe Detail

```sql
DESCRIBE DETAIL bronze_customer;
```

### Update

```sql
UPDATE bronze_customer
SET customer_city='TEST_CITY'
WHERE customer_city='sao paulo';
```

### Delete

```sql
DELETE FROM bronze_customer
WHERE customer_city='TEST_CITY';
```

### Time Travel

```sql
SELECT *
FROM bronze_customer VERSION AS OF 0;
```

### Optimize

```sql
OPTIMIZE bronze_customer;
```

### Vacuum

```sql
VACUUM bronze_customer RETAIN 168 HOURS;
```

---

## 📈 Business Insights

- Identified high-value customers using customer segmentation.
- Analyzed top-performing product categories.
- Evaluated monthly revenue trends.
- Analyzed customer purchasing behavior.
- Studied payment method preferences.

---

## 🎯 Key Learnings

- Medallion Architecture
- Azure Data Lake Storage Gen2
- Databricks
- PySpark Transformations
- Delta Lake
- Window Functions
- Data Quality Checks
- Customer Segmentation
- Multi-Table Joins
- Dashboard Development

---

End-to-End Data Engineering Project using Azure, Databricks, PySpark, SQL, and Delta Lake.

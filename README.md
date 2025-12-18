# End-to-End Data Engineering ETL Pipeline

## Project Overview
This project demonstrates an end-to-end Data Engineering ETL pipeline that ingests raw CSV data, performs data transformation and enrichment using Python, and loads analytics-ready data into PostgreSQL for SQL-based reporting and analysis. The pipeline follows industry-standard practices such as data layering, batch ingestion, and performance optimization.

---

## Architecture
Raw CSV Files  
→ Python & Pandas (Data Transformation)  
→ Processed Fact Table  
→ PostgreSQL (Analytics & Reporting)

---

## Tech Stack
- Python (Pandas)
- PostgreSQL
- psycopg2
- SQL
- Jupyter Notebook
- Git

---

## Project Structure

data-engineering-etl-project/
│
├── data/
│ ├── raw/
│ │ ├── customers.csv
│ │ ├── products.csv
│ │ └── sales.csv
│ └── processed/
│ └── fact_sales.csv
│
├── notebooks/
│ ├── 01_extract_transform.ipynb
│ └── 02_load_to_postgres.ipynb
│
├── sql/
│ └── analytics_queries.sql
│
└── README.md

---

## ETL Workflow

### Extract
- Loaded raw CSV datasets containing customer, product, and sales information using Pandas.

### Transform
- Cleaned and standardized raw data.
- Joined transactional data with customer and product dimension data.
- Created derived business metrics such as revenue.
- Performed basic data quality validation.

### Load
- Created an analytics-ready fact table in PostgreSQL.
- Loaded transformed data using psycopg2 for reliable batch ingestion.

---

## Sample SQL Analytics Queries

### Total Revenue by Product
```sql
SELECT product_name, SUM(revenue) AS total_revenue
FROM fact_sales
GROUP BY product_name
ORDER BY total_revenue DESC;

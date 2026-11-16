# Retail Sales Data Engineering Pipeline

An end-to-end batch data engineering pipeline built using **Databricks, PySpark, Delta Lake, and Unity Catalog**.

## Project Overview

This project processes retail customer, product, and order data through a scalable data pipeline using the Medallion Architecture.

The pipeline performs raw data ingestion, data cleaning, transformation, integration, and business analytics. Databricks Workflows orchestrates the execution of all pipeline stages.

## Architecture

```text
CSV Data Sources
       |
       v
BRONZE LAYER
Raw Delta Tables
       |
       v
SILVER LAYER
Cleaning and Standardization
Business Transformations
Data Integration
       |
       v
GOLD LAYER
Monthly Sales
Yearly Sales
Category Sales
Product Sales
       |
       v
Databricks Workflows
Automated Pipeline Execution
```

## Technology Stack

- Databricks Free Edition
- Apache Spark
- PySpark
- Delta Lake
- Unity Catalog
- Databricks Workflows
- Python
- SQL
- GitHub

## Dataset

The project uses synthetic retail datasets.

| Dataset | Records |
|---|---:|
| Customers | 600 |
| Products | 114 |
| Orders | 10,465 |

## Medallion Architecture

### Bronze Layer
- Ingests raw CSV datasets.
- Stores data in Delta tables.
- Preserves original source records.

### Silver Layer
- Removes duplicate records.
- Handles missing values.
- Standardizes text fields.
- Calculates gross sales, discounts, and net sales.
- Classifies order statuses.
- Integrates customer, product, and order data.

### Gold Layer
Creates four analytics-ready datasets:

- Monthly sales analysis
- Yearly sales analysis
- Category-wise sales analysis
- Product-wise sales analysis

## Databricks Workflow

The pipeline consists of three dependent notebook tasks:

1. `01_Bronze_Ingestion`
2. `02_Silver_Processing`
3. `03_Gold_Analytics`

The complete workflow has been successfully executed and configured for daily scheduled execution.

## Final Results

| Layer | Table | Records |
|---|---|---:|
| Bronze | Customers | 600 |
| Bronze | Products | 114 |
| Bronze | Orders | 10,465 |
| Silver | Retail Sales | 10,447 |
| Gold | Monthly Sales | 36 |
| Gold | Yearly Sales | 3 |
| Gold | Category Sales | 6 |
| Gold | Product Sales | 114 |

## Repository Structure

```text
retail-sales-data-engineering/
│
├── notebooks/
│   ├── 01_Bronze_Ingestion
│   ├── 02_Silver_Processing
│   └── 03_Gold_Analytics
│
├── docs/
│
└── README.md
```

## Future Improvements

- Incremental data ingestion
- Automated new-file detection
- Data quality monitoring
- Pipeline failure alerts
- Power BI or Databricks dashboard integration

## Disclaimer

All datasets used in this project are synthetic and intended for educational and portfolio purposes.

# Northwind ERP Sales Intelligence Platform
### Microsoft Fabric | Medallion Architecture | PySpark | Power BI
## Project Overview
End-to-end data engineering project built entirely on Microsoft Fabric,
transforming raw Northwind ERP CSV files into a live Power BI dashboard
through a full medallion architecture pipeline.

## Architecture
Raw CSV → Bronze → Silver → Gold → Semantic Model → Power BI
## Layers Built
| Layer | Tool | Purpose |
|---|---|---|
| Raw | OneLake Files | CSV landing zone |
| Bronze | PySpark Notebook | Delta ingestion + audit columns |
| Silver | PySpark Notebook | Data quality fixes |
| Gold | PySpark Notebook | Star schema for analytics |
| Semantic Model | Fabric Semantic Model | Relationships + DAX measures |
| Dashboard | Power BI | Business intelligence |

## Data Quality Issues Found & Fixed
| Finding | Issue | Fix Layer |
|---|---|---|
| String NULL contamination | 507 rows in orders.shipRegion stored as text "NULL" | Silver |
| Wrong data type | shippedDate stored as string not timestamp | Silver |

## Gold Star Schema
- `fact_sales` — 2155 rows (order line items)
- `dim_customer` — 91 rows
- `dim_product` — 77 rows
- `dim_employee` — 9 rows
- `dim_date` — 672 rows (generated)

## DAX Measures
- Total Revenue = 1.27M
- Total Orders = 830
- Avg Order Value

## Tech Stack
Microsoft Fabric, PySpark, Delta Lake, OneLake,
SQL Analytics Endpoint, DAX, Power BI

## Author
Charan Gnanappan | Data Engineer

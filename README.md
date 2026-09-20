# 🚕 NYC Taxi End-to-End Azure Data Engineering Pipeline

An end-to-end data engineering solution built on Azure to ingest, transform, and analyze NYC Green Taxi trip data. The pipeline follows the Medallion Architecture (Bronze -> Silver -> Gold) using Azure Data Factory, Azure Databricks, Delta Lake, and Power BI.

---

## 🏗️ Architecture Overview

```text
[NYC Taxi Data / Web] 
         │
         ▼
[Azure Data Factory] ──(Dynamic Ingestion)──► [ADLS Gen2 - Bronze Layer (Raw Parquet/CSV)]
                                                            │
                                                            ▼
                                           [Azure Databricks - PySpark]
                                                            │
                                    ┌───────────────────────┴───────────────────────┐
                                    ▼                                               ▼
                     [Silver Layer (Cleaned Delta)]                   [Gold Layer (Curated Delta)]
                                                                                    │
                                                                                    ▼
                                                                           [Power BI Analytics]

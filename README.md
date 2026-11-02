# Airline Operations & Performance Analytics

An end-to-end cloud data engineering and business intelligence project using Azure Data Factory, Azure Data Lake Storage Gen2, Azure Databricks, PySpark and Power BI.

## Project Overview

This project processes airline flight operations data to generate insights into flight performance, delays, routes, aircraft utilization and revenue.

The source dataset contains 1,000 flight records stored in a CSV file.

## Technology Stack

- **Source Control:** Git, GitHub
- **Orchestration:** Azure Data Factory
- **Cloud Storage:** Azure Data Lake Storage Gen2
- **Data Transformation:** Azure Databricks, PySpark
- **Data Formats:** CSV, Parquet / Delta
- **Visualization:** Power BI

## Data Source

- File: `data/flights.csv`
- Format: CSV
- Records: 1,000
- Columns: 11

## Current Data Ingestion Architecture

```text
GitHub Repository
    |
    | HTTP Linked Service
    v
Azure Data Factory
    |
    | Copy Activity
    v
ADLS Gen2
    |
    v
Bronze Container
    |
    v
Raw_flights/
    |
    v
flights.csv
```

The source CSV is maintained in the GitHub repository and ingested into the Bronze layer of ADLS Gen2 using an Azure Data Factory Copy Activity.

## Planned Data Engineering Architecture

```text
GitHub (CSV Source)
        |
        v
Azure Data Factory
        |
        v
ADLS Gen2 - Bronze
        |
        v
Azure Databricks / PySpark
        |
        v
ADLS Gen2 - Silver
        |
        v
ADLS Gen2 - Gold
        |
        v
Power BI
```

## Project Layers

| Layer    | Responsibility                               |
| -------- | -------------------------------------------- |
| Bronze   | Store the original ingested source data      |
| Silver   | Clean, validate and transform flight records |
| Gold     | Store analytical datasets and business KPIs  |
| Power BI | Present airline operations insights          |

## Planned Analytics

- Flight completion and cancellation analysis
- Flight delay analysis
- Route performance
- Aircraft utilization
- Revenue analysis
- Pipeline execution monitoring

## Project Status

- [x] Local project setup
- [x] Source dataset added to GitHub
- [x] Azure Data Factory resource created
- [x] ADLS Gen2 containers created
- [x] ADF HTTP and ADLS linked services configured
- [x] CSV ingested into the Bronze layer
- [ ] Silver-layer transformations
- [ ] Gold-layer analytical datasets
- [ ] Pipeline monitoring dashboard
- [ ] Power BI dashboard

## Repository Structure

```text
AirLineOperationAnalytics/
├── data/
│   └── flights.csv
├── adf/
│   ├── pipelines/
│   ├── datasets/
│   └── linked_services/
├── notebooks/
├── src/
├── config/
├── tests/
├── docs/
├── powerbi/
├── README.md
├── requirements.txt
└── .gitignore
```

## Note

Azure services are used as the execution and storage environment. The GitHub repository maintains project source files, exported Azure configurations, documentation and dashboard deliverables.

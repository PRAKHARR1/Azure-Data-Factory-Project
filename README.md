# Azure Data Engineering Project using Azure Data Factory, Databricks & Azure SQL

## Project Overview

This project demonstrates an end-to-end Azure Data Engineering pipeline using Azure Data Factory, Azure Databricks, Azure Data Lake Storage, and Azure SQL Database.

The project processes raw World Wide Importers (WWI) CSV files, converts them into Parquet format, performs data cleaning and transformation using Databricks, and stores analytical business data into Azure SQL Database for reporting and business decision-making.

---

# Project Architecture

1. Create Azure Resource Group
2. Create Azure Storage Account
3. Create Storage Containers
4. Upload Raw CSV Files
5. Create Azure Data Factory Pipeline
6. Convert CSV Files to Parquet
7. Store Parquet Files in Staging Container
8. Connect Azure Databricks with Azure Data Lake Storage
9. Perform Data Cleaning and Transformation
10. Generate Business Insights
11. Store Final Analytical Data into Azure SQL Database

---

# Technologies Used

- Azure Resource Group
- Azure Storage Account
- Azure Data Lake Storage Gen2
- Azure Data Factory
- Azure Databricks
- Azure SQL Database
- Parquet File Format
- PySpark

---

# Step 1: Create Azure Resource Group

First, a Resource Group was created in Azure Portal to manage all project resources under one environment.

Example:
- Resource Group Name: `wwi-project-rg`

---

# Step 2: Create Azure Storage Account

An Azure Storage Account was created for storing raw, staging, and processed data.

## Containers Created

| Container Name | Purpose |
|----------------|---------|
| storage | Store raw CSV files |
| staging | Store converted Parquet files |
| process | Store cleaned and transformed data |

---

# Step 3: Upload Raw WWI Data

The following WWI CSV files were uploaded into the `storage` container:

- DimAccount.csv
- DimDate.csv
- DimStrategy.csv
- DimEntity.csv
- DimCustomer.csv
- FactSales.csv

---

# Step 4: Create Azure Data Factory

An Azure Data Factory instance was created inside the Resource Group.

## Pipeline Created

Pipeline Name:
- `pl_first`

---

# Step 5: Configure Lookup Activity

A Lookup Activity was added to the pipeline.

Purpose:
- Read JSON configuration file
- Dynamically process multiple files

A JSON dataset was created and uploaded for file mapping configuration.

---

# Step 6: Configure ForEach Activity

A ForEach Activity was added to process all CSV files dynamically.

Inside the ForEach Activity:
- Copy Data Activity was added
- Dynamic content expressions were used
- Parameterized datasets were configured

---

# Step 7: CSV to Parquet Conversion

Inside Copy Data Activity:

## Source
- CSV files from `storage` container

## Sink
- Parquet files into `staging` container

## Configurations
- Source dataset configuration
- Sink dataset configuration
- Column mapping
- Dynamic file handling
- Parameterized pipeline

After debugging and successful execution, all CSV files were converted into Parquet format.

---

# Step 8: Create Azure Databricks

Azure Databricks workspace was created using Azure Portal.

---

# Step 9: Connect Azure Data Lake Storage with Databricks

Using Databricks Connector and Linked Services, Azure Data Lake Storage was connected with Azure Databricks.

This connection allowed Databricks to access staging data directly.

---

# Step 10: Data Cleaning and Transformation

Data cleaning operations were performed in Databricks using PySpark.

## Operations Performed

- Null value handling
- Duplicate removal
- Data type conversion
- Table creation
- Data transformation
- Business calculations

Cleaned and transformed data was stored into the `process` container.

---

# Step 11: Business Analytics

Using transformed data, business analytical reports were generated:

- Total Sales
- Month-wise Sales
- City-wise Sales
- Customer Analysis
- Product Analysis

These analytical datasets help in business decision-making.

---

# Step 12: Azure SQL Database Integration

An Azure SQL Database was created to store final reporting tables.

## Linked Services Created

- Azure Data Lake Storage Linked Service
- Azure SQL Database Linked Service
- Azure Databricks Linked Service

Final transformed data was loaded into Azure SQL tables for reporting purposes.

---

# Project Outcome

This project successfully demonstrates:

- End-to-End Azure Data Engineering Pipeline
- Dynamic ETL Process using Azure Data Factory
- CSV to Parquet Conversion
- Data Cleaning using Databricks
- Business Analytics Generation
- Data Storage in Azure SQL Database

---

# Future Enhancements

- Power BI Dashboard Integration
- Incremental Data Loading
- Pipeline Scheduling
- CI/CD using Azure DevOps
- Monitoring & Alerting
- Data Quality Validation

---

# Author

Azure Data Engineering Project using:

- Azure Data Factory
- Azure Databricks
- Azure Data Lake Storage
- Azure SQL Database
- PySpark

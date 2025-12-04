# fabric-sales-analytics-pipeline

# Fabric Sales Analytics Pipeline

## 📌 Project Overview
This project demonstrates an end-to-end automated data analytics pipeline built using Microsoft Fabric Lakehouse architecture to process sales data from raw files to analytics-ready datasets following the Medallion Architecture approach.

The pipeline ingests raw sales data, transforms it through multiple layers (Landing, Bronze, Silver, Gold), applies data cleaning and transformation logic, builds dimensional models (Fact & Dimension tables), and finally prepares the dataset for reporting in Power BI through a semantic model.

---

## 🏗 Architecture Overview

Raw Data → Landing → Bronze → Silver → Gold → Semantic Model → Power BI Reports


This architecture ensures:
- Scalable data ingestion
- Data quality enforcement
- Structured modeling for reporting
- Automation and pipeline orchestration
- Incremental data processing

---

## 🚀 Pipeline Workflow

### 1. Raw → Landing (File Ingestion)
- Raw datasets are uploaded into the Raw folder in the Lakehouse.
- A dynamic notebook loads files into the Landing zone.
- Incremental loading is implemented based on:
  - File name
  - Processing date
- Ensures only new files are processed.

---

### 2. Landing → Bronze (Structured Tables)
- Schemas and tables are created in the Bronze layer.
- Data is stored in structured Lakehouse tables.
- A new column `Processing_Date` is added to track ingestion.
- SCD Type 1 logic is implemented to maintain the latest data.

---

### 3. Bronze → Silver (Data Cleaning & Transformations)
- Extracts only today's newly ingested records.
- Performs:
  - Null value handling
  - Data standardization
  - Type conversions
  - Business rule transformations
- Cleaned and transformed data is stored in Silver tables.
- SCD Type 1 logic applied.

---

### 4. Silver → Gold (Dimensional Modeling)
- Silver data is split into:
  - Fact tables
  - Dimension tables
- Star schema is implemented.
- Tables are optimized for analytics and reporting.

---

### 5. Semantic Model & Power BI
- A semantic model is created from Fact and Dimension tables.
- Relationships are defined.
- Power BI connects to the model for analytics and visualization.

---

### 6. Automation Using Fabric Pipeline
- All notebooks are executed through a single pipeline.
- Trigger is configured:
  - When a new file is uploaded, the pipeline runs automatically.
- Enables real-time ingestion and processing.

---

## 🛠 Technology Stack

- Microsoft Fabric  
- Lakehouse  
- PySpark  
- Spark SQL  
- Delta Tables  
- Medallion Architecture  
- Slowly Changing Dimension (SCD Type 1)  
- Power BI  
- Fabric Pipelines  
- Dimensional Modeling  

---

## 🎯 Key Features

- Incremental file ingestion  
- Layered Medallion architecture  
- Automated pipeline execution  
- Data cleaning and transformation  
- Dimensional modeling  
- Power BI-ready datasets  
- Trigger-based automation  






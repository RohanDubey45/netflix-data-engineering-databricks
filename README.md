# Netflix Azure Data Engineering End to End Pipeline using Azure Databricks 

## 📌 Project Overview
This project demonstrates an **end-to-end data engineering pipeline** built using **Azure Databricks**, **Delta Lake**, and **Delta Live Tables (DLT)**.  
The pipeline ingests raw Netflix data, processes it using the **Medallion Architecture (Bronze, Silver, Gold)**, enforces **data quality rules**, and publishes **analytics-ready Gold tables** using modern data engineering best practices.

This project is designed to simulate a **real-world, production-grade data platform**.

---

## 🏗️ Architecture Overview

**Data Flow:**
Raw CSV Files (ADLS Gen2)
↓
Databricks Auto Loader (Incremental Ingestion)
↓
Bronze Layer (Raw Data)
↓
Silver Layer (Cleaned & Transformed Data)
↓
Gold Layer (Business-Ready Tables using DLT)

---

**Key Concepts Used:**
- Incremental ingestion using Auto Loader
- Streaming transformations
- Medallion architecture
- Data quality enforcement with DLT expectations
- Centralized governance using Unity Catalog

---

## 🛠️ Tech Stack

- **Azure Databricks**
- **Azure Data Lake Storage Gen2 (ADLS)**
- **Delta Lake**
- **Delta Live Tables (DLT)**
- **Unity Catalog**
- **Python**
- **SQL**
- **Apache Spark (Structured Streaming)**

---

## 📂 Project Structure

netflix-data-engineering-databricks/
```
├── 1_AutoLoader.ipynb
├── 2_silver.ipynb
├── 3_lookup.ipynb
├── 4_silver.ipynb
├── 5_LookUpNotebook.ipynb
├── 6_GetDayNumber.ipynb
├── 7_DLT_Notebook.ipynb
└── README.md
```



## 📘 Notebook Descriptions

### 1️⃣ Auto Loader (1_AutoLoader.ipynb)
- Ingests Netflix CSV files from ADLS Gen2
- Uses **Databricks Auto Loader**
- Supports **incremental file ingestion**
- Stores raw data in **Bronze Delta tables**

---

### 2️⃣ Silver Layer Transformations (2_silver.ipynb & 4_silver.ipynb)
- Cleans raw data
- Handles null values
- Parses and standardizes date formats
- Splits duration fields (minutes / seasons)
- Applies schema normalization

---

### 3️⃣ Lookup Processing (3_lookup.ipynb & 5_LookUpNotebook.ipynb)
- Creates lookup datasets
- Supports downstream joins and enrichments
- Improves query performance and readability

---

### 4️⃣ Utility Notebook (6_GetDayNumber.ipynb)
- Derives weekday/day-number logic
- Demonstrates parameter passing using Databricks widgets
- Shows job task value handling

---

### 5️⃣ Gold Layer using Delta Live Tables (7_DLT_Notebook.ipynb)
- Creates **Gold tables** using **DLT**
- Reads from Silver Delta tables
- Applies **data quality rules using DLT expectations**
- Publishes curated, analytics-ready datasets

---

## 🥇 Gold Tables Created

- `gold_netflix_titles`
- `gold_netflix_cast`
- `gold_netflix_directors`
- `gold_netflix_categories`
- `gold_netflix_countries`

These tables are:
- Fully managed by **Delta Live Tables**
- Registered in **Unity Catalog**
- Stored as **Delta tables** in the configured storage location

---

## ✅ Data Quality & Governance

- Implemented **DLT expectations** to validate data (e.g., non-null IDs)
- Invalid records are automatically dropped
- Centralized metadata and access control using **Unity Catalog**
- Built-in lineage and monitoring via Databricks UI

---

## 📊 Pipeline Execution

- Pipeline executed using **Databricks Delta Live Tables**
- Supports **streaming execution**
- Monitoring available via:
  - Pipeline graph
  - Event logs
  - Data quality metrics

---

## 🚀 Key Learnings

- Designing end-to-end data pipelines on Azure
- Incremental ingestion with Auto Loader
- Streaming vs batch processing
- Implementing Medallion Architecture
- Building governed datasets with Unity Catalog
- Enforcing data quality using Delta Live Tables
- Version control integration with GitHub

---

---

## 👤 Author

**Rohan Dubey**  
Aspiring Data Engineer  
GitHub: https://github.com/RohanDubey45  

---

⭐ If you find this project useful, feel free to star the repository!

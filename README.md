# 🏥 Healthcare Lakehouse Analytics Platform

## 📌 Project Overview

This project implements an end-to-end Healthcare Data Engineering Platform using the Azure ecosystem and Medallion Architecture (Bronze, Silver, Gold).

The objective is to create a centralized, scalable, and analytics-ready data repository that serves as a single source of truth for Data Analytics, Business Intelligence, and Data Science teams.

The solution integrates healthcare data from multiple source systems, applies data quality and transformation rules, builds dimensional models, and delivers business insights through Power BI dashboards.

---

# 🎯 Business Objective

Healthcare organizations often store patient, provider, encounter, and diagnosis information across multiple systems.

The goal of this project is to:

- Centralize healthcare data into a unified platform
- Improve data quality and consistency
- Enable advanced analytics and reporting
- Support Data Science and AI initiatives
- Provide business-ready datasets for stakeholders

---

# 🏗️ Solution Architecture

Source Systems
↓
Azure Data Factory
↓
Azure Data Lake Storage Gen2
↓
Bronze Layer (Raw Data)
↓
Azure Databricks (PySpark)
↓
Silver Layer (Cleaned & Standardized Data)
↓
Gold Layer (Business-Ready Data)
↓
Azure SQL / Delta Tables
↓
Power BI Dashboard

---

# ☁️ Azure Services Used

| Service | Purpose |
|----------|----------|
| Azure Data Factory | Data Ingestion & Orchestration |
| Azure Data Lake Storage Gen2 | Data Lake Storage |
| Azure Databricks | Data Transformation |
| PySpark | Data Processing |
| Delta Lake | Storage & Optimization |
| Azure SQL Database | Serving Layer |
| Power BI | Reporting & Visualization |

---

# 📂 Data Sources

The platform integrates the following healthcare datasets:

### Provider

Contains provider information:

- Provider ID
- Provider Name
- Provider Specialty
- Provider Location

### Patient

Contains patient demographics:

- Patient ID
- Gender
- Birth Date
- Primary Location

### Locations

Contains facility information:

- Location ID
- Location Name
- Service Area

### PCP

Patient primary care provider mapping.

### Encounters

Patient visit information:

- Encounter ID
- Provider
- Visit Date
- Status
- Due Date

### Encounter Diagnosis

Contains diagnosis information associated with encounters.

### Pregnancy Diagnosis

Reference table used to identify pregnancy-related encounters.

---

# 🥉 Bronze Layer

## Purpose

Store raw healthcare data exactly as received.

### Activities

- Raw file ingestion
- Schema preservation
- Audit metadata creation
- Data lineage tracking

### Data Characteristics

- No transformations
- Historical retention
- Immutable records

---

# 🥈 Silver Layer

## Purpose

Data cleansing, standardization, and enrichment.

### Transformations

### Data Quality Checks

- Null validation
- Duplicate removal
- Schema validation

### Standardization

- Column naming conventions
- Data type corrections
- Date standardization

### Business Rules

- Provider validation
- Patient validation
- Encounter standardization

### Data Enrichment

- Provider details enrichment
- Location enrichment
- Diagnosis enrichment

---

# 🥇 Gold Layer

## Purpose

Create analytics-ready datasets optimized for reporting and machine learning.

### Data Model

### Fact Table

#### Fact_Encounter

Measures:

- Total Encounters
- Completed Encounters
- Cancelled Encounters
- Pregnancy Encounters

### Dimension Tables

#### Dim_Patient

- Patient demographics

#### Dim_Provider

- Provider details

#### Dim_Location

- Location hierarchy

#### Dim_Diagnosis

- Diagnosis details

#### Dim_Date

- Calendar attributes

---

# ⭐ Data Modeling

Implemented a Star Schema design for analytics workloads.

Fact_Encounter
|
├── Dim_Patient
├── Dim_Provider
├── Dim_Location
├── Dim_Diagnosis
└── Dim_Date

Benefits:

- Faster query performance
- Simplified reporting
- Better scalability

---

# ⚡ Data Engineering Workflow

## Step 1

Azure Data Factory ingests source data into ADLS Gen2.

## Step 2

Raw files stored in Bronze layer.

## Step 3

Databricks notebooks process data using PySpark.

## Step 4

Silver layer applies:

- Cleaning
- Standardization
- Validation
- Enrichment

## Step 5

Gold layer builds dimensional models.

## Step 6

Power BI connects to curated datasets for reporting.

---

# 📊 Power BI Dashboard

Developed an executive dashboard providing insights into:

### Patient Analytics

- Total Patients
- Patient Demographics
- Gender Distribution

### Provider Analytics

- Provider Performance
- Encounters by Provider
- Specialty Analysis

### Encounter Analytics

- Total Encounters
- Completed vs Cancelled Visits
- Monthly Trends

### Pregnancy Analytics

- Pregnancy Encounters
- Diagnosis Distribution
- Due Date Monitoring

---

# 📈 Key Benefits

✅ Single Source of Truth

✅ Improved Data Quality

✅ Scalable Lakehouse Architecture

✅ Faster Reporting

✅ Analytics-Ready Data

✅ AI/ML Ready Data Assets

---

# 🛠️ Technology Stack

- Azure Data Factory
- Azure Data Lake Storage Gen2
- Azure Databricks
- PySpark
- Delta Lake
- Azure SQL Database
- Power BI
- GitHub

---

# 📂 Repository Structure

healthcare-lakehouse-platform/

├── datafactory/
│
├── databricks/
│ ├── bronze/
│ ├── silver/
│ └── gold/
│
├── notebooks/
│ ├── patient_processing.ipynb
│ ├── provider_processing.ipynb
│ ├── encounter_processing.ipynb
│ └── diagnosis_processing.ipynb
│
├── sql/
│ └── star_schema.sql
│
├── powerbi/
│ └── healthcare_dashboard.pbix
│
├── architecture/
│ └── architecture.png
│
└── README.md

---

# 🚀 Future Enhancements

- Real-time streaming ingestion
- Delta Live Tables
- dbt implementation
- Data Quality Framework
- CI/CD using Azure DevOps
- Predictive Healthcare Analytics
- Patient Risk Scoring Models

---

# 💡 Skills Demonstrated

- Data Engineering
- Azure Data Factory
- Azure Data Lake
- Azure Databricks
- PySpark
- Delta Lake
- Data Modeling
- Star Schema
- ETL Development
- Data Quality
- Healthcare Analytics
- Power BI Reporting
- Lakehouse Architecture

---

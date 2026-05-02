# SQL-DataWarehouse-Project
A comprehensive guide to building a morden data warehouse with SQL Server, including ETL processes, data modeling, and analytics.
This is a portfolio project showcasing hands-on-practical skills in data engineering on SQL and draw.oi for construction of visual diagrams.

## 🏗️ Data Architecture

<img width="2288" height="1100" alt="image" src="https://github.com/user-attachments/assets/b4733d27-d8d6-4a79-baaf-f50d7cde8439" />

The data architecture implementation follows a **Medallion architecture**, which is a data design pattern used to logically organize data in a lakehouse, with the goal of incrementally and progressively improving the structure and quality of data as it flows through each layer of the architecture (from Bronze ⇒ Silver ⇒ Gold layer tables):
- Bronze layer (raw data)
  - Landing layer of all the data from external source systems. The table structures in this layer correspond to the source system table structures "as-is," along with any additional metadata columns that capture the load date/time, process ID, etc. The focus in this layer is quick Change Data Capture (CDC) and the ability to provide a historical archive of sources (cold storage), data lineage, auditability, reprocessing without rereading the data from the source system.
- Silver layer (cleansed and conformed data
  - The Silver layer brings the data from different sources into an Enterprise view and enables self-service analytics for ad-hoc reporting, advanced analytics and Machine Learning model development.
- Gold layer (curated business-level tables)
  - Data in the Gold layer of the lakehouse is typically organized in consumption-ready "project-specific" databases. This layer is for reporting data and uses more de-normalized and read-optimized data models with fewer joins. The final layer of data transformations and data quality rules are applied here.

## 📖 Project Overview
This project involves:
The development of a modern data warehouse using SQL Server to consolidate sales data, enabling analytical reporting and informed decision-making with the following specifications:

- Data Sources: Import data from two source systems (ERP and CRM) provided as CSV files.
  - The Data Flow Diagram (DFD) depicts how the mapping of data from source systems to the madellion architecture was implemented.

<img width="1389" height="848" alt="Data Flow Diagram (3)" src="https://github.com/user-attachments/assets/a8ba6a73-3606-40b9-8cac-72126ad3edf5" />

- Data Quality: Cleanse and resolve data quality (DQ) issues prior to analysis.
- Integration: Combine both sources into a single, user-friendly data model designed for analytical queries.
- Scope: Focus on the latest dataset only; historization of data is not required.

<img width="1014" height="615" alt="image" src="https://github.com/user-attachments/assets/d60c33da-139c-4641-ae46-1c548447e9f8" />

Data Architecture: Designing a Modern Data Warehouse Using Medallion Architecture Bronze, Silver, and Gold layers.
ETL Pipelines: Extracting, transforming, and loading data from source systems into the warehouse.
Data Modeling: Developing fact and dimension tables optimized for analytical queries.
Analytics & Reporting: Creating SQL-based reports and dashboards for actionable insights.

🎯 This repository is an excellent resource for professionals and students looking to gain knowledge and showcase expertise in:

- SQL Development
- Data Architect
- Data Engineering
- ETL Pipeline Developer
- Data Modeling
- Data Analytics

## 📂 Repository Structure

      data-warehouse-project/
      │
      ├── datasets/                           # Raw datasets used for the project (ERP and CRM data)
      │
      ├── docs/                               # Project documentation and architecture details
      │   ├── data_architecture.drawio        # Draw.io file shows the project's architecture
      │   ├── data_catalog.md                 # Catalog of datasets, including field descriptions and metadata
      │   ├── data_flow.drawio                # Draw.io file for the data flow diagram
      │
      ├── scripts/                            # SQL scripts for ETL and transformations
      │   ├── bronze/                         # Scripts for extracting and loading raw data
      │   ├── silver/                         # Scripts for cleaning and transforming data
      │   ├── gold/                           # Scripts for creating analytical models
      │
      ├── tests/                              # Test scripts and quality files
      │
      ├── README.md                           # Project overview and instructions
      └── LICENSE                             # License information for the repository


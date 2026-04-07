# SQL-DataWarehouse-Project
A comprehensive guide to building a morden data warehouse with SQL Server, including ETL processes, data modeling, and analytics. By Baraa Khatib Salkini of Data with Baraa.
 Source details linked on https://github.com/DataWithBaraa/sql-data-warehouse-project

## 🏗️ Data Architecture
The data architecture implementation follows a **Medallion architecture**, which is a data design pattern used to logically organize data in a lakehouse, with the goal of incrementally and progressively improving the structure and quality of data as it flows through each layer of the architecture (from Bronze ⇒ Silver ⇒ Gold layer tables):
- Bronze layer (raw data)
  - Landing layer of all the data from external source systems. The table structures in this layer correspond to the source system table structures "as-is," along with any additional metadata columns that capture the load date/time, process ID, etc. The focus in this layer is quick Change Data Capture (CDC) and the ability to provide a historical archive of sources (cold storage), data lineage, auditability, reprocessing without rereading the data from the source system.
- Silver layer (cleansed and conformed data
  - 
- Gold layer (curated business-level tables)

# NetFlix_End_to_End

📊 End-to-End Data Engineering Pipeline Report
🧾 Project Name: Real-Time Analytics OF NetFlix with Delta Live Tables in Azure
👨‍💻 Prepared By: Vinay Jangir
🏢 Platform: Azure (ADF, Databricks, Synapse, Power BI)
🔁 1. Data Ingestion
Tools Used:

Azure Data Factory (ADF)

Databricks Autoloader

Source:

Data is ingested from external sources (files, APIs, etc.) using ADF and Databricks’ Autoloader.

Output:

Raw data is written to Azure Data Lake Gen2 (Raw Zone) as Bronze Layer (Incremental Storage).

🔄 2. Raw Data Store (Bronze Layer)
Technology:

Azure Data Lake Gen2

Purpose:

Stores raw, unprocessed, incremental data for audit and historical purposes.

Enables schema-on-read capabilities.

🔄 3. Data Transformation (Silver Layer)
Tool:

Databricks Delta Live Tables (DLT)

Operations:

Cleaning, filtering, standardizing, and joining datasets

Transformations follow Medallion Architecture (Bronze → Silver → Gold)

Storage:

Transformed data is again stored in Data Lake Gen2.

⭐ 4. Serving Layer (Gold Layer / Star Schema)
Action:

Final transformed data is structured into fact and dimension tables (Star Schema)

Used for analytics and reporting

Storage:

Data is stored in Gold Layer (Serving Zone) in Delta Lake

🏢 5. Data Warehouse
Tool:

Azure Synapse Analytics

Integration:

Gold layer data is pushed to Synapse for BI users, data scientists, and business teams for advanced querying and dashboards.

📊 6. Reporting
Tool:

Power BI

Purpose:

Real-time dashboards and visualizations

Connected to Synapse or Delta Lake directly for dynamic analytics

🔐 7. Security & DevOps
GitHub is used for source code and CI/CD pipelines

Azure Key Vault for secrets and credential management

Role-based access control (RBAC) enforced via Unity Catalog or Azure RBAC

✅ Summary Flow:
📁 Raw Data → 🏗️ ADF/Autoloader → 🪣 Raw Zone (Bronze) →
🧪 Delta Live Tables → 🧹 Cleaned Data (Silver) →
📊 Star Schema (Gold) → 🔎 Azure Synapse → 📈 Power BI

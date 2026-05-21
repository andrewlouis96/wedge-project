# wedge-project:

Local Business Transaction Data Engineering & Reporting Pipeline;

Designed and implemented an end-to-end data engineering and analytics pipeline using real transactional data from a local business. The project focused on converting raw point-of-sale transaction files into a clean, structured, cloud-hosted dataset that could support downstream reporting, analysis, and business intelligence use cases.

The workflow began with ingesting multiple raw CSV transaction files using Python and pandas. I cleaned and standardized the data by enforcing appropriate data types across transaction, customer, product, pricing, discount, tax, employee, register, and store-related fields. This included converting numeric columns, handling missing values, parsing transaction timestamps, formatting string fields, and standardizing Boolean indicators used in the raw transaction records.

After preprocessing the files, I built an ETL process to append the cleaned transaction data into Google BigQuery using service account authentication and pandas_gbq. This created a centralized cloud data warehouse table for large-scale querying and analysis.
I then used SQL in BigQuery to build analytical datasets from the cleaned transaction archive. This included creating customer-level samples, joining sampled customer IDs back to their full transaction history, filtering invalid or non-analytical department records, adjusting item counts for voided and returned transactions, and aggregating sales, transaction counts, and item quantities across multiple business dimensions.

The final reporting layer included summary tables for sales by year and hour, sales by customer/card owner by year and month, and sales by product, department, year, and month. These outputs were exported into a local SQLite reporting database, creating a lightweight reporting layer that could support business intelligence dashboards, ad hoc analysis, and operational reporting.
This project demonstrated practical experience with data ingestion, ETL development, data cleaning, schema standardization, SQL-based transformation, cloud data warehousing, transactional data modeling, BigQuery, SQLite, and analytical reporting design.

Python scripts for all three tasks are in the ipynb files. Results and comments are in the .md file.

packages needed:

!pip install google-cloud-bigquery pandas
!pip install pandas_gbq

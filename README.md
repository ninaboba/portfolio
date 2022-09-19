# Data Engineer End to End project
**Table of Content**
- [Project overview](##project-overview)
- [Data collection with Python](##data-collection-with-python)
- [Data wrangling with Spark](##data-wrangling-with-spark)
- [Data storage with Google Cloud Storage (GCS)](##data-storage-with-google-cloud-storage-(gcs))
- [Automated data pipeline with Airflow](##automated-data-pipeline-with-airflow)
- [Building Data Warehouse with BigQuery](##building-data-warehouse-with-bigquery)

## Project overview
![overview](images/overview.png)

This project builds an automated end-to-end data pipeline that aims to learn about data engineer process from data collection, data cleaning, data storaging, automated pipeline with airflow and build data warehouse.

Firstly, we extract the books data from MySQL database and currency exchange rate from API. Also clean the data with Pyspark. Then we load them into Google Data Storage (Data Lake) and schedule a data pipeline (Airflow) to automate daily to load the data into Google BigQuery (Data Warehouse).

## Data collection with Python
We use python to collect data from database and API. Then we merge it into csv file.
1. Connect to database with pymysql, query table and convert to Pandas for better visual.
[datacollection_1]
[datacollection_2]
2. Query another table with Pandas
[datacollection_3]
3. Join 2 table (audible_transaction & audible_data)
[datacollection_4]
4. Read data from REST API [link](https://r2de2-workshop-vmftiryt6q-ts.a.run.app/usd_thb_conversion_rate) ,convert to Pandas and indexing the table.
[datacollection_5]
5. Join the conversion rate table and previous table with Pandas to make THB price column.
[datacollection_6]
6. Save the result to csv file.

## Data wrangling with Spark



## Data storage with Google Cloud Storage (GCS)

## Automated data pipeline with Airflow

## Building Data Warehouse with BigQuery

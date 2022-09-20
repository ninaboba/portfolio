# Data Engineer End to End project
**Table of Content**
- [Project overview](#project-overview)
- [Data collection with Python](#data-collection-with-python)
- [Data wrangling with Spark](#data-wrangling-with-spark)
- [Data storage with Google Cloud Storage (GCS)](#data-storage-with-google-cloud-storage-gcs)
- [Automated data pipeline with Airflow](#automated-data-pipeline-with-airflow)
- [Building Data Warehouse with BigQuery](#building-data-warehouse-with-bigquery)

## Project overview
![overview](images/overview.png)

This project builds an automated end-to-end data pipeline that aims to learn about data engineer process from data collection, data cleaning, data storaging, automated pipeline with airflow and build data warehouse.

Firstly, we extract the books data from MySQL database and currency exchange rate from API. Also clean the data with Pyspark. Then we load them into Google Data Storage (Data Lake) and schedule a data pipeline (Airflow) to automate daily to load the data into Google BigQuery (Data Warehouse).

## Data collection with Python
We use python to collect data from database and API. Then we merge it into csv file.
1. Connect to database with pymysql, query table and convert to Pandas for better visual.

![datacollection_1](images/datacollection_1.png)
![datacollection_2](images/datacollection_2.png)

2. Query another table with Pandas

![datacollection_3](images/datacollection_3.png)

3. Join 2 table (audible_transaction & audible_data)

![datacollection_4](images/datacollection_4.png)

4. Read data from REST API [link](https://r2de2-workshop-vmftiryt6q-ts.a.run.app/usd_thb_conversion_rate) ,convert to Pandas and indexing the table.

![datacollection_5](images/datacollection_5.png)

5. Join the conversion rate table and previous table with Pandas to make THB price column.

![datacollection_6](images/datacollection_6.png)

6. Save the result to csv file.

## Data wrangling with Spark
1. Install Spark and PySpark

2. Data profiling and find if there are missing values with Spark 

![spark_1](images/spark_1.png)
![spark_2](images/spark_2.png)
![spark_3](images/spark_3.png)

3. Exploratory Data Analysis (EDA)
- Non-Graphical EDA: We can use where clause to show what you want to looking for. Spark will show only tops 20 row from show() function.

![spark_4](images/spark_4.png)

- Graphical EDA: We will use seaborn or matplotlib wiith pandas instead, because spark cannot do the plotting job.

<img width="162" alt="image" src="https://user-images.githubusercontent.com/106046788/191273386-3b96a201-a1dc-453b-8d90-531f03389f97.png">

Boxplot to show number distribution and outliers

![spark_5](images/spark_5.png)

4. Data cleansing with Spark
- Data type convert from string to date time

![spark_6](images/spark_6.png)

- Show timestamp column to see if it's (DD/MM/YYYY or MM/DD/YYYY)

![spark_7](images/spark_7.png)

- Using pyspark.sql.function (to_timestamp) to convert

![spark_8](images/spark_8.png)

5. Data cleansing with Spark SQL
- Convert spark dataframe to TempView

![spark_9](images/spark_9.png)

- Check if user_id column is not 8 character long and then correct them

![spark_10](images/spark_10.png)

![spark_11](images/spark_11.png)

6. Save data to CSV file

![spark_12](images/spark_12.png)

## Data storage with Google Cloud Storage (GCS)

## Automated data pipeline with Airflow

## Building Data Warehouse with BigQuery

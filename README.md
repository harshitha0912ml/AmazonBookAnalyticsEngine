# AmazonBookAnalyticsEngine By Harshitha Reddy T

## Overview
This project involves scraping book data from Amazon using Python and BeautifulSoup, then loading it into a bronze storage layer via DataFactory. The data is transformed in Databricks and stored in a silver layer. Snowflake is used to build the serving layer with fact and dimension tables. Finally, Power BI is connected for data visualization and insights.

## Project Goals
1. **Data Ingestion** – Scrape book data from **Amazon** using Python and **BeautifulSoup**, and ingest it into the **Bronze layer** using **Azure Data Factory**.
2. **ETL System** – Use **Azure Databricks** to clean, transform, and enrich the raw scraped data for structured analysis.
3. **Medallion Architecture** – Implement a **Bronze-Silver-Gold** data model, storing cleaned and structured data in **Azure Data Lake**, and building **fact and dimension tables** in **Snowflake** for the serving (Gold) layer.
4. **Reporting** – Connect the Gold layer to **Power BI** and build insightful dashboards visualizing book ratings, popularity, genres, pricing, and review patterns.

## Services Used
1. **Python & BeautifulSoups** – Used for web scraping book data directly from Amazon, extracting details like title, author, rating, price, and more.
2. **Azure Data Factory** – Orchestrates data pipelines to ingest the scraped data into the Bronze layer of the medallion architecture for further processing.
3. **Azure Databricks** – Performs data cleaning, transformation, and enrichment using Apache Spark, moving refined data into the Silver layer.
4. **Snowflake** – Serves as the serving (Gold) layer, where fact and dimension tables are created to support structured querying and analytics.
5. **Microsoft Power BI** – Connects to Snowflake to create interactive dashboards visualizing key book metrics like ratings, genres, pricing trends, and popularity.

## Dataset Used

1. The Dataset has been extracted using Python via the Amazon website.
2. Data such as Author, Title, Rating, Reviews Count, Image URL, price have been extracted to form a meaningful dataset.
3. Features such as price_category, rate_category, and popularity_score have been derived to add more insights to the dataset.

## Architechture Diagram
![amazon](https://github.com/user-attachments/assets/16d11635-702b-4ca6-a855-23a473a1dd32)
*Figure 1: Architechture Diagram of the System*

## Process Flow
1. **Web Scraping from Amazon → Python & BeautifulSoup** : Book data including title, author, genre, rating, reviews, and price is scraped directly from Amazon using a custom Python script powered by BeautifulSoup. The data is structured into a tabular format for further processing.
2. **Data Ingestion into Bronze Layer using Azure Data Factory** : The scraped raw data is ingested into the Bronze layer of Azure Data Lake Storage Gen2 using pipelines configured in Azure Data Factory. This layer stores the raw, unaltered data for traceability and auditing.
3. **Data Transformation with Azure Databricks (Bronze → Silver)** : In Azure Databricks, Spark-based ETL processes clean, standardize, and format the data: Null handling, data type casting, and deduplication. Output is converted to Parquet format and saved to the Silver layer for optimized querying.
4. **Dimensional Modeling and Serving via Snowflake (Silver → Gold)**: The cleaned data is loaded into Snowflake, where fact and dimension tables are created to support analytical queries. This forms the Gold layer, enabling efficient data modeling and business-ready datasets.
<img width="1536" height="1024" alt="ChatGPT Image Jul 13, 2025, 05_04_46 PM" src="https://github.com/user-attachments/assets/b60fafad-423b-4633-ae60-225005ea5ff7" />
*Figure 2: Star Schema Dimensional Modelling*

5: **Data Visualization using Power BI**: Power BI connects to Snowflake to build interactive dashboards, visualizing key book metrics such as ratings, pricing trends, genre distribution, and review volume for actionable insights.
<img width="1290" height="746" alt="image" src="https://github.com/user-attachments/assets/cea3634b-35b8-42df-93dc-b8c351da9011" />
*Figure 3: Power BI Dashboard*




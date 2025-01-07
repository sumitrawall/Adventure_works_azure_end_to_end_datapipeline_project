# Azure-End-to-End-Data-Engineering-Project

## Introduction
This project performs the end-to-end Data Engineering implementation for the <strong>AdventureWorks</strong> data using Microsoft Azure services. This project helps to understand the data ingestion from github, storing the data, transforming, performing analysis and visualization of the AdventureWorks data.

## Project Overview
This project uses the AdventureWorks dataset, fetched directly from Github. With this data we process, transform and deliver data for Business Intelligence (BI) purpose, using the resources like Azure Data Factory, Azure Databricks, Azure Synapse Analytics, and Power BI.

## Architecture Diagram
![image_alt](https://github.com/sumitrawall/Adventure_works_azure_end_to_end_datapipeline_project/blob/main/images/Architecture.png?raw=true)
The data flows through the following steps:
1. <strong>Data Source</strong>: The source of the data is AdventureWorks data which is stored in Github.
2. <strong>Data Ingestion</strong>: Data from the Github is ingested to Azure Data Factory. In the Data Factory the data is prepared for processing.
3. <strong>Raw Data Storage</strong>: The ingested raw data is stored in Azure Data Lake Gen2, providing scalable and secure storage.
4. <strong>Transformation</strong>:Azure Databricks is used for data transformation, performing various operations to process and refine the raw data.
5. <strong>Serving</strong>: Azure Synapse Analytics is used for generating insights from the transformed data.
6. <strong>Reporting</strong>: Data visualizations are created with Power BI, providing interactive and insightful reports for business decision-making.

## Azure Servies Used
* Microsoft Azure
* Resource Groups
* Azure Data Factory
* Azure Data Lake Gen2
* Azure Databricks
* Microsoft Entra ID
* Azure Syanpse Analytcis
* Power BI

## Data Source



The project data is used from AdventureWorks data stored in Github.
The [Dataset](https://github.com/sumitrawall/Adventure_works_azure_end_to_end_datapipeline_project/tree/main/Data)
 involves multiple files with information about
* Calendar
* Customers
* Product Categories
* Product Subcategories
* Products
* Returns
* Sales 2015
* Sales 2016
* Sales 2017
* Territories

## Resource Groups
Resource Groups in Azure are logical containers that help organize and manage project-related Azure resources. They simplify lifecycle management by enabling easy deletion of associated resources and provide a way to track costs and usage across services. The first step in the project is to set up the Resource Groups. The following image illustrates the implementation of the resource groups.

![Resource Groups](https://github.com/sumitrawall/Adventure_works_azure_end_to_end_datapipeline_project/blob/main/images/resources.png?raw=true)

## Data Ingestion
We used Azure Data Factory for data orchestration and automation. Data is pulled from GitHub using an HTTP connector and stored in the bronze container in Azure Storage. Parameters are incorporated into the pipeline to ensure adaptability to changes in the data source.

![Data Ingestion](https://github.com/sumitrawall/Adventure_works_azure_end_to_end_datapipeline_project/blob/main/images/dataIngestion.png?raw=true)

## Storage Accounts
We used Azure Data Lake Gen2 to store the raw data. In Azure Data Engineering, the Bronze, Silver, and Gold layers represent a data architecture pattern used in Data Lakes and Lakehouses for organizing and processing data. 

The Bronze layer serves as the raw data storage layer, where data from various sources is ingested in its original format, regardless of structure. The data is immutable and used for reprocessing.

![BronzeLayer](https://github.com/sumitrawall/Adventure_works_azure_end_to_end_datapipeline_project/blob/main/images/bronze%20container.png?raw=true)

The Silver layer contains cleaned and transformed data from the Bronze layer. Data transformation is performed using Azure Databricks, where processes like data standardization and basic transformations are applied, making it suitable for intermediate analytics and operational reporting.

![SilverLayer](https://github.com/sumitrawall/Adventure_works_azure_end_to_end_datapipeline_project/blob/main/images/Silver_container.png?raw=true)

The Gold layer contains curated, fully processed data that is ready for advanced analytics. The data in this layer is aggregated, summarized, and enriched to support decision-making processes.

![GoldLayer](https://github.com/sumitrawall/Adventure_works_azure_end_to_end_datapipeline_project/blob/main/images/gold_layer.png?raw=true)

This layered approach ensures data quality, scalability, and efficient data management, enabling robust analytics using Azure services like Azure Data Lake Storage, Azure Synapse Analytics, Azure Data Factory, and Azure Databricks.

## Data Transformation
Azure Databricks was utilized to transform raw data from the Bronze container into a structured format, storing it in the Silver layer for advanced analytics. A dedicated Databricks cluster was set up to optimize processing efficiency.
![Cluster](https://github.com/sumitrawall/Adventure_works_azure_end_to_end_datapipeline_project/blob/main/images/databricks_cluster.png?raw=true)

The transformation process involved data cleaning, filtering, normalization for consistency, and dataset concatenation to enhance usability. The attached notebook [ipynb](https://github.com/sumitrawall/Adventure_works_azure_end_to_end_datapipeline_project/blob/main/silver_layer.ipynb) file details the steps, including data ingestion from the Bronze layer, transformation using PySpark, and the creation of the Silver layer for reporting and further analysis.


## Insights and Analytics
The final step involved integrating the transformed data into Power BI for visualization and insights generation. The reports created in Power BI provide actionable insights for stakeholders. For example, the visualizations highlight the number of orders placed across different years and the growth in customer engagement over time. These insights help stakeholders understand trends and make informed decisions.

![Insights1](https://github.com/sumitrawall/Adventure_works_azure_end_to_end_datapipeline_project/blob/main/images/Power%20BI.png?raw=true)

## Summary of Project
The project focused on building a scalable data pipeline for processing and analyzing large datasets using Azure tools. Azure Data Factory orchestrated data ingestion into Azure Data Lake Storage (Bronze layer) for centralized storage. Azure Databricks handled ETL processes to clean, aggregate, and enrich data using Apache Spark with best practices like caching and partitioning. The processed data was loaded into Azure Synapse Analytics, leveraging dedicated SQL pools for analytical querying and reporting. Finally, Power BI dashboards provided real-time business insights.

Key highlights included optimizing pipeline performance with parameterized pipelines, ensuring data quality through validation checks, and implementing robust security measures. This solution empowered data-driven decision-making by delivering accurate, timely, and actionable insights.


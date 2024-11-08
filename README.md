# End-to-End Azure Data Engineering Project: Tokyo Olympics 2020


![data architecture](https://github.com/user-attachments/assets/73b0caed-daae-4101-9822-6f93808506b5)




# Table of contents 

- [Introduction](#introduction)
   - [Building an End-to-End Azure Data Engineering Project](#building-an-end-to-End-azure-data-engineering-project)
- [Objective](#objective)
   - [What is the primary challenge?](what-is-the-primary-challenge)
   - [What is the ideal solution?](what-is-the-ideal-solution?)
   - [User story](user-story)
- [Data Source](#data-source)
   - [What data is needed to achieve our objective?](what-data-is-needed-to-achieve-our-objective?)
- [Stages](#stages)
- [Design](#design)
  - [Dashboard components required](dashboard-components-required)
  - [Dashboard mockup](#dashboard-mockup)
  - [Tools](#tools)
- [Development](#development)
  - [Pseudocode](#pseudocode)
  - [Data Exploration](#data-exploration)
  - [Create a storage account](#create-a-storage-account)
  - [Create data factory](#create-data-factory)
  - [Data Transformation](#data-transformation )
- [Analysis](#analysis)
- [Visualization](#visualization)

# Introduction

### Building an End-to-End Azure Data Engineering Project

This project aims to demonstrate a comprehensive data engineering workflow using various Azure services. Below is a detailed step-by-step guide:

1. **Extract Data from Kaggle**
    - Use Azure Data Factory to connect to Kaggle and extract raw data.
2. **Upload Raw Data to Azure Data Lake Gen2**
    - Create pipelines in Azure Data Factory to upload the extracted raw data into your Azure Data Lake Gen2 Storage account.
3. **Transform Data Using Azure Databricks**
    - Utilize Azure Databricks to process and transform the raw data using Spark code.
4. **Store Transformed Data in Azure Data Lake Gen2**
    - Save the transformed data back into your Azure Data Lake Gen2 Storage account.
5. **Analyze Data with Azure Synapse Analytics**
    - Run SQL queries on the transformed data using Azure Synapse Analytics to derive meaningful insights.
6. **Visualize Data in Power BI**
    - Load the processed data into Power BI.
    - Create a dashboard in Power BI to visualize key data points and insights.

Each step leverages the capabilities of Azure's data services to ensure a seamless and efficient data engineering process. This project will provide a comprehensive understanding of the end-to-end workflow, from data extraction and transformation to analysis and visualization.

# Objective 

### What is the primary challenge? 

The Head of Marketing wants to analyze the performance of different countries in the 2020 Olympics to decide on which countries would be best to target for marketing campaigns in future sports events.


### What is the ideal solution? 

To create a dashboard that provides insights into the performance of various countries in the 2020 Olympics. The dashboard should include:
- Total medals won by each country
- Total Gold, Silver and bronze medals won by top 10 countries
- All sports based on number of athletes 
- Percentage of men and women in top 3 sports 

This will help the marketing team make informed decisions about which countries to focus on for future marketing campaigns related to sports events.


### User story 

As the Head of Marketing, I want to use a dashboard that analyzes the performance data of countries in the 2020 Olympics.

This dashboard should allow me to identify the top-performing countries based on metrics like total medal count and most popular sports events.

With this information, I can make more informed decisions about which countries are right to target for future marketing campaigns, and therefore maximize the effectiveness of each marketing campaign.


# Data source 

### What data is needed to achieve our objective?

We need data on the performance of countries in the 2020 Olympics that includes:

- Country names
- Total medal count
- Number of gold medals
- Number of silver medals
- Number of bronze medals
- Overall ranking
- Sports events by gender
- most popular sports 

  
Where is the data coming from? The data is sourced from Kaggle (an Excel extract). [see here to find it.](https://www.kaggle.com/datasets/arjunprasadsarkhel/2021-olympics-in-tokyo)



# Stages

- Design
- Developement
- Analysis
- Visualization
 


# Design 

### Dashboard components required 

What should the dashboard contain based on the requirements provided?

To understand what it should contain, we need to figure out what questions we need the dashboard to answer:

- Total medals won by each country?
- Total Gold, Silver and bronze medals won by top 10 countries?
- All sports based on number of athletes?
- Percentage of men and women in top 3 sports?

For now, these are some of the questions we need to answer; this may change as we progress through our analysis. 


### Dashboard mockup

What should it look like?

Some of the data visuals that may be appropriate in answering our questions include:
- Bar chart
- pie chart
- martix table
- tree map

![Dashboard-Mockup](assets/images/Mock-up-dashboard-tokyo-olympics.png)


### Tools 

| Tool | Purpose |
| --- | --- |
| Excel | Initial exploring of the data |
| Azure Data factory | Extracting data and ingesting into storage account |
| Azure Data Lake | To store raw and transformed data |
| Azure Databricks | To process and transform the raw data using Spark code |
| Azure Synapse Analytics | Run SQL queries on the transformed data using Azure Synapse Analytics to derive meaningful insights |
| Power BI | Visualizing the data via interactive dashboards |
| GitHub | Hosting the project documentation and version control |
| Mokkup AI | Designing the wireframe/mockup of the dashboard | 



# Development

### Pseudocode

What's the general approach in creating this solution from start to finish?

1. Get the data from kaggle
2. Explore the data in Excel
3. Ingest the data into ADLS gen2 using Data factory
4. Transform the data using Databricks 
5. Return the transformed data back to ADLS gen2
6. Use Azure Synapse Analytics to derive meaningful insights
7. Generate the findings based on the insights
8. Visualize the data in Power BI
9. Publish the data to GitHub Pages


### Data exploration

This is the stage where you have a scan of what's in the data, errors, inconcsistencies, bugs, weird and corrupted characters etc  


What are your initial observations with this dataset? What's caught your attention so far? 

1. There are at least 3 Tables that contain the data we need for this analysis, which signals we have everything we need from the file without needing to contact the client for any more data. 
2. There are some columns that have errors and need to be renamed correctly.
3. We have more data than we need, so some of these tables would not be needed.



### Create a storage account
- create storage account
![Create storage account](assets/images/create-storage-account.png)
- create a container and put two folders in there one for the raw data and the other for the transformed data.
![create container](assets/images/create-a-container.png)



### Create data factory
- create data factory to ingest data into storage account
![create data factory](assets/images/create-data-factory.png)
- create a self hosted integration runtime in order to connect to your on-premise data
![Integration runtime](assets/images/create-a-self-hosted-integration-runtime.png)
- create a linked service which is linked to your laptop
![Linked service](assets/images/create-a-linked-service.png)
- create your pipeline to ingest data into your storage account from your laptop
![Create pipeline](assets/images/create-your-pipeline.png)
- Check files have been uploaded to storage account in the raw data folder inside your container
![raw data](assets/images/ingest-data-into-your-storage-account.png)



### Data Transformation 

- create databricks
![databricks](assets/images/create-databricks.png)
- create a compute cluster (because our spark code needs to run somewhere)
![compute cluster](assets/images/create-a-cluster.png)
![compute cluster](assets/images/create-a-compute.png)
- configure the notebook to connect your Databricks to your storage account
![connect your Databricks to your storage account](assets/images/connect-your-Databricks-to-your-storage-account.png)
- read your data on notebooks
![read your data on notebooks](assets/images/read-your-data-on-notebooks.png)


### Transforming the data 
What do we expect the transformed data to look like, what should it contain and what constraints should we apply to it?

The aim is to refine our dataset to ensure it is structured and ready for analysis. 

The transformed data should meet the following criteria and constraints:


1. Rename column names correctly using this code **athletes = athletes.withColumnRenamed("NOC", "Country")**

DataFrame with Renamed Columns:

| Name | Country | Discipline |
|---|---|---|
| AALERUD Katrine         | Norway                        | Cycling Road          |
| ABAD Nestor             | Spain                         | Artistic Gymnastics   |
| ABAGNALE Giovanni       | Italy                         | Rowing                |
| ABALDE Alberto          | Spain                         | Basketball            |
| ABALDE Tamara           | Spain                         | Basketball            |
| ABALO Luc               | France                        | Handball              |
| ABAROA Cesar            | Chile                         | Rowing                |
| ABASS Abobakr           | Sudan                         | Swimming              |
| ABBASALI Hamideh        | Islamic Republic of Iran      | Karate                |
| ABBASOV Islam           | Azerbaijan                    | Wrestling             |
| ABBINGH Lois            | Netherlands                   | Handball              |
| ABBOT Emily             | Australia                     | Rhythmic Gymnastics   |
| ABBOTT Monic            | United States of America      | Baseball/Softball     |
| ABDALLA Abubaker Haydar | Qatar                         | Athletics             |
| ABDALLA Maryam          | Egypt                         | Artistic Swimming     |
| ABDALLAH Shahd          | Egypt                         | Artistic Swimming     |
| ABDALRASOOL Mohamed     | Sudan                         | Judo                  |
| ABDEL LATIF Radwa       | Egypt                         | Shooting              |
| ABDEL RAZEK Samy        | Egypt                         | Shooting              |
| ABDELAZIZ Abdalla       | Egypt                         | Karate                |



2. fix all the schemas using this code **.option("inferSchema","true")**

![Fix the schemas](assets/images/fix-schemas.png)



- Move your transformed data into the **transformed data folder** in your ADLS storage account
  
![move your transformed data](assets/images/move-your-transformed-data-into-the-transformed-data-folder-in-your-ADLS.png)


# Analysis
- create synapse analytics workspace

![create synapse analytics workspace](assets/images/create-synapse-analytics-workspace.png)

- create a database on synapse

![create a database on synapse](assets/images/create-a-database.png)


- create an external table

![create an external table](assets/images/create-an-external-table-1.png)

![create an external table](assets/images/create-an-external-table-2.png)

- use SQL to query the data

![SQL to query the data](assets/images/use-SQL-to-query-the-data-1.png)

![SQL to query the data](assets/images/use-SQL-to-query-the-data-2.png)

# Visualization
- download the data and upload it to PowerBI

![download the data and upload to powerBI](assets/images/download-the-data-and-upload-to-powerBI.png)

- create a dashboard

![Tokyo Olympics dashboard](assets/images/Tokyo-Olympics-dashboard.PNG)




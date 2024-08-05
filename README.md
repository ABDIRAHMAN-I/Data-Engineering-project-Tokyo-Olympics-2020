# Data Engineering project: Tokyo Olympics 2020


![data architecture](https://github.com/user-attachments/assets/73b0caed-daae-4101-9822-6f93808506b5)




# Table of contents 

- [Introduction](#Introduction)
- [Objective](#objective)
- [Data Source](#data-source)
- [Stages](#stages)
- [Design](#design)
  - [Mockup](#mockup)
  - [Tools](#tools)
- [Development](#development)
  - [Pseudocode](#pseudocode)
  - [Data Exploration](#data-exploration)
  - [Data Cleaning](#data-cleaning)
  - [Transform the Data](#transform-the-data)
  - [Create the SQL View](#create-the-sql-view)
- [Testing](#testing)
  - [Data Quality Tests](#data-quality-tests)
- [Visualization](#visualization)
  - [Results](#results)
  - [DAX Measures](#dax-measures)
- [Analysis](#analysis)
  - [Findings](#findings)
  - [Validation](#validation)
  - [Discovery](#discovery)
- [Recommendations](#recommendations)
  - [Potential ROI](#potential-roi)
  - [Potential Courses of Actions](#potential-courses-of-actions)
- [Conclusion](#conclusion)

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

- What is the primary challenge? 

The Head of Marketing wants to analyze the performance of different countries in the 2020 Olympics to decide on which countries would be best to target for marketing campaigns in future sports events.


- What is the ideal solution? 

To create a dashboard that provides insights into the performance of various countries in the 2020 Olympics. The dashboard should include:
- Total medals won by each country
- Total Gold, Silver and bronze medals won by top 10 countries
- All sports based on number of athletes 
- Percentage of men and women in top 3 sports 

This will help the marketing team make informed decisions about which countries to focus on for future marketing campaigns related to sports events.


## User story 

As the Head of Marketing, I want to use a dashboard that analyzes the performance data of countries in the 2020 Olympics.

This dashboard should allow me to identify the top-performing countries based on metrics like total medal count and most popular sports events.

With this information, I can make more informed decisions about which countries are right to target for future marketing campaigns, and therefore maximize the effectiveness of each marketing campaign.


# Data source 

- What data is needed to achieve our objective?

We need data on the performance of countries in the 2020 Olympics that includes:

- Country names
- Total medal count
- Number of gold medals
- Number of silver medals
- Number of bronze medals
- Overall ranking
- Sports events by gender
- most popular sports 

  
- Where is the data coming from? The data is sourced from Kaggle (an Excel extract). [see here to find it.](https://www.kaggle.com/datasets/arjunprasadsarkhel/2021-olympics-in-tokyo)



# Stages

- Design
- Developement
- Testing
- Analysis 
 


# Design 

## Dashboard components required 

What should the dashboard contain based on the requirements provided?

To understand what it should contain, we need to figure out what questions we need the dashboard to answer:

- Total medals won by each country?
- Total Gold, Silver and bronze medals won by top 10 countries?
- All sports based on number of athletes?
- Percentage of men and women in top 3 sports?

For now, these are some of the questions we need to answer; this may change as we progress through our analysis. 


## Dashboard mockup

What should it look like?

Some of the data visuals that may be appropriate in answering our questions include:
- Bar chart
- pie chart
- martix table
- tree map

![Dashboard-Mockup](https://github.com/ABDIRAHMAN-I/Olympic-2021-data/blob/main/assets/images/Mock%20up%20dashboard%20tokyo%20olympics.png)


## Tools 

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













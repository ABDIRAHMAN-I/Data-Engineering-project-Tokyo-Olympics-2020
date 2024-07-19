# Data Engineering project: Olympics2021-data


![data architecture](https://github.com/user-attachments/assets/73b0caed-daae-4101-9822-6f93808506b5)




# Table of contents 

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




# Objective 

- What is the key pain point? 

The Head of Marketing wants to analyze the performance of different countries in the 2021 Olympics to decide on which countries' teams would be best to target for marketing campaigns in future sports events.


- What is the ideal solution? 

To create a dashboard that provides insights into the performance of various countries in the 2021 Olympics. The dashboard should include:
- Total medal count
- Gold medals
- Silver medals
- Bronze medals
- Overall ranking
- Event-specific performance

This will help the marketing team make informed decisions about which countries to focus on for future marketing campaigns related to sports events.

## User story 

As the Head of Marketing, I want to use a dashboard that analyzes the performance data of countries in the 2021 Olympics.

This dashboard should allow me to identify the top-performing countries based on metrics like total medal count and event-specific success.

With this information, I can make more informed decisions about which countries' teams are right to target for future marketing campaigns, and therefore maximize the effectiveness of each marketing campaign.


# Data source 

- What data is needed to achieve our objective?

We need data on the performance of countries in the 2021 Olympics that includes:

- Country names
- Total medal count
- Number of gold medals
- Number of silver medals
- Number of bronze medals
- Overall ranking
- Event-specific performance data

  
- Where is the data coming from?

The data is sourced from Kaggle (an Excel extract). [see here to find it.](https://www.kaggle.com/datasets/arjunprasadsarkhel/2021-olympics-in-tokyo)



# Stages

- Design
- Developement
- Testing
- Analysis 
 


# Design 

## Dashboard components required 
- What should the dashboard contain based on the requirements provided?

To understand what it should contain, we need to figure out what questions we need the dashboard to answer:

1. Which countries are the top 10 in terms of total medal count?
2. Which 3 countries have the most gold medals?
3. Which 3 countries have the most silver medals?
4. Which 3 countries have the most bronze medals?
5. Which countries have the highest medals per capita ratio?
6. Which countries have the highest gold medal efficiency (gold medals per event participated)?
7. Which countries have the highest overall ranking in specific sports/events?

For now, these are some of the questions we need to answer; this may change as we progress through our analysis. 


## Dashboard mockup

-Proposed Dashboard Components

* Top 10 Countries by Total Medal Count: Bar chart showing the top 10 countries with the highest total medals.

* Top 3 Countries by Gold Medals: Pie chart or bar chart showing the top 3 countries with the highest number of gold medals.

* Top 3 Countries by Silver Medals: Pie chart or bar chart showing the top 3 countries with the highest number of silver medals.

* Top 3 Countries by Bronze Medals: Pie chart or bar chart showing the top 3 countries with the highest number of bronze medals.

* Medals Per Capita: Table or bar chart showing the top countries with the highest medals per capita ratio.

* Gold Medal Efficiency: Table or bar chart showing the top countries with the highest gold medals per event participated.

* Event-Specific Performance: Interactive filter or dropdown to select specific sports/events and see the ranking of countries in those events.

* Overall Medal Distribution: Heatmap or geographic map showing the distribution of medals across different countries.

- User Interaction Features
  
* Interactive Filters: Filters to view data by specific regions, sports/events, or medal types (gold, silver, bronze).

* Search Functionality: Ability to search for specific countries to see their detailed performance.

* Time Series Analysis: Line chart showing the trend of medal counts over the duration of the 2021 Olympics.
  
* Comparison Tool: Feature to compare the performance of selected countries across different metrics.
  
By including these components, the dashboard will provide comprehensive insights into the performance of countries in the 2021 Olympics, helping the marketing team make informed decisions for future campaigns.












# Project Overview
This project focuses on building an end-to-end data analytics pipeline using PySpark to analyze global COVID-19 trends using multiple real-world datasets. The datasets contain information such as daily confirmed cases, deaths, recoveries, active cases, country-wise statistics, WHO region data, population details, and county-level geographic information.
Interns will work with multiple CSV datasets and perform data engineering tasks such as:
Data ingestion from multiple sources
Schema inference and validation
Data cleaning and preprocessing
Handling missing values and duplicates
Standardizing country names across datasets
Aggregations and KPI generation
Time-series analysis on daily case growth
Window function-based trend analysis
Multi-dataset joins
Feature engineering
Exporting transformed datasets for visualization dashboards
The final objective is to build a scalable analytics workflow that converts raw COVID-19 data into meaningful insights that can later be visualized using tools like Matplotlib, Plotly, Power BI, or Tableau.
Business Problem Statement
During the COVID-19 pandemic, governments, healthcare organizations, and analysts needed quick access to reliable insights such as:
Which countries were most affected?
Which WHO regions had the highest recovery rates?
When did global cases peak?
Which countries had high active case burdens?
How did population size impact infection rates?
Since the data is spread across multiple datasets with different formats and granularity levels, organizations require a robust data pipeline to clean, transform, and analyze this information efficiently.
This project simulates how a real-world analytics team would process pandemic data for reporting and decision-making.

### Tech Stack
PySpark → Large-scale data processing
Python → Additional scripting
Spark SQL → Analytical queries
Parquet/CSV → Output storage
Matplotlib / Plotly / Tableau / Power BI → Visualization
Datasets Used
full_grouped.csv → Daily country-level COVID trends
covid_19_clean_complete.csv → Location-level historical data
country_wise_latest.csv → Latest country statistics
day_wise.csv → Global day-wise trends
usa_county_wise.csv → US county-level data
worldometer_data.csv → Population and global COVID stats
   Link:https://www.kaggle.com/datasets/imdevskp/corona-virus-report 


   
## Module 1: Data Loading & Schema Handling

#### Task 1: Load all CSV files into PySpark DataFrames
Load:
full_grouped.csv
covid_19_clean_complete.csv
country_wise_latest.csv
day_wise.csv
usa_county_wise.csv
worldometer_data.csv

Requirements:
Infer schema
Handle headers
Print schema of each dataset
Count rows

Concepts practiced:
spark.read.csv()
inferSchema
printSchema()
count()


## Module 2: Data Cleaning Tasks

#### Task 2: Handle Missing Province/State Values
In covid_19_clean_complete.csv:
Find rows where Province/State is null
Replace null values with "Unknown"
Output:
Country-wise null count report
Concepts:
isNull()
fillna()
filtering

#### Task 3: Standardize Country Names
Check if country names differ across:
full_grouped
country_wise_latest
worldometer_data
Example:
US vs USA
Korea vs South Korea
Create standardized naming.
Concepts:
when()
regexp_replace()
cleaning inconsistencies

#### Task 4: Remove Duplicate Daily Records
Check if duplicate entries exist for:
Country + Date
Remove duplicates.
Concepts:
dropDuplicates()


## Module 3: Aggregation Tasks

#### Task 5: Top 10 Countries by Total Confirmed Cases
Using country_wise_latest.csv
Output:
| Country | Confirmed |
Sort descending.
Visualization:
Bar chart
Concepts:
orderBy()
limit()

#### Task 6: Top 10 Countries by Death Rate
Using:
Deaths / 100 Cases
Find top countries with highest death rate.
Visualization:
Horizontal bar chart

#### Task 7: WHO Region-wise Total Cases
Using:
full_grouped.csv
Find:
total confirmed
total deaths
total recovered
grouped by WHO region.
Visualization:
Pie chart / stacked bar chart
Concepts:
groupBy()
agg()


## Module 4: Time-Series Analysis

#### Task 8: Daily Global New Cases Trend
Using day_wise.csv
Find:
date
new cases
Visualization:
Line chart

#### Task 9: Daily Global Death Growth Trend
Using day_wise.csv
Calculate:
daily death growth percentage
Formula:
(new_deaths / previous_day_deaths) * 100
Concepts:
window functions
lag
Visualization:
Line chart



#### Task 10: Monthly COVID Case Growth
Using full_grouped.csv
Extract:
month
total confirmed cases
Concepts:
month()
groupBy()
Visualization:
Monthly trend chart


## **Module 5** : Window Function Tasks

#### **Task 11** : Top 5 Most Affected Countries Per WHO Region
Using:
country_wise_latest.csv
For each WHO region:
rank countries based on confirmed cases
return top 5
Concepts:
Window.partitionBy()
dense_rank()
Visualization:
Grouped bar chart

#### **Task 12** : Country-wise Daily Case Increase
Using full_grouped.csv
For each country:
calculate:
today_confirmed - yesterday_confirmed
Concepts:
lag
partition window
Visualization:
Country trend chart


## **Module 6**: Join Operations

#### **Task 13**: Compare Latest Dataset Sources
Join:
country_wise_latest.csv
worldometer_data.csv
Join on:
Country/Region
Compare:
Confirmed cases difference
Death difference
Recovery difference
Output:
Find countries where both datasets show large mismatches.
Concepts:
joins
calculated columns

#### **Task 14**: Population vs Total Cases
Using worldometer_data.csv
Calculate:
infection_rate = (TotalCases / Population) * 100
Find top countries with highest infection rate.
Visualization:
Scatter plot / bar chart

## **Module 7** : Geographic Analysis
#### **Task 15** : USA State-wise Case Distribution
Using usa_county_wise.csv
Group by:
Province_State
Find number of counties reported per state.
Visualization:
US map / bar chart

#### **Task 16**: Latitude-Longitude Based Case Clusters
Using covid_19_clean_complete.csv
Create dataset containing:
latitude
longitude
confirmed cases
Visualization:
Geo scatter plot


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

Tech Stack
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


   
Module 1: Data Loading & Schema Handling

Task 1: Load all CSV files into PySpark DataFrames
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

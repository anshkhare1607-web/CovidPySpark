# Project Overview
This project focuses on building an end-to-end data analytics pipeline using PySpark to analyze global COVID-19 trends using multiple real-world datasets. The datasets contain information such as daily confirmed cases, deaths, recoveries, active cases, country-wise statistics, WHO region data, population details, and county-level geographic information.
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


# Global COVID-19 Analytics Pipeline
 
## Project Overview
 
This project is an end-to-end data engineering and analytics pipeline built using PySpark. The goal was to take raw, fragmented COVID-19 datasets from multiple sources and transform them into clean, actionable insights.
 
Instead of just running basic queries, this project scales up into a fully automated ETL (Extract, Transform, Load) pipeline that cleans the data, calculates advanced metrics, and exports the final reporting tables (in CSV and Parquet formats) so they can be easily plugged into visualization dashboards like Tableau or Power BI.
 
---
 
## What This Pipeline Does
 
Data Cleaning & Standardization: Ingests six different datasets, infers schemas, handles missing values, and fixes naming inconsistencies (like unifying "US" and "USA") so the data can be accurately joined.
 
Global Aggregations: Calculates the top most affected countries, mortality rates, and overall case breakdowns by WHO regions.
 
Time-Series Tracking: Uses PySpark Window functions to track daily case growth, monthly trends, and pinpoint the exact peak days of the pandemic.
 
Geographic Analysis: Maps out US state-wise case distributions and identifies global infection clusters using Latitude and Longitude coordinates.
 
Advanced Feature Engineering: Calculates recovery rates, identifies "high-risk" countries where active cases outnumber recoveries, and dynamically categorizes countries into severity tiers (Low to Critical) based on infection volume.
 
Automated ETL Execution: The final script wraps all these steps into a modular, repeatable pipeline that processes the raw data and spits out clean, finalized reporting tables.
 
---


   

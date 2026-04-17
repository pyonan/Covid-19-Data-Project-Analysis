# Experiments - 19 & 20
# COVID-19 Data Analysis Project

## Introduction
This repository contains a Python-based analysis of the COVID-19 pandemic. The project focuses on data cleaning, exploratory data analysis (EDA), and the visualization of global infection trends using a dataset spanning from January 2020 to May 2021.

## Dataset
The analysis is based on the covid_19_data.csv dataset, which includes:
- Date-wise observations of confirmed, death, and recovered cases.
- Geographic breakdown by Country/Region and Province/State.
- Cumulative totals for global and regional monitoring.

## Tech Stack
- Language: Python
- Environment: Google Colab / Jupyter Notebook
- Libraries: Pandas, Matplotlib, Seaborn, NumPy

## Analysis Workflow
1. Data Preprocessing: Cleaning null values in regional columns and formatting date-time objects.
2. Global Trend Analysis: Visualizing the cumulative growth of confirmed cases worldwide.
3. Regional Comparisons: Identifying the most impacted countries and comparing mortality vs. recovery rates.
4. Active Case Tracking: Derived metrics to monitor the progression of active infections.

## Data Limitations
- Reporting Standards: Variation in how different countries define and report "Recovered" cases can impact comparative accuracy.
- Time Horizon: The analysis is bounded by the dataset end-date of May 2021 and does not reflect subsequent pandemic waves or vaccination impacts.

## Conclusion
This research demonstrates the power of data visualization in understanding the scale and spread of a global health crisis. By aggregating daily observations, the project highlights the distinct waves of infection and the varying success rates of recovery efforts across different nations. The findings suggest that geographic and temporal factors played a critical role in the pandemic's trajectory, providing a clear historical record of the first 18 months of the COVID-19 outbreak.

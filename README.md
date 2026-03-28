# Airbnb Listings Analysis: Market Structure & Data Quality Validation

## Business Context: What is Airbnb?

[Airbnb, Inc.](https://www.airbnb.com) is an American company based in San Francisco that revolutionized the hospitality industry. It operates a peer-to-peer (P2P) online marketplace that connects people who want to rent out their homes (hosts) with people who are looking for accommodations in that locale (guests).

# Project Overview

This project analyzes an Airbnb listings dataset to understand market structure, listing activity, and availability patterns across New York City boroughs.

The analysis follows a structured end-to-end data analytics workflow, including data understanding, cleaning, exploratory data analysis (EDA), and insight generation.

A key component of this project is data quality validation, as certain variables—particularly price—show patterns that may not fully reflect realistic market behavior.

# Objectives

The analysis aims to answer the following questions:

How is Airbnb supply distributed across boroughs?
What is the distribution of room types?
How do review activity and listing availability vary across locations?
Can pricing insights be considered reliable given the dataset quality?

# Methodology

The project follows a structured analytical workflow:

*1) Business Understanding
Data Understanding
Data Cleaning
Exploratory Data Analysis (EDA)
Insights Generation
Preparation for Visualization
Dashboard Development

A data quality assessment step was incorporated to evaluate the reliability of key variables.
```python
import pandas as pd
df = pd.read_csv('datos_olist.csv')
print(df.head())
```


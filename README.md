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

1. Business Understanding
2. Data Understanding
3. Data Cleaning
4. Exploratory Data Analysis (EDA)
5. Insights Generation

**Important:** Initially, the project's roadmap included advanced stages such as Insights Generation, Preparation for Visualization, and Dashboard Development. However, following a rigorous peer review and the incorporation of a Data Quality Assessment step, the technical direction shifted.

During the Exploratory Data Analysis (Step 4) and initial Insights Generation (Step 5), a deep dive into the price distribution revealed that the dataset lacks the variance and complexity expected in a real-world real estate market. The data appears to be synthetic, showing an unnaturally uniform distribution. As a result, I decided to conclude the analysis at the diagnostic stage to maintain the integrity of the findings, as proceeding to visualization with non-representative data would lead to inaccurate economic conclusions.

A data quality assessment step was incorporated to evaluate the reliability of key variables.
```python
import pandas as pd
df = pd.read_csv('datos_olist.csv')
print(df.head())
```


# Airbnb Listings Analysis: Market Structure & Data Quality Validation

## Business Context: What is Airbnb?

Airbnb, Inc. is an American company based in San Francisco that revolutionized the hospitality industry. It operates a peer-to-peer (P2P) online marketplace that connects people who want to rent out their homes (hosts) with people who are looking for accommodations in that locale (guests).

# Project Overview

* This project analyzes an Airbnb listings dataset to understand market structure, listing activity, and availability patterns across New York City boroughs.

> The analysis follows a structured end-to-end data analytics workflow, including data understanding, cleaning, exploratory data analysis (EDA), and insight generation.

A key component of this project is data quality validation, as certain variables—particularly price—show patterns that may not fully reflect realistic market behavior.
```python
import pandas as pd
df = pd.read_csv('datos_olist.csv')
print(df.head())
```


# Airbnb Listings Analysis: Market Structure & Data Quality Validation

## Business Context: What is Airbnb?

[Airbnb, Inc.](https://www.airbnb.com) is an American company based in San Francisco that revolutionized the hospitality industry. It operates a peer-to-peer (P2P) online marketplace that connects people who want to rent out their homes (hosts) with people who are looking for accommodations in that locale (guests).

---

# Project Overview

This project analyzes an Airbnb listings dataset to understand market structure, listing activity, and availability patterns across New York City boroughs.

The analysis follows a structured end-to-end data analytics workflow, including data understanding, cleaning, exploratory data analysis (EDA), and insight generation.

A key component of this project is data quality validation, as certain variables (particularly price) show patterns that may not fully reflect realistic market behavior.

---

# Objectives

The analysis aims to answer the following questions:

* How is Airbnb supply distributed across boroughs?
* What is the distribution of room types?
* How do review activity and listing availability vary across locations?
* Can pricing insights be considered reliable given the dataset quality?

---

# Dataset

- **Source:** [Airbnb Open Data - NYC](https://www.kaggle.com/datasets/arianazmoudeh/airbnbopendata)
- **Unit of analysis:** individual Airbnb listings
- **Initial dataset size:** 102,599 rows and 26 columns

> Note: This dataset was treated as a public analytical source, but not all variables appeared equally reliable. A specific data quality validation section was included to assess dataset trustworthiness before drawing conclusions.

---

# Methodology

The project follows a structured analytical workflow:

1. Business Understanding
2. Data Understanding
3. Data Cleaning
4. Exploratory Data Analysis (EDA)
5. Insights Generation

**Important:** Initially, the project's roadmap included advanced stages such as Insights Generation, Preparation for Visualization, and Dashboard Development. However, following a rigorous peer review and the incorporation of a Data Quality Assessment step, the technical direction shifted.

During the Exploratory Data Analysis (Step 4) and initial Insights Generation (Step 5), a deep dive into the price distribution revealed that the dataset lacks the variance and complexity expected in a real-world real estate market. The data appears to be synthetic, showing an unnaturally uniform distribution. As a result, I decided to conclude the analysis at the diagnostic stage to maintain the integrity of the findings, as proceeding to visualization with non-representative data would lead to inaccurate economic conclusions.

---

## Data Understanding

The initial review focused on:
- dataset shape and structure
- column names and data types
- descriptive statistics
- missing values
- category consistency

This step helped identify several early data quality issues, including:
- missing values in important analytical fields
- inconsistent text labels
- non-numeric price formatting
- suspicious date values
- logically invalid values in availability and minimum nights

---

## Data Cleaning

The cleaning process included the following actions:

- standardized column names
- removed irrelevant or high-missing-value columns
- converted `price` and `service_fee` into numeric variables
- converted `last_review` into datetime format
- converted categorical fields to category type
- handled missing values using variable-specific logic
- removed duplicates
- filtered invalid negative values
- removed unrealistic values in `minimum_nights` and `availability_365`
- corrected inconsistent borough labels such as `brookln` and `manhatan`
- removed future dates in `last_review` while preserving true missing values for listings without reviews

The goal of cleaning was not only to improve technical consistency, but also to increase the credibility of the final analysis.

---

## Exploratory Data Analysis

The exploratory analysis focused on the most relevant variables for describing market structure:

- `neighbourhood_group`
- `room_type`
- `number_of_reviews`
- `availability_365`
- `price`

Visual exploration showed that listing distribution, room type composition, review activity, and availability contained interpretable patterns.

However, price-related visualizations revealed suspicious behavior: price distributions remained unusually similar across room types and boroughs, which does not reflect realistic market behavior in New York City.

<img width="862" height="473" alt="image" src="https://github.com/user-attachments/assets/1aa6b997-b2a5-4d9a-af45-bb02ebd82776" />

---

## Key Findings

### High-confidence insights

#### 1. Market supply is highly concentrated in Manhattan and Brooklyn
The dataset shows that the majority of listings are located in Manhattan and Brooklyn, indicating that these boroughs dominate Airbnb supply in NYC.

<img width="871" height="532" alt="image" src="https://github.com/user-attachments/assets/6916ed9f-aef4-40c1-984d-56e20eeb1f6a" />

#### 2. The market is dominated by entire homes/apartments and private rooms
Most listings belong to either Entire home/apartment or Private room, while Shared room and Hotel room represent much smaller segments.

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>room_type</th>
      <th>listings_count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Entire home/apt</td>
      <td>51481</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Private room</td>
      <td>44817</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Shared room</td>
      <td>2148</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Hotel room</td>
      <td>115</td>
    </tr>
  </tbody>
</table>
</div>

#### 3. Review activity varies across boroughs
Average review counts differ by borough, suggesting that listing engagement or usage patterns are not evenly distributed across the city.

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>neighbourhood_group</th>
      <th>avg_number_of_reviews</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Staten Island</td>
      <td>35.285097</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Queens</td>
      <td>33.428428</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Bronx</td>
      <td>31.179313</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Brooklyn</td>
      <td>28.241487</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Manhattan</td>
      <td>23.830448</td>
    </tr>
  </tbody>
</table>
</div>

#### 4. Availability differs significantly by borough
Annual availability patterns also vary by location, with some boroughs showing higher average availability than others.

<img width="854" height="532" alt="image" src="https://github.com/user-attachments/assets/fa22bbc6-d727-4940-8c73-5adefe59595a" />

---

### Cautionary insights

#### 5. Price-related conclusions should be interpreted with caution
Although price summaries can be calculated, the distribution appears unusually uniform across categories.

<img width="862" height="473" alt="image" src="https://github.com/user-attachments/assets/f85e7b98-8f00-4f96-b184-7f6f38f1ffa1" />

#### 6. Price does not show realistic differentiation by room type or borough
In real market conditions, strong variation would be expected between boroughs and accommodation types. Since this pattern is not clearly reflected in the dataset, pricing insights were treated as analytically limited.

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>room_type</th>
      <th>mean</th>
      <th>median</th>
      <th>min</th>
      <th>max</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Hotel room</td>
      <td>666.391304</td>
      <td>643.0</td>
      <td>50.0</td>
      <td>1193.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Shared room</td>
      <td>634.595438</td>
      <td>655.0</td>
      <td>50.0</td>
      <td>1199.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Entire home/apt</td>
      <td>626.142286</td>
      <td>626.0</td>
      <td>50.0</td>
      <td>1200.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Private room</td>
      <td>624.766004</td>
      <td>623.0</td>
      <td>50.0</td>
      <td>1200.0</td>
    </tr>
  </tbody>
</table>
</div>


---

## Data Quality Validation

A dedicated data quality review was included as part of the project.

### Main issues identified

- missing values in important variables
- inconsistent category labels
- invalid negative values
- unrealistic annual availability values
- future dates in `last_review`
- suspiciously uniform price behavior across segments

### Impact on the analysis

These issues do not invalidate the entire project, but they do affect the level of confidence that can be assigned to different findings.

For this reason, the final interpretation distinguishes between:

- **High-confidence insights**: findings considered stable and interpretable
- **Cautionary insights**: findings that may reflect dataset limitations rather than real market patterns

This validation step improves the credibility of the project and demonstrates analytical judgment beyond basic EDA.

---

## Tools Used

- **Python**
- **Pandas**
- **Matplotlib**
- **Seaborn**
- **Jupyter Notebook**

---

## Final Conclusion

This project shows that useful descriptive analysis can still be produced from imperfect data when data quality issues are explicitly documented and interpreted carefully.

The strongest findings in this dataset relate to:

listing concentration
room type composition
review activity
availability patterns

However, pricing behavior appears too uniform to support robust pricing conclusions. Rather than overinterpreting this variable, the project flags it as analytically limited.

This case study demonstrates not only technical skills in Python and dashboarding, but also critical thinking, data validation, and professional communication.

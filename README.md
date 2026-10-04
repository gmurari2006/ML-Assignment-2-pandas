# Assignment 2 — Pandas: Messy Data Handling

## Overview

This assignment focuses on handling messy real-world data using Pandas.

The analysis is performed on the AB_NYC_2019 Airbnb dataset. The notebook demonstrates practical techniques for memory optimisation, DataFrame profiling, duplicate detection, text cleaning, regular expression extraction, date processing, GroupBy operations, transform(), apply(), pivoting, merging, rolling analysis, ranking, and data export.

## Dataset

Dataset: AB_NYC_2019 Airbnb Dataset

The dataset contains Airbnb listing information from New York City.

The dataset includes information such as:

- Listing ID
- Listing name
- Host information
- Neighbourhood
- Neighbourhood group
- Latitude and longitude
- Room type
- Price
- Minimum nights
- Number of reviews
- Last review date
- Reviews per month
- Host listing count
- Availability

Dataset source:

https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data

## Tools and Technologies

- Python
- Pandas
- NumPy
- Google Colab
- Google Drive
- Jupyter Notebook

## Assignment Tasks

### 1. Memory Optimisation

The DataFrame memory usage was measured before and after optimisation.

Memory before optimisation:

19.16 MB

Memory after optimisation:

8.62 MB

Memory saving:

55.03%

Numeric columns were downcast where appropriate, and low-cardinality text columns were converted to categorical data types.

### 2. DataFrame Profiling

A complete profiling DataFrame was created with one row per column.

The profile includes:

- Data type
- Missing value count
- Missing percentage
- Unique value count
- Most frequent value
- Frequency of the most frequent value

The dataset contains 48,895 rows and 16 columns.

### 3. Duplicate Detection

Exact duplicate rows were checked.

Exact duplicate rows:

0

Duplicate records were also checked using the listing ID as the key.

### 4. Text Cleaning

The room_type column was cleaned by:

- Removing unnecessary whitespace
- Standardising text case
- Collapsing inconsistent labels into a standard set

The standard room types are:

- Entire Home/Apt
- Private Room
- Shared Room

Value counts were examined before and after cleaning.

### 5. Regular Expression Extraction

A regular expression was used to extract numeric values from a text column into a new numeric column.

The number of rows that did not match the regular expression was also reported.

### 6. Date Parsing

The last_review column was converted to a datetime format using errors="coerce".

The following date features were created:

- Review year
- Review month
- Review day of week
- Review quarter

Number of values that failed date parsing:

0

### 7. GroupBy and Named Aggregation

The data was grouped by neighbourhood_group.

The following aggregations were calculated:

- Listing count
- Average price
- Median price
- Average number of reviews
- Price range using a custom function

### 8. Group-Based Transformation

The Pandas transform() function was used to calculate the mean price within each neighbourhood group.

A new column was created containing the difference between each listing's price and its group's average price.

transform() is appropriate because it returns a result with the same number of rows as the original DataFrame, allowing the group-level mean to be aligned directly with every original row.

### 9. Pivot and Melt

A pivot table is created using categorical columns and a numeric column.

The resulting pivot table is then converted back to long format using melt().

The round trip is checked to confirm that the reshaping is lossless.

### 10. Merge Operations

The DataFrame is divided into two DataFrames sharing a common key.

The two DataFrames are merged using:

- inner
- left
- outer

The resulting row counts are compared and the differences between the merge types are explained.

The validate argument is also used to demonstrate many-to-many merge behaviour.

### 11. Rolling Mean and Ranking

The data is sorted by date within each group.

A 7-row rolling mean of a numeric column is calculated for each group.

A rank is also assigned to each row within its group.

### 12. Suspicious Records

Three suspicious records are identified from the dataset.

Each suspicious record is examined and the reason it is considered problematic is explained.

### 13. CSV and Parquet Export

The cleaned DataFrame is saved in both CSV and Parquet formats.

The file size and loading time of both formats are compared.

## Results

### Memory Optimisation

Memory before optimisation:

19.16 MB

Memory after optimisation:

8.62 MB

Memory saving:

55.03%

### File Size Comparison

CSV file size:

To be filled after Q13.

Parquet file size:

To be filled after Q13.

### Load Time Comparison

CSV load time:

To be filled after Q13.

Parquet load time:

To be filled after Q13.

## Repository Contents

```text
ml-assignment-2-pandas/
│
├── assignment2_pandas.ipynb
├── AB_NYC_2019.csv
└── README.md

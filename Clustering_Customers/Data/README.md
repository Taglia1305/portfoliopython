# Data — Mall Customers Dataset

## File

`Mall_Customers.csv`

## Description

Dataset containing anonymised demographic and behavioural data for 200 customers of a shopping mall. Each record represents a single customer and includes income, age, gender, and a proprietary spending score assigned by the mall based on purchasing history and behaviour.

The dataset is a standard benchmark for unsupervised segmentation tasks and is used in this project as the basis for K-Means clustering.

## Schema

| Column | Type | Range | Description |
|---|---|---|---|
| `CustomerID` | integer | 1 – 200 | Unique customer identifier. Not used in modelling. |
| `Gender` | string | Male / Female | Customer gender. |
| `Age` | integer | 18 – 70 | Customer age in years. |
| `Annual Income (k$)` | integer | 15 – 137 | Annual income in thousands of USD. |
| `Spending Score (1-100)` | integer | 1 – 99 | Mall-assigned score (1 = lowest engagement, 100 = highest). |

## Summary Statistics

| | Age | Annual Income (k$) | Spending Score (1-100) |
|---|---|---|---|
| Count | 200 | 200 | 200 |
| Mean | 38.8 | 60.6 | 50.2 |
| Std | 14.0 | 26.3 | 25.8 |
| Min | 18 | 15 | 1 |
| 25th percentile | 28.8 | 41.5 | 34.8 |
| Median | 36.0 | 61.5 | 50.0 |
| 75th percentile | 49.0 | 78.0 | 73.0 |
| Max | 70 | 137 | 99 |

**Gender split:** 112 Female (56%) — 88 Male (44%)

## Data Quality

No missing values across all 200 records and 5 columns. No duplicates. No preprocessing was required before EDA.

## Usage in This Project

Two features are used as input to the clustering model: `Annual Income (k$)` and `Spending Score (1-100)`. `CustomerID` is dropped before any analysis. `Gender` and `Age` are retained for post-hoc cluster profiling but are not fed into the algorithm — their variation across clusters serves as an independent validation of segmentation quality.

## Source

Publicly available on [Kaggle](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python).  
Original contributor: Vjchoudhary7.

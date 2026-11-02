# Task 1: Data Preprocessing for Machine Learning

## Internship
Codveda Technologies – Machine Learning Internship

## Project Overview
This task focuses on preprocessing a historical stock prices dataset to prepare it for potential machine learning applications.

The dataset contains daily stock market records, including stock symbols, trading dates, opening prices, highest prices, lowest prices, closing prices, and trading volumes.

## Dataset Information
- Original records: 497,472
- Stock symbols: 505
- Date range: January 2, 2014 – December 29, 2017
- Original columns: 7

## Data Preprocessing Steps

1. **Data Inspection:** Examined dataset dimensions, data types, missing values, and duplicate records.
2. **Date Conversion:** Converted the date column into a datetime format.
3. **Missing Values Handling:** Identified 11 records with missing OHLC values and excluded them from the working dataset to avoid inventing missing prices.
4. **Price Anomaly Detection:** Identified 12 records with inconsistencies in OHLC relationships. These records were flagged and retained for further investigation.
5. **Feature Engineering:** Extracted year, month, day, and weekday information from the date column.
6. **Log Transformation:** Applied `log1p` to trading volume to reduce its strong right skewness.
7. **Cyclical Encoding:** Applied sine and cosine transformations to represent month and weekday cyclicality.
8. **Duplicate Investigation:** Investigated two apparent duplicate feature rows and confirmed that they represented different trading dates, so no additional records were removed.
9. **Feature Preparation:** Prepared a dataset containing 11 features.
10. **Preprocessing Pipeline:** Built a Scikit-learn pipeline using median imputation, standard scaling, most-frequent categorical imputation, and One-Hot Encoding.

## Key Results

- Final working records: 497,461
- Remaining missing values: 0
- Original exact duplicate records: 0
- Duplicate symbol-date pairs: 0
- Unique stock symbols: 505
- Volume skewness before transformation: 10.3222
- Volume skewness after transformation: 0.4007
- Detected price anomaly records: 12

## Pipeline Validation

The preprocessing pipeline was tested on a sample of 1,000 records.

- Original sample shape: (1000, 11)
- Transformed sample shape: (1000, 443)
- Unknown categorical value test: Passed

The fitted pipeline was trained on the sample for validation purposes only. It is not a final production preprocessing artifact.

## Important Notes

The detected price anomalies were retained rather than automatically corrected or deleted. Their underlying causes require further investigation before using the affected records in predictive modeling.

The dataset does not currently define a prediction target. Therefore, no supervised model training or predictive evaluation was performed.

For future modeling, preprocessing parameters must be fitted using training data only, with a time-aware data split to prevent data leakage.

## Tools and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib

## Project Status
Data inspection, cleaning decisions, feature engineering, and preprocessing pipeline validation have been completed.

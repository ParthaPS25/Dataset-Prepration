# Dataset-Prepration
This project demonstrates essential **data preprocessing** techniques for machine learning workflows. It includes **missing value imputation**, **exploratory data analysis (EDA)**, and various **encoding methods** such as One-Hot Encoding, Ordinal Encoding, and Label Encoding.

Table of Contents
Project Overview
What I did
Key Techniques Covered
How to run
File structure
Requirements
Notes & Recommendations

Project Overview
This project walks through cleaning and preparing a tabular dataset for machine learning. It focuses on:
identifying and handling missing values
detecting and handling outliers
performing exploratory data analysis (EDA)
encoding categorical variables
applying feature scaling
All steps are implemented in the provided Jupyter notebook with explanatory comments.

What I did

Missing Value Imputation: identified columns with missing data and handled them using:
  Simple approaches (mean / median for numerical, mode for categorical)
  SimpleImputer from scikit-learn
  column-wise transformers (e.g., ColumnTransformer) when combining different imputers for different column types

Outlier detection & handling :
  Z-score method: used the absolute z-score and filtered rows where |z| < 3 (or a chosen threshold) to detect outliers.
  IQR method: computed Q1, Q3, and IQR = Q3 - Q1 and flagged values outside Q1 - 1.5*IQR and Q3 + 1.5*IQR as outliers.
  Handling strategies: removed extreme rows, or applied winsorization/capping depending on the column and modeling needs.

Exploratory Data Analysis (EDA): inspected data distributions, checked class balance and summary statistics, visualized using histograms and box plots.

Encoding categorical variables:
  One-Hot Encoding for nominal features (OneHotEncoder / pd.get_dummies)
  Ordinal Encoding for ordered categories (OrdinalEncoder) — mapped category order where relevant
  Label Encoding for target or non-ordinal single-column encodings (LabelEncoder) when appropriate

Feature scaling (ADDED):
  StandardScaler (zero mean, unit variance) — generally used for algorithms that assume normally distributed features (e.g., PCA, linear models that use distance)
  MinMaxScaler (scales to [0,1]) — useful for bounded inputs or when features need to be on the same scale
  RobustScaler (uses median and IQR) — preferable when outliers are present
  Applied scalers using ColumnTransformer so preprocessing can be reproduced and exported




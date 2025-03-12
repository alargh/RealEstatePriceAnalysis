# Real Estate Price Prediction Model

## Overview
This project involves analyzing a dataset related to housing prices in Austin and neighboring cities. The goal is to perform exploratory data analysis (EDA), preprocess the data, and build a predictive model to estimate housing prices based on various features.

## Dataset
The dataset contains a mix of numerical and categorical data, including features like latitude, longitude, number of bedrooms, and year built.

## Technical Environment
- **Programming Language:** Python
- **Libraries Used:**
  - `pandas` for data manipulation
  - `numpy` for numerical operations
  - `matplotlib` and `seaborn` for data visualization
  - `scikit-learn` for model training and evaluation
  - `xgboost` for building the regression model
  - `haystack` for NLP tasks

## Model Design Process
### Target Variable
- **Target Variable:** `latestPrice` (total property price)

### Input Variables
- **Key Features:**
  - `zipcode` (target encoded as `zip_smooth`)
  - `latitude` and `longitude` (target encoded and combined into `lat_long`)
  - `livingAreaSqFt` and `lotSizeSqFt` (scaled using `StandardScaler`)
  - `numberOfBedrooms` and `numberOfBathrooms` (one-hot encoded)
  - `AvgSchoolRating` (scaled)
  - `garageSpaces` and `parkingSpaces`
  - `yearBuilt` (target encoded as `year_smooth`)
  - Features derived from the `description` column using NLP techniques

### Outlier Removal
- **Methods:**
  - IQR Outlier Removal
  - Manual Outlier Removal using visualization

### Natural Language Processing (NLP)
- **Techniques Used:** Named Entity Recognition (NER) to extract keywords from property descriptions.

## Model Selection
- **Model:** XGBoost
- **Hyperparameter Tuning:** RandomizedSearchCV
- **Preprocessing:**
  - Categorical features: OneHotEncoding
  - Continuous features: StandardScaler

## Evaluation Metrics
- **Root Mean Squared Error (RMSE):** 132,378.36
- **Mean Squared Error (MSE):** 17,524,029,440.0
- **R² Score:** 76.67%

## Generative AI Usage
- **NLP:** Used to generate a list of stop words for NER processing.
- **Report Writing:** LLMs were used to streamline the report writing process.

# Stock-Market-Index-Prediction-using-Random-Forest-Regressor

This project uses historical S&P 500 index data to predict whether the price will go up or down the next day. The core approach involves feature engineering and machine learning using a Random Forest classifier.

**Project Overview**

Data Source: Historical S&P 500 data via Yahoo Finance (yfinance).

Features: Includes Open, High, Low, Close, Volume, and engineered features such as rolling averages and trends over multiple horizons.

Model: Random Forest classifier, trained and validated using a custom backtesting framework.

Output: Predicts whether the S&P 500 will close higher or lower the next day.

**Features**

**Original Features**

Open, High, Low, Close, Volume

**Engineered Features**

Tomorrow: The next day's closing price (shifted from Close)

Target: Binary indicator if Tomorrow > Close (1 if True, else 0)

Rolling window features (e.g., Close_Ratio_2, Close_Ratio_5, etc.): Ratio of today's close to the rolling average close over various horizons

Trend features (e.g., Trend_2, Trend_5, etc.): Sum of Target over the previous horizon days

**Code Structure**

**Data Loading**

Fetches S&P 500 data using yfinance if not already downloaded.

Saves data as sp500.csv for future use.

**Feature Engineering**

Creates Tomorrow and Target columns.

Adds rolling window and trend features for multiple horizons.

Model Training and Prediction

Trains a Random Forest classifier using a subset of features.

Implements a custom backtesting function to evaluate model performance over time.

**Evaluation**

Computes precision score for predictions.

Visualizes predictions vs. actuals.


**Results**

Precision Score: 0.571 (57.1% accuracy in predicting upward movements)

Prediction Distribution:

0.0 (Down): 4,561 predictions

1.0 (Up): 870 predictions

Actual Distribution:

Upward days (1): 54.6%

Downward days (0): 45.4%

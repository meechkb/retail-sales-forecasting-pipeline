# Retail Sales Forecasting Pipeline

## Overview
This project builds an end-to-end machine learning pipeline to forecast retail sales using historical transaction data. It transforms raw multi-sheet Excel data into a structured time-series dataset, engineers predictive features, and evaluates multiple machine learning and deep learning models.

## Problem Statement
Retail businesses rely on accurate demand forecasting to optimize inventory, staffing, and revenue strategies. However, raw transactional data is often incomplete, inconsistent, and not immediately suitable for predictive modeling.

This project addresses that challenge by cleaning, structuring, and transforming raw data into a format suitable for time-series forecasting.

## Data Pipeline

### Data Ingestion
- Multi-sheet Excel dataset containing retail transactions (2009–2011)
- Combined into a single unified dataset

### Data Cleaning
- Removed rows with missing values in key columns
- Filtered out canceled invoices (Invoice values beginning with "C")
- Removed invalid records with negative quantity or price

### Feature Engineering
- Created Sales column (Quantity × Price)
- Aggregated daily sales totals
- Filled missing dates to maintain continuous time-series data
- Added time-based features:
  - Day of week
  - Month
  - Quarter
  - Year
- Created predictive features:
  - Lag features (1, 7, 14 days)
  - Rolling mean and standard deviation (7-day window)

## Time-Series Transformation
- Converted data into supervised learning format using a sliding window approach
- Window size: 30 days
- Each input sequence predicts the next day’s sales value

## Models Implemented

### Machine Learning Models
- Decision Tree Regressor
- Random Forest Regressor
- XGBoost Regressor

### Deep Learning Models
- LSTM (Long Short-Term Memory)
- GRU (Gated Recurrent Unit)
- Transformer-based model using multi-head attention

## Evaluation Metrics
Models are evaluated using:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

## Visualizations
The project includes:
- Daily sales trend over time
- Sales distribution by day of week
- Sales distribution by month
- Feature importance (Random Forest and XGBoost)
- Actual vs predicted sales comparison (GRU model)

## Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- TensorFlow / Keras
- Matplotlib, Seaborn

## Project Structure

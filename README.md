# Retail Sales Forecasting Pipeline

## Overview
This project builds an end-to-end machine learning pipeline to forecast retail sales using historical transaction data. It transforms raw multi-sheet Excel data into a structured time-series dataset, engineers predictive features, and evaluates multiple machine learning and deep learning models.

This pipeline demonstrates how raw business data can be converted into actionable forecasts for inventory planning, demand forecasting, and revenue optimization.

---

## Problem Statement
Retail businesses rely on accurate demand forecasting to optimize inventory, staffing, and revenue strategies. However, raw transactional data is often incomplete, inconsistent, and not immediately suitable for predictive modeling.

This project addresses that challenge by cleaning, structuring, and transforming raw data into a format suitable for time-series forecasting.

---

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

---

## Time-Series Transformation
- Converted data into supervised learning format using a sliding window approach
- Window size: 30 days
- Each input sequence predicts the next day’s sales value

---

## Models Implemented

### Machine Learning Models
- Decision Tree Regressor
- Random Forest Regressor
- XGBoost Regressor

### Deep Learning Models
- LSTM (Long Short-Term Memory)
- GRU (Gated Recurrent Unit)
- Transformer-based model using multi-head attention

---

## Evaluation Metrics
Models are evaluated using:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

---

## Visualizations

### Sample Output

![Daily Sales Trend](outputs/daily_sales_trend.png)

Additional visualizations included in the project:
- Sales distribution by day of week
- Sales distribution by month
- Feature importance (Random Forest and XGBoost)
- Actual vs predicted sales comparison (GRU model)

---

## Dataset

The dataset used in this project is not included in the repository.

To run this project:

1. Obtain a retail transaction dataset (Excel format with fields such as Invoice, Quantity, Price, and InvoiceDate)
2. Place the dataset in the following directory:  data/raw/Retail_forecasting.ipynb 

Note: The pipeline is designed to work with structured retail transaction datasets and can be adapted to similar time-series forecasting problems.

---

## Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- TensorFlow / Keras
- Matplotlib, Seaborn

---

## Project Structure

retail-sales-forecasting-pipeline/
├── data/
│ └── raw/
│ └── (dataset placed here)
├── outputs/
│ └── daily_sales_trend.png
├── retail_forecasting_pipeline.ipynb
├── README.md
└── requirements.txt


---

## How to Run

1. Clone the repository: git clone https://github.com/meechkb/retail-sales-forecasting-pipeline.git
cd retail-sales-forecasting-pipeline


2. Place the dataset in: data/raw/Retail_forecasting.xlsx

3.  Run the notebook: retail_forecasting_pipeline.ipynb

---

## Key Takeaways
- Built a complete data pipeline from raw transactional data to model evaluation
- Applied feature engineering techniques for time-series forecasting
- Compared traditional machine learning models with deep learning approaches
- Generated visual insights to support data-driven decision making

---

## Future Improvements
- Hyperparameter tuning for improved model performance
- Model deployment via API or dashboard
- Integration of external features such as holidays and promotions
- Real-time data pipeline implementation

---

## Author
Demetri Brown  
Data Science Student focused on data engineering, machine learning, and time-series analysis

# Data-Science-Project
Introduction
Welcome to the Data Science Internship Assignment. In this project, you will work with real-world retail sales data to develop a forecasting model that predicts future sales for thousands of product families across different stores in Ecuador. This assignment will help you understand how external factors like promotions, holidays, economic conditions, and events impact sales, and how machine learning models can be used to improve demand forecasting.

**This assignment is structured into two main parts:**

Data Processing and Feature Engineering (Day 1) - Cleaning, transforming, and exploring the dataset.
Model Selection, Forecasting, and Evaluation (Day 2) - Training different forecasting models, comparing their performance, and presenting insights.

Dataset Overview
The dataset consists of multiple files providing sales data and additional influencing factors:

train.csv - Historical sales data.
test.csv - The test set for which sales need to be predicted.
stores.csv - Metadata about store locations and clusters.
oil.csv - Daily oil prices (affecting Ecuador's economy).
holidays_events.csv - Information about holidays and special events.
Your task is to forecast daily sales for each product family at each store for the next 15 days after the last training date.

## Project Structure
The project is structured into two main parts:

1. Data Processing and Feature Engineering
Data Cleaning: Handle missing values, convert date columns, and merge datasets.
Feature Engineering: Create time-based, event-based, and rolling statistics features.
Exploratory Data Analysis (EDA): Visualize sales trends, analyze correlations, and identify anomalies.

2. Model Selection, Forecasting, and Evaluation
Model Training: Train multiple forecasting models (Naïve, ARIMA, Random Forest, XGBoost, LSTM).
Model Evaluation: Compare models using RMSE, MAPE, and R-squared.
Visualization: Plot historical vs. predicted sales and feature importance.
Business Insights: Summarize model performance and suggest strategies for improving sales forecasting.

##Installation
To run this project, you need the following Python libraries:

Pandas

NumPy

Matplotlib

Seaborn

Scikit-learn

Statsmodels

XGBoost

Keras (for LSTM)


#### Run the Jupyter Notebook:
Open the Jupyter Notebook (sales_forecasting.ipynb) and run the cells step-by-step.
The notebook is divided into two parts:

### Part 1: Data Processing and Feature Engineering.

### Part 2: Model Selection, Forecasting, and Evaluation.

## View Results:
The notebook will generate visualizations, model performance metrics, and business insights.
The final model predictions will be saved in a CSV file (predictions.csv).

## Code Explanation
## 1. Data Processing and Feature Engineering

Data Cleaning:
Missing values in oil prices are filled using interpolation.
Date columns are converted to datetime format.
Datasets are merged based on common columns (store_nbr and date).

Feature Engineering:
Time-based features: day, week, month, year, day_of_week.
Event-based features: is_holiday, onpromotion, is_payday, is_earthquake.
Rolling statistics: rolling_avg_7, rolling_std_7.

Exploratory Data Analysis (EDA):
Visualize sales trends over time.
Analyze sales before and after holidays and promotions.
Check correlations between oil prices and sales.

## 2. Model Selection, Forecasting, and Evaluation

### 1.Model Training:
Baseline Model (Naïve Forecasting).
ARIMA (AutoRegressive Integrated Moving Average).
Random Forest Regressor.
XGBoost.
LSTM (Long Short-Term Memory Neural Network).

### 2.Model Evaluation:
Models are evaluated using RMSE, MAPE, and R-squared.
Visualize actual vs. predicted sales.

### 3.Visualization
Plot historical sales and predicted sales.
Compare model performances using error metrics.
Visualize feature importance (for Random Forest/XGBoost)

### 4.Interpretation and Business Insights
Model Comparison Based on Metrics

Interpretation:
1. RMSE (Root Mean Square Error)
XGBoost has the lowest RMSE (307.43), meaning its predictions are closest to actual values.
ARIMA performs the worst (1411.32).
Random Forest is better than ARIMA but worse than XGBoost.

2. R² (Coefficient of Determination)
XGBoost has the highest R² (0.95), indicating it explains 95% of the variance.
Random Forest is close with 0.90.
ARIMA has negative R², meaning it's worse than simply using the mean of the data.

3. MAPE (Mean Absolute Percentage Error) – Extremely Large!
These numbers are way too big to be reasonable. This suggests:
Some predictions are dividing by very small actual values (causing MAPE to explode).
Data scaling issues (e.g., log-transformed data).
Errors when computing percentage format (should be in 0-100% range).

### Best Performing Model
Based on the error metrics, the [XGBoost Model] performed best with the lowest RMSE and highest R-Squared value. This model effectively captured the sales patterns and external factors.

### Impact of External Factors
Holidays: Sales showed a significant increase during national holidays, particularly around [2016-04-16]. Models with holiday data as features showed improved accuracy.

Oil Prices: There was a negative correlation between oil prices and sales in certain product families, indicating that higher fuel prices decreased sales.

Promotions: Promotional events had a notable impact on sales spikes, especially for [oils]. Incorporating promotion data improved model performance.

### Business Strategies

Inventory Planning: Use sales forecasts to optimize inventory levels, especially during peak holiday seasons.
Targeted Promotions: Align promotional campaigns with periods of low predicted sales to boost revenue.
Price Adjustments: Monitor oil prices and adjust pricing strategies accordingly to maintain sales volumes.

By leveraging these insights, the business can improve demand forecasting, reduce stockouts, and enhance customer satisfaction.

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

Project Structure
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

Installation
To run this project, you need the following Python libraries:

Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn
Statsmodels
XGBoost
Keras (for LSTM)


Run the Jupyter Notebook:
Open the Jupyter Notebook (sales_forecasting.ipynb) and run the cells step-by-step.
The notebook is divided into two parts:
Part 1: Data Processing and Feature Engineering.

Part 2: Model Selection, Forecasting, and Evaluation.

View Results:
The notebook will generate visualizations, model performance metrics, and business insights.
The final model predictions will be saved in a CSV file (predictions.csv).

Code Explanation
1. Data Processing and Feature Engineering

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

2. Model Selection, Forecasting, and Evaluation

Model Training:
Baseline Model (Naïve Forecasting).
ARIMA (AutoRegressive Integrated Moving Average).
Random Forest Regressor.
XGBoost.
LSTM (Long Short-Term Memory Neural Network).

Model Evaluation:
Models are evaluated using RMSE, MAPE, and R-squared.
Visualize actual vs. predicted sales.

 Interpretation and Business Insights
Model Comparison Based on Metrics

Model	RMSE ↓ (Lower is better)	MAPE ↓ (Lower is better)	R² ↑ (Higher is better)
ARIMA	1411.32	10195183152728457216.00%	-0.06 (very bad)
Random Forest	431.90	975344682013655424.00%	0.90 (good)
XGBoost	307.43 (best)	728251545701144448.00%	0.95 (best)
Interpretation

RMSE (Root Mean Square Error)
XGBoost has the lowest RMSE (307.43), meaning its predictions are closest to actual values.
ARIMA performs the worst (1411.32).
Random Forest is better than ARIMA but worse than XGBoost.
R² (Coefficient of Determination)
XGBoost has the highest R² (0.95), indicating it explains 95% of the variance.
Random Forest is close with 0.90.
ARIMA has negative R², meaning it's worse than simply using the mean of the data.
MAPE (Mean Absolute Percentage Error) – Extremely Large!
These numbers are way too big to be reasonable. This suggests:
Some predictions are dividing by very small actual values (causing MAPE to explode).
Data scaling issues (e.g., log-transformed data).
Errors when computing percentage format (should be in 0-100% range).

Results
Best Model: The best-performing model was XGBoost with an RMSE of X and MAPE of Y.

Key Insights:
Sales are higher during holidays and promotions.
Oil prices have a moderate negative correlation with sales.
Paydays (15th and last day of the month) show a spike in sales.

Future Work

Incorporate additional external factors (e.g., weather data, competitor pricing).
Experiment with more advanced models like Prophet or deep learning architectures.
Deploy the model as a web application for real-time sales forecasting.

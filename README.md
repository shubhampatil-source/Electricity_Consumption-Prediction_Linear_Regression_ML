# Electricity_Consumption-Prediction_Linear_Regression_ML
Electricity Demand Prediction using Machine Learning
Overview

This project focuses on predicting residential electricity consumption using regression techniques. It emphasizes real-world data challenges such as skewed distributions, multicollinearity, and heteroscedasticity, while delivering interpretable insights and a deployable application.

Problem Statement

Accurate electricity demand prediction is essential for energy planning, infrastructure optimization, and sustainability. The objective is to build a model that estimates residential electricity consumption based on demographic and environmental factors.

Objectives
Predict electricity consumption (GWh)
Identify key demand drivers
Handle real-world data issues:

Skewness

Multicollinearity

Heteroscedasticity

Deploy model as an interactive web app

Dataset:

The dataset includes:

Population data

Cooling Degree Days (temperature proxy)

Renewable energy consumption

CO₂ emissions (used initially, later removed)


Exploratory Data Analysis

Key findings:

Target variable showed strong right skewness

Several features had high skew (up to 9+)

High correlation between population and CO₂ emissions

Presence of extreme but valid values


Data Preprocessing

Log Transformation:

Applied to target and skewed features

Reduced skewness and stabilized variance

Outlier Handling: 

Outliers were retained as they represent real-world high-demand scenarios

Log transformation used to reduce their impact

Feature Engineering:

Removed CO₂ emissions (proxy variable)

Created total renewable energy feature

Added interaction term (Population × Temperature)

Multicollinearity Handling:

Used Variance Inflation Factor (VIF)

Reduced VIF from >70 to <10 using:

Feature removal

Feature aggregation

Mean centering


Model Building
Models Used:
Linear Regression
Ridge Regression (did not improve performance)

Final Model:

Linear Regression with engineered features


Model Performance

Metric	Value:

R² Score	0.72

RMSE	~1.18M

MAE	~617K

MAPE	~27%


Visualizations:

Distribution plots (before/after transformation)

Correlation heatmap

Actual vs Predicted plot

Residual plot


Key Insights: 

Population is the strongest driver of electricity demand

Temperature moderately impacts consumption

Renewable energy has weak direct impact on demand

Model underestimates high consumption values


Limitations:

Presence of heteroscedasticity

Linear model cannot fully capture non-linear patterns

Reduced accuracy for extreme values


Future Improvements
Implement tree-based models (Random Forest, XGBoost)

Add economic and urbanization features

Explore time-series forecasting


Deployment

The model is deployed using Streamlit for interactive predictions.

Live App

(Add your Streamlit link here)


Tech Stack

Python

Pandas, NumPy

Scikit-learn

Matplotlib, Seaborn

Streamlit


Project Structure
electricity-demand-prediction/
│
├── app.py
├── model.pkl
├── scaler.pkl
├── requirements.txt
├── notebooks/
│   ├── EDA.ipynb
│   ├── Modeling.ipynb


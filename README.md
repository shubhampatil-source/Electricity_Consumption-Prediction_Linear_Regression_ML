# Electricity_Consumption-Prediction_Linear_Regression_ML
Electricity Demand Prediction using Machine Learning

Overview:

This project focuses on predicting residential electricity consumption using linear regression techniques. It emphasizes real-world data challenges such as skewed distributions, multicollinearity, and heteroscedasticity, while delivering interpretable insights and a deployable application.


Problem Statement:

Accurate electricity demand prediction is essential for energy planning, infrastructure optimization, and sustainability. The objective is to build a model that estimates residential electricity consumption based on demographic and environmental factors.


Objectives:

•	Predict electricity consumption (GWh)

•	Identify key demand drivers

•	Handle real-world data issues:

1.	Skewness
2.	Multicollinearity
3.	Heteroscedasticity
4.	Deploy model as an interactive web app


Dataset:

The dataset includes: Population data, Cooling Degree Days (temperature proxy), Renewable energy consumption, CO₂ emissions (used initially, later removed). Along with this additional 33 columns present.


Dataset Link: 

https://www.kaggle.com/datasets/naveedtaimoor/electricity-consumption-dataset


Exploratory Data Analysis:


Key findings:

•	Target variable showed strong right skewness

•	Several features had high skew (up to 9+)

•	High correlation between population and CO₂ emissions

•	Presence of extreme but valid values


Data Preprocessing:

•	Log Transformation applied to target and skewed features. This helped to reduce skewness and stabilize variance.

•	Outliers were retained as they represent real-world high-demand scenarios. Log transformation used to reduce their impact.

•	Feature Engineering: Created total renewable energy feature and added mean centering interaction term (Population × Temperature). Centering was applied before creating interaction terms to reduce multicollinearity between the interaction term and the original variables. Without centering, the interaction term is highly correlated with its components, leading to inflated VIF values. Centering ensures that the interaction captures only the deviation effects, improving model stability and interpretability.

•	Multicollinearity Handling: Used Variance Inflation Factor (VIF) to find multicollinearity. And reduced VIF from >70 to <10 using feature removal and mean centering


Model Building: 
Models Used in this project is Linear Regression and Ridge Regression. Ridge Regression removed later because it did not improve performance.



Model Performance:

Metric	Value:

•	R² Score: 0.72

•	RMSE: ~1.18M

•	MAE: ~617K

•	MAPE: ~27%



Visualizations:

•	Distribution plots (before/after transformation)

•	Correlation heatmap

•	Actual vs Predicted plot

•	Residual plot



Key Insights: 

•	Population is the strongest driver of electricity demand

•	Temperature moderately impacts consumption

•	Renewable energy has weak direct impact on demand

•	Model underestimates high consumption values



Limitations:

•	Presence of heteroscedasticity

•	Linear model cannot fully capture non-linear patterns

•	Reduced accuracy for extreme values



Future Improvements:

•	Implement tree-based models (Random Forest, XGBoost)

•	Add economic and urbanization features

•	Explore time-series forecasting



Deployment: 

The model is deployed using Streamlit for interactive predictions.



Live App:
https://electricityconsumption-predictionlinearregressionml-hxibextfem.streamlit.app/



Tech Stack:

•	Python

•	Pandas, NumPy

•	Scikit-learn

•	Matplotlib, Seaborn

•	Streamlit





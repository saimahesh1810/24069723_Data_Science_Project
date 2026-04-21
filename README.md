# 24069723_Data_Science_Project
# Electricity Consumption Forecasting

## Overview
This project implements an end-to-end time series forecasting pipeline for household electricity consumption using classical models and machine learning. The focus is on realistic preprocessing, feature engineering, and evaluation under both one-step and recursive forecasting settings.

## Dataset
UCI Individual Household Electric Power Consumption dataset  
Target variable: Global_active_power (kW)  
Minute-level data resampled to hourly frequency

## Implementation Workflow
Data loading and datetime indexing  
Missing value handling using time-based interpolation  
Hourly resampling for noise reduction  
Feature engineering including lag features, rolling statistics, and calendar variables  
Chronological train–test split (80/20)  
Model training across baseline, SARIMA, and ML models  
Evaluation using MAE, RMSE, and sMAPE  
Recursive forecasting for realistic multi-step prediction  
Walk-forward validation for robustness

## Models Implemented
Naive and Seasonal Naive (baseline)  
SARIMA (classical time-series)  
Ridge Regression  
Random Forest  
XGBoost  
Recursive forecasting for Random Forest and XGBoost

## Repository Structure
├── individual+household+electric+power+consumption.zip
│──24069723_DS_Project.ipynb # Full end-to-end workflow
├── README.md # Project documentation

## Key Implementation Details
Lag features: [1, 2, 3, 6, 12, 24] hours  
Rolling windows: [3, 6, 12, 24] (shifted to avoid leakage)  
Seasonality handled via SARIMA (24-hour cycle)  
Recursive forecasting uses predicted values as future inputs  
Walk-forward validation uses expanding window with 3 folds  

## How to Run
Clone the repository  
Download dataset and place in data/raw/  
Run the notebook or modular scripts to reproduce results  

## Results Summary
XGBoost achieved best performance in one-step prediction  
Performance drops under recursive forecasting due to error accumulation  
Naive baseline remains highly competitive  
Walk-forward validation confirms stability differences across models  

## Dependencies
Python  
pandas  
numpy  
scikit-learn  
statsmodels  
xgboost  
matplotlib  
seaborn  

## References
Box et al. (2015), Time Series Analysis  
Chen and Guestrin (2016), XGBoost  
Hyndman and Athanasopoulos (2018), Forecasting Principles and Practice  
Hong et al. (2016), Global Energy Forecasting Competition  
UCI Machine Learning Repository

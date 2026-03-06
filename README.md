# Ecommerce Spend Forecasting

## Overview
This project builds a machine learning pipeline to predict customer spending in an e-commerce setting using the **Average Order Value (AOV)** as the target variable.

## Objective
The goal is to estimate the average amount spent by each customer based on aggregated purchase behavior and customer-level features.

## Dataset
The project uses the **Online Retail** dataset, a transactional e-commerce dataset.  
After cleaning the data, transactions were aggregated first at the invoice level and then at the customer level.

## Main preprocessing steps
- Removed rows without `CustomerID`
- Removed canceled invoices
- Removed transactions with non-positive quantity or price
- Created `LineTotal = Quantity * UnitPrice`
- Built customer-level features such as:
  - number of invoices
  - average quantity purchased
  - average number of products
  - average unit price
  - recency
  - tenure
  - country

## Target variable
The target variable is **AOV (Average Order Value)**, defined as the average invoice total per customer.

## Models evaluated
- Linear Regression
- Ridge Regression
- Lasso Regression
- KNN Regressor
- Gradient Boosting Regressor

A complementary conceptual classification exercise using **KNN Classifier** was also included to illustrate the difference between regression and classification.

## Validation strategy
- Train/test split: **80/20**
- Cross-validation: **5-Fold**
- Metrics used:
  - MAE
  - RMSE
  - R²

## Best model
The best final model was **Gradient Boosting Regressor**.

### Test performance
- **MAE:** 87.156
- **RMSE:** 203.870
- **R²:** 0.750

## Repository structure
- `notebooks/` → project notebook
- `reports/` → final report and figures
- `reports/figures/` → model evaluation plots
- `results/` → CSV files with model metrics

## Author
Valenthina Pérez Cifuentes

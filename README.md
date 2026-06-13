# Sales Prediction Using Python

## Project Overview

This project predicts product sales based on advertising expenditure across different marketing channels: TV, Radio, and Newspaper.

The objective is to identify which advertising channels contribute most to sales and build a reliable regression model for sales prediction.

## Dataset

The dataset contains 200 observations with the following variables:

- TV: Advertising budget spent on TV
- Radio: Advertising budget spent on Radio
- Newspaper: Advertising budget spent on Newspaper
- Sales: Product sales

## Project Workflow

1. Data loading and cleaning
2. Exploratory Data Analysis
3. Feature engineering
4. Cross-validation model comparison
5. Final model selection
6. Business interpretation

## Data Cleaning

The dataset had:

- 200 rows
- No missing values
- No duplicate records

The `Unnamed: 0` column was removed because it was only an index column and had no predictive value.

## Exploratory Data Analysis

Correlation with Sales:

| Feature | Correlation |
|---|---:|
| TV | 0.782 |
| Radio | 0.576 |
| Newspaper | 0.228 |
| Total Advertising | 0.868 |

TV advertising showed the strongest individual relationship with sales, followed by Radio. Newspaper had a weak relationship with sales.

## Feature Engineering

A new feature, `Total_Advertising`, was created by combining TV, Radio, and Newspaper expenditure.

However, cross-validation showed that using the individual TV and Radio features performed better than using Total Advertising alone.

## Model Comparison

All models were evaluated using 5-Fold Cross-Validation.

| Model | Mean R² | Mean MAE | Mean RMSE | Std R² |
|---|---:|---:|---:|---:|
| TV + Radio | 0.8844 | 1.2796 | 1.6936 | 0.0391 |
| TV + Radio + Newspaper | 0.8827 | 1.2873 | 1.7057 | 0.0395 |
| Total Advertising | 0.7403 | 1.9669 | 2.5850 | 0.0437 |

## Final Model

The best model used:

- TV
- Radio

Final model coefficients:

| Feature | Coefficient |
|---|---:|
| TV | 0.0458 |
| Radio | 0.1880 |

## Key Findings

- TV and Radio are the strongest predictors of sales.
- Newspaper advertising did not improve model performance.
- The final model explains approximately 88.4% of sales variation.
- Radio has a stronger marginal impact per unit of advertising spend than TV.
- Total Advertising had high correlation with Sales but performed worse in prediction, showing that correlation alone is not enough for model selection.

## Business Recommendation

The business should prioritise TV and Radio advertising when planning marketing budgets. Newspaper advertising appears to have limited predictive value and may not be the most effective channel for increasing sales.

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn<img width="2400" height="1500" alt="model_comparison" src="https://github.com/user-attachments/assets/de59ef8f-d254-47e2-9d82-2f947fe4506e" />
<img width="1800" height="1200" alt="feature_coefficients" src="https://github.com/user-attachments/assets/b82c04e5-16db-4925-87a0-fc2c249635ce" />
<img width="2400" height="1800" alt="correlation_heatmap" src="https://github.com/user-attachments/assets/da3a4f02-3c3b-441d-a34c-812abb2d76e0" />


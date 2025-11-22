# Random Forest MDD Severity Prediction

This project uses clinical and demographic information to predict the severity of depressive symptoms measured by the MADRS1 score. The data come from a depression study with variables such as gender, age group, inpatient status, marital status, work status and follow up MADRS2 scores.

## Overview

The goal of the analysis is to explore the structure of the depression dataset and to build regression models that predict MADRS1. The workflow includes data loading, cleaning, exploratory data analysis and model building. A linear regression model is first used as a baseline, followed by a Random Forest regressor that can capture nonlinear relationships among variables.

## Data and preprocessing

The dataset is loaded from scores.csv. Non numeric fields such as work are converted to numeric form. Missing values are handled by combining mean imputation for numeric columns and row wise deletion, leaving a cleaned numeric subset of the data.

A subset of columns is selected for modeling. The target variable is MADRS1, and the remaining numeric variables are used as predictors. The cleaned data are split into training and testing sets in an eighty to twenty ratio.

## Models

A linear regression model is trained on the training data and evaluated on the test data using mean squared error and the R squared score. This provides a simple baseline and an interpretable set of coefficients for each feature.

A Random Forest regressor is then trained on the same training set. The model is evaluated on the test set, and feature importance scores are extracted from the trained forest. These importance scores are combined with the feature names to create a ranking of the most influential predictors of MADRS1.

## Results

The linear regression model shows limited predictive performance on the small test set, and the negative R squared value suggests that the simple linear relationship does not fully capture the variability in MADRS1. The Random Forest model provides a more flexible fit and highlights MADRS2 and several clinical variables as important predictors.

Feature importance plots are generated for both the linear regression coefficients and the Random Forest importance scores. These visualizations help illustrate which characteristics of the patients are most strongly associated with higher or lower MADRS1 scores.

## Notes

The dataset is relatively small after cleaning, so the evaluation metrics are unstable and should be interpreted with caution. The current setup predicts MADRS1 using MADRS2 and other variables, which is useful for exploring associations but may not match all clinical use cases. An alternative design is to predict the follow up score MADRS2 from baseline features including MADRS1.

All code used for loading the data, running the analysis and fitting the models is contained in the notebook mdd_prediction.ipynb.

## Author

Hsiang Chen Yeh

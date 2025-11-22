##Random Forest MDD Severity Prediction

This project analyzes clinical and demographic information to model the severity of depressive symptoms, operationalized as the MADRS1 score. The dataset includes variables such as gender, age group, inpatient status, marital status, work status and follow up MADRS2 scores.

##Overview

The objective is to examine the structure of the depression dataset and to build regression models that predict MADRS1. The workflow includes data loading, preprocessing, exploratory data analysis and model development. A linear regression model is used as the baseline, followed by a Random Forest regressor that is able to capture nonlinear relationships in the data.

##Data and preprocessing

The dataset is loaded from mdd_scores_baseline.csv. Non numeric variables such as work are converted into numeric form. Missing values in numeric fields are filled using the mean, and remaining rows with incomplete information are removed. This results in a cleaned subset suitable for modeling.

A selected set of columns is used for prediction. MADRS1 is the target variable, and the other numeric variables serve as predictors. The processed data are divided into training and testing sets using an eighty twenty split.

##Models

A linear regression model is trained as a baseline and evaluated on the test data using mean squared error and the R squared score. This model provides an interpretable reference point for subsequent comparisons.

A Random Forest regressor is then fitted using the same training data. The model is evaluated on the test set, and feature importance scores are extracted. These scores are paired with the corresponding predictors to show which variables contribute most strongly to the model’s predictions of MADRS1.

##Results

The linear regression model displays limited predictive performance on the small test set. Negative R squared values indicate that linear relationships alone do not account for the observed variation in MADRS1. The Random Forest model provides a more flexible fit and identifies MADRS2 and several clinical indicators as influential predictors.

Feature importance plots are generated for both models. These visualizations summarize which patient characteristics are most closely related to differences in MADRS1 in the present dataset.

##Notes

The dataset becomes small after preprocessing, and the resulting evaluation metrics should be interpreted with caution. The current design predicts MADRS1 using MADRS2 and other variables, which supports an examination of associations but may not align with all clinical applications. A possible alternative is to use baseline variables, including MADRS1, to predict the follow up score MADRS2.

All analysis steps, including data cleaning, exploratory analysis and model fitting, are contained in the notebook mdd_prediction.ipynb.

##Author

Hsiang Chen Yeh

# **Random Forest MDD Severity Prediction**

This project examines clinical and demographic variables to model the severity of depressive symptoms, represented by the MADRS1 score. The dataset includes variables such as gender, age group, inpatient status, marital status, work status, and follow-up MADRS2 scores.

## **Overview**

The objective is to explore the dataset structure and develop predictive models for MADRS1. The workflow includes data loading, preprocessing, exploratory analysis, and model development. A linear regression model serves as the baseline, followed by a Random Forest regressor that captures nonlinear patterns in the data.

## **Data and Preprocessing**

The dataset is loaded from mdd_scores_baseline.csv.  
Non-numeric variables (e.g., work) are converted into numeric form. Numeric columns with missing values are imputed using the mean. Rows with remaining missing data are removed to create a clean dataset suitable for modeling.

MADRS1 is used as the target variable, and all other numeric variables are used as predictors. The processed data are split into 80% training and 20% testing.

## **Models**

### **Baseline: Linear Regression**

A linear regression model is trained and evaluated using mean squared error (MSE) and R².  
It serves as a simple interpretable reference model.

### **Random Forest Regressor**

A Random Forest model is trained using the same predictors.  
Its performance is evaluated on the test set, and feature-importance values are extracted to identify variables that most influence predictions of MADRS1.

## **Results**

The linear regression model demonstrates limited predictive accuracy on the small test set.  
Negative R² values indicate that linear relationships do not sufficiently explain the variability in MADRS1.

The Random Forest model provides a more flexible fit and identifies MADRS2 and other clinical indicators as influential predictors.  
Feature-importance plots summarize which patient characteristics are most strongly associated with variations in MADRS1.

## **Notes**

The dataset becomes quite small after preprocessing, so model evaluation metrics should be interpreted cautiously.  
The current design predicts MADRS1 using MADRS2 and other variables, which is useful for exploring associations but may not reflect all clinical applications.  
An alternative direction is to predict MADRS2 using baseline variables—including MADRS1.

All steps—including data loading, preprocessing, exploratory visualization, and modeling—are included in the notebook mdd_prediction.ipynb.

## **Author**

Hsiang Chen Yeh


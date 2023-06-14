# Credit-Risk-Classification

## Table of Contents
- [Background](#background)
- [Objective](#objective)
- [Credit Risk Analysis Report](#credit-risk-analysis-report)
- [Method](#method)
- [References](#references)
  
## Background

Use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

## Objective
  
Using knowledge of Python and supervised machine learning to train and evaluate the best model to use based on loan risk, where a healthy loan status is `0` and a high-risk loan status is `1`.

## Credit Risk Analysis Report

Please reference the file `credit_risk_analysis_report.md` for additional information regarding the machine learning models, including bulleted lists describing balanced accuracy scores, prediction and recall of all machine learning models and a summary of the results of the machine learning models with a recommendation on which model to use.

## Method

### Split the Data into Training and Testing Sets

1. Read the `lending_data.csv` data from Resources folder into a Pandas DataFrame.
2. Create labels set (y) from 'loan_status' column and create features (X) DataFrame from remaining columns.
3. Check balance of the labels variable (y) with value_counts function.
4. Split data into training and testing datasets by using train_test_split.

### Create a Logistic Regression Model with the Original Data

1. Fit a logistic regression model using the training data (`X_train` and `y_train`).
2. Save predictions on testing data labels using the testing feature data (`X_test`) and the fitted model.
3. Evaluate the mode's performance by completing the following:
        a. Calculate accuracy score of the model.
        b. Generate a confusion matrix.
        c. Print the classification report.

*Model 1 Summary:*
The logistic regression model trained on the original data has a 94.4% accuracy of predicting the two labels. As it relates to predicting the healthy loans (0), the model does very well, as is evidenced by an f1-score of 1.00 (100%). Conversely, the model only accurately predicted around 87% of the high-risk loans, and thus, there is evidence that the model could potentially use some improvement. The recall score for high-risk loans is 0.89, indicating that the model only identified 89% of all high-risk loans in the dataset.

### Predict a Logistic Regression Model with Resampled Training Data

1. Use the `RandomOverSampler` module from the imbalanced-learn library to resample the data. Confirm labels have an equal number of data points.

2. Use the `LogisticRegression` classifier and resampled data to fit the model and make predictions.
3. Evaluate the model's perforamnce by completing the following:
        a. Calculate accuracy score of the model.
        b. Generate a confusion matrix.
        c. Print the classification report.

*Model 2 Summary:*
The logistic regression model trained on the resampled data has a 96.6% accuracy of predicting the two labels. As it relates to predicting the healthy loans (0), this model also does very well, as is evidenced by precision and recall scores of 1.00 (100%). While there is no improvement in the precision score for the high-risk loans using the resampled regression model, there is improvement in the recall score, indicating the model can now predict all high-risk loans in the dataset.

### Overall Summary: 
Overall, when comparing the results of the two machine learning models, the resampled model appears to be the model of choice due to a balanced accuracy score of 99.6% vs. the 94.4% from the original model. Additionally, there was an improvement in the recall score for the high-risk loans from 89% to 100%. Thus, to reiterate, the over-sampled/resampled model seems to be the best choice for predicting true positives, meaning it is more effective at distinguishing high-risk loans with high recall accuracy. Simultaneously, the number of false positives decreases, which reveals the model is able to more appropriately and accurately classify health and high-risk loans accordingly.

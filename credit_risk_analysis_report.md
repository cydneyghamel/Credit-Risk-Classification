# Credit Risk Analysis Report

## Table of Contents
- [Overview/Purpose of the Analysis](#overviewpurpose-of-the-analysis)
- [Model Results](#model-results)
- [Summary](#summary)

## Overview/Purpose of the Analysis

**Purpose of the Analysis:**

The purpose of the analysis is to identify the creditworthiness of borrowers using various machine learning techniques. This is achieved through creating, training, and evaluating two models based on loan risk using a dataset of historical lending activity from a peer-to-peer lending services company. Through this analysis, we can determine whether or not a borrower is associated with a high risk and/or determine if a there is inaccurate determination of healthy loans as high-risk. By using logistic regression modeling, two models were created and evaluated using different approaches. The predictive variables in the models are the labels, which were 0 (healthy loan) and 1 (high-risk loan).

In the process of constructing the models, the dataset was split into features and labels, and further divided into training and testing sets. Specifically, Model 1 was built using the original training data while Model 2 was created using the RandomOverSampler module and fitted with resampled training data. Both models were evaluated based on the balance accuracy score, confusion matrices, and classification reports that included precision, recall, and f1-scores.

## Model Results

**Machine Learning Model 1 - Logistic Regression Model Fitted with Original Data:**

- Balanced Accuracy Score: 0.9442676901753825 (94.4%)
  - Healthy loan status:
    - Precision: 100%
    - Recall: 100%
  - High-risk loan status:
    - Precision: 87%
    - Recall: 89%

The logistic regression model trained on the original data has a 94.4% accuracy of predicting the two labels. As it relates to predicting the healthy loans (0), the model does very well, as is evidenced by an f1-score of 1.00 (100%). Conversely, the model only accurately predicted around 87% of the high-risk loans, and thus, there is evidence that the model could potentially use some improvement. The recall score for high-risk loans is 0.89, indicating that the model only identified 89% of all high-risk loans in the dataset.

**Machine Learning Model 2 - Logistic Regression Model Fitted with Resampled Training Data:**

- Balanced Accuracy Score: 0.9959744975744975 (99.6%)
  - Healthy loan status:
    - Precision: 100%
    - Recall: 100%
  - High-risk loan status:
    - Precision: 87%
    - Recall: 100%

The logistic regression model trained on the resampled data has a 96.6% accuracy of predicting the two labels. As it relates to predicting the healthy loans (0), this model also does very well, as is evidenced by precision and recall scores of 1.00 (100%). While there is no improvement in the precision score for the high-risk loans using the resampled regression model, there is improvement in the recall score, indicating the model can now predict all high-risk loans in the dataset. 

## Summary
Overall, when comparing the results of the two machine learning models, the resampled model appears to be the model of choice due to a balanced accuracy score of 99.6% vs. the 94.4% from the original model. Additionally, there was an improvement in the recall score for the high-risk loans from 89% to 100%. Thus, to reiterate, the over-sampled/resampled model seems to be the best choice for predicting true positives, meaning it is more effective at distinguishing high-risk loans with high recall accuracy. Simultaneously, the number of false positives decreases, which reveals the model is able to more appropriately and accurately classify health and high-risk loans accordingly.

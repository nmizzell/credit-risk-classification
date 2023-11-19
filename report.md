# Module 12 Report

## Overview of the Analysis

* The purpose of this analysis is to develop a logistic regression model that is capable of classifying a loan a high risk or low risk based on a set of criteria.
* The goal is to predict whether or not a loan is high risk based on the size of the loan, the interest rate, the borrower's income, the borrower's debt to income ratio, the borrower's number of accounts, the borrower's number of derogatory marks, and the borrower's total debt.
* Our dataset is composed of 75 thousand low risk loans, and 2.5 thousand high risk loans.
* Initially, a logistic regression model was applied , taking in the aforementioned variables to predict the risk status of the loan. However, due to the underrepresentation of the high risk loans in our dataset, the analysis was repeated on an oversampled version of the dataset.
* The specific methods that were used in the model included: LogisticRegression lbfgs solver, balanced accuracy score, confusion matrix, and classification report.

## Results

* Machine Learning Model 1:
  * Precision = TP / (TP+FP)
  * Accuracy = (TN+TP) / (TN+TP+FN+FP)
  * Recall = TP / (TP+FN)
  Balanced Accuracy = 94.4%
  

              precision    recall  f1-score   support

           0       1.00      1.00      1.00     18759
           1       0.87      0.89      0.88       625

    accuracy                           0.99     19384
   macro avg       0.94      0.94      0.94     19384
weighted avg       0.99      0.99      0.99     19384


* Machine Learning Model 2:
  Balanced Accuracy = 99.5%
                precision    recall  f1-score   support

           0       1.00      0.99      1.00     18905
           1       0.99      1.00      0.99     18613

    accuracy                           1.00     37518
   macro avg       1.00      1.00      1.00     37518
weighted avg       1.00      1.00      1.00     37518


## Summary

* The resampled model (model #2) has a better weighted average score and higher scores for accuracy, and precision (not recall), so it is more suitable for use than the non resampled model.
* It is important that the model correctly classifies both low and high risk loans. However, in the case where the model incorrecly classifies a loan, it is less risky to classify a true low risk loan as a high risk loan, since we will not face any true business risk, and will likely act in a more conservative manner than is required. In the case that the model classifies a high risk loan as a low risk loan, we face the risk of having the customer default without us anticipating it.


# 12_Credit_Risk_Analysis

---

## Overview of the Analysis

---

Purpose of analysis: the purpose of this is to build a model that can identify creditworthiness of borrowers by using logistic regression model to compare two versions of the datatset: original and oversampled dataset.

The dataset included the following variables of the borrowers and using machine learning, we wanted to assign a loan status of either 1 (high-risk loan) or a 0 (healthy loan) to each borrower: loan size, loan rate, borrower's income, debt to income, number of accounts, derogatory marks, and total debt

When preparing both datasets, we checked variables such as `value_counts` to see the balance of the labels in each category. Since there was an imbalance of 1 and 0 in the original dataset, we resampled the data and used the `RandomOverSampler` module to randomly select instances of the minority class (i.e., 1) and add them to the training set until we've balanced the majority and minority classes.

Before this step, we split the data into training and testing datasets by using `train_test_split` so we can train the logistic regression models with the triaing data and then evaluate the models with the testing data. This allows us to make unbiased evaluations of the models.

Then, we fit the models with training data so they can learn and mathematically adjust themselves to best represent this data so they can ultimately make predictions by using the testing data. This will allow us a better sense of how well the models will perform with new data.

---

## Results

---

Below are a summary of the results of both models:

- Machine Learning Model 1: original dataset

  - Description of Model 1 Accuracy score: 0.9918. This means that approximately 99.18% of the transactions in the test data were accurately categorized by the model.
  - The precision for the 0 values (healthy loan) is 1.00. This means that out of all the times that the model predicted a testing data observation to be the value 0, 100% of those predictions were correct. By contrast, out of all the times that the model predicted a value of 1 (high-risk loan), only 85% of those predictions were correct. The model is much better at predicting healthy loans than high-risk loans
  - The recall value is 0.91

- Machine Learning Model 2: random oversampled dataset
  - Description of Model 2 Accuracy score: 0.9937. This means that approximately 99.37% of the transactions in the test data were accurately categorized by the model.
  - The precision for the 0 values (healthy loan) is 1.00. This means that out of all the times that the model predicted a testing data observation to be the value 0, 100% of those predictions were correct. By contrast, out of all the times that the model predicted a value of 1 (high-risk loan), only 84% (slightlyt worse) of those predictions were correct.
  - The recall value is 0.99

---

## Summary

---

Both models are recommended for predicting people with healthy loans but the second model is better at identifying high-risk borrowers. Therefore, the second model is recommended to for use when flagging people that may pose a high-risk when applying for loans as healthy loans easily outnumber risky loans so it is important to identify the latter. Even though the second model had a slightly lower precision, it was able to identify more risky loans.

# credit-risk-classification-challenge
## Module 20: Supervised Machine Learning

In this challenge, various techniques to train and evaluate a model based on loan risk were utilized. There was a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

# Part 1: Split the Data into Training and Testing Sets
- Open the starter code notebook and use it to complete the following steps:
  - Read the lending_data.csv data from the Resources folder into a Pandas DataFrame.
  - Create the labels set (y) from the “loan_status” column, and then create the features (X) DataFrame from the remaining columns.
  - Split the data into training and testing datasets by using train_test_split.

# Part 2: Create a Logistic Regression Model with the Original Data
- Use your knowledge of logistic regression to complete the following steps:
  - Fit a logistic regression model by using the training data (X_train and y_train).
  - Save the predictions for the testing data labels by using the testing feature data (X_test) and the fitted model.
  - Evaluate the model’s performance by doing the following:
  - Generate a confusion matrix.
  - Print the classification report.
  - Answer the following question: How well does the logistic regression model predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

# Part 3: Write a Credit Risk Analysis Report
- Write a brief report that includes a summary and analysis of the performance of the machine learning models that you used in this homework.
- You should write this report as the README.md file included in your GitHub repository.
    - Structure your report by using the report template that Starter_Code.zip includes, ensuring that it contains the following:
        - An overview of the analysis: Explain the purpose of this analysis.
        - The results: Using a bulleted list, describe the accuracy score, the precision score, and recall score of the machine learning model.
        - A summary: Summarize the results from the machine learning model. Include your justification for recommending the model for use by the company. If you don’t              recommend the model, justify your reasoning.

# Analysis Report: 
The dataset (77,536 data points) was split into training and testing sets. The training set was used to build an initial logistic regression model (Logistic Regression Model 1) using the LogisticRegression module from scikit-learn. Logistic Regression Model 1 was then applied to the testing dataset. The purpose of the model was to determine whether a loan to the borrower in the testing set would be low or high-risk. The results are summarized below.

This intial model was drawing from a dataset that had 75,036 low-risk loan data points and 2,500 high-risk data points. To resample the training data and ensure that the logistic regression model had an equal number of data points to draw from, the training set data was resampled with the RandomOverSampler module from imbalanced-learn. This generated 56,277 data points for both low-risk (0) and high-risk (1) loans, based on the original dataset.

The resampled data was used to build a new logistic regression model (Logistic Regression Model 2). The purpose of Logistic Regression Model 2 was to determine whether a loan to the borrower in the testing set would be low- or high-risk. The results are summarized below.

# Results:
## Logistic Regression Model 1:
- Precision: 93% (an average--in predicting low-risk loans, the model was 100% precise, though the model was only 87% precise in predicting high-risk loans)
- Accuracy: 94%
- Recall: 95% (an average--the model had 100% recall in predicting low-risk loans, but 89% recall in predicting high-risk loans)

## Logistic Regression Model 2:
- Precision: 93% (an average--in predicting low-risk loans, the model was 100% precise, though the model was only 87% precise in predicting high-risk loans)
- Accuracy: 100%
- Recall: 100%

# Summary: 
The Logistic Regression Model 2 is less likely to predict false negative results. However, based on the confusion matrices for each model, Logistic Regression Model 2 predicted slightly more false positives (low-risk when the actual was high-risk).

If the goal of the model is to determine the likelihood of high-risk loans, neither model scores are above a 90% precision. Logistic Regression Model 2 had fewer false predictions of the testing data overall and would be the best model to use based on the high accuracy and recall of this model.

# Resources: 
1. Modules 19: In Class Activities
2. Class Instructor: Arooj A Qureshi
3. TA Instructor: Abdelrahman "Abdo" Elewah









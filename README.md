# Logistic-Regression-car-insurance-claims
![image](https://github.com/rutuja-jadhav-github/Logistic-Regression-car-insurance-claims/assets/160432263/4f3c71e0-bc43-4cf2-b813-e3076999a56f)

## Context
Used a practice dataset and problem statement from Data Camp. Determined the accuracy and recall for the fitted values of a logistic regression model for car insurance claims to recommend the best predictor of insuarance claims.

## Problem Statement
Data Camp: Insurance companies invest a lot of time and money into optimizing their pricing and accurately estimating the likelihood that customers will make a claim. 

'On the Road' car insurance have requested your services in building a model to predict whether a customer will make a claim on their insurance during the policy period. As they have very little expertise and infrastructure for deploying and monitoring machine learning models, they've asked you to identify the single feature that results in the best performing model, as measured by accuracy, so they can start with a simple model in production.

They have supplied you with their customer data as a csv file called car_insurance.csv, along with a table detailing the column names and descriptions.

Note: Please Refer to the Notebook CarInsuranceLR.ipynb to view the above table.

## Approach
1. Data Exploration and manipulation - This was a relatively neat data set. There were only two columns with missing values. I ran a histrogram to see if the spread was Normally distributed. Both cols had a normal dist, so replaced missing values with mean.</br>
2. Modelling Approach - Since the problem statement specifies that the company has just enough budget to create a model based on one feature only, we can create a model for every feature and report the best performing model.
•First, I separated the titles of all feature columns.</br>
•Then I passed these titles individually in a for loop to create a model for each feature using the logit algorithm.</br>
•Each model object created was appended to a list of all models.</br>
3. Model/ Feature Evaluation - Recall Vs Precision - Opted for Recall instead of Precision. As an insuarance provider it would make sense for the company to focus on reducing type II error, ie, reducing False Negatives. When we aim to reduce false negatives, we shoul focus on higher Recall. It is imp that the company is able to reduce number of false negatives because, you'd rather have the model tell us someone is going to make a claim but doesn't actually claim than have the model tell us that someone is NOT going to make a claim but actually files for a claim. In the later case, the company is likely to loose more money than it would expect to. Recall helps us increase the number of True Positives wrt Actual Positives (Positive = Made a claim)</br>

## Conclusion
Based on the output of metrics for all the features, if the insuarance company had enough resources to predict the outcome of future applications using just ONE feature, they should go for Driving_experience based on the recall (0.707). Experience is also the feature with the highest accuracy(0.777).

## Requirements
statsmodels==0.14.2
matplotlib==3.9.0
pandas==2.2.2




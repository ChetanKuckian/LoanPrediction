# LoanPrediction

### The dataset is a part of analytics vidhya hackathon and can be downloaded from:https://datahack.analyticsvidhya.com/contest/practice-problem-loan-prediction-iii/

- The training dataset consists of 614 rows and 13 columns, the LOAN_ID being the unique identifier columns. The Loan_Status column is the output column which gives the status whether the loan is approved or not. There are 5 categorical and 6 numerical columns.
- I created 2 sklearn pipelines which had 2 different encodings for categorical columns One Hot Encoding and Ordinal Encoding and MinMax Scaling for numerical data.
- To handle the missing values in numerical columns an IterativeImputer is used.
- To handle the missing values in categorical data a SimpleImputer which replaces the null values with the most frequent value in that column is used.
- The first model is created using an XGBoost Classifier with 100 n_estimators  as a base_estimator for the Bagging Classifier. The pipeline containing ordinal encoding for categorical column was used. The model gave an f1 score of 0.89 for 'Y' class and 0.64 for 'N' class.
- The second model is also created using an XGBoost Classifier with 100 n_estimators  as a base_estimator for the Bagging Classifier. The pipeline containing one hot encoding for categorical column was used. The model gave an f1 score of 0.89 for 'Y' class and 0.66 for 'N' class.
- Then using a VotingClassifier for combining these 2 models the output obtained was 0.90 f1-score for class 'Y'  and 0.67 f1-score for class 'N'.
- The final model gets an accuracy of 80.55 % and a rank of 114 on the leaderboard.

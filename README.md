# Fake-Instagram-Account-Detection
Project Overview
This project aims to detect fake Instagram accounts using machine learning. By leveraging various features extracted from Instagram profiles, we built a robust model that effectively differentiates between real and fake accounts. Our final model, based on the CatBoost algorithm, achieved high performance in classification tasks.

Dataset
The dataset used in this project includes the following features:

profile_pic: Binary feature indicating if an account has a profile picture (1) or not (0).
nums/length username: Continuous feature representing the ratio of numerical characters in the username to the total length of the username.
fullname words: Continuous feature representing the total number of words in the full name.
nums/length fullname: Continuous feature representing the ratio of numerical characters in the full name to the total length of the full name.
name == username: Binary feature indicating if the full name is the same as the username (1) or not (0).
description length: Continuous feature representing the length of the profile description (bio).
external URL: Binary feature indicating if the profile has an external URL in its bio (1) or not (0).
private: Binary feature indicating if the profile is private (1) or public (0).
#posts: Continuous feature representing the total number of posts made by the profile.
#followers: Continuous feature representing the total number of followers of the profile.
#follows: Continuous feature representing the total number of accounts the profile follows.
fake: Target variable, a binary feature indicating if the account is fake (1) or real (0).
Feature Engineering
We created two additional features during the feature engineering process:

Activity Ratio: Continuous feature calculated as the number of posts divided by the number of followers.
#Followers > #Follows?: Binary feature indicating if the number of followers is greater than the number of accounts followed (1) or not (0).
Data Preprocessing
The following preprocessing steps were performed on the dataset:

Checking for missing values: Ensured there were no missing values.
Handling duplicates: Removed duplicate rows to prevent bias and overfitting.
Feature scaling: Applied standard scaling to features with a large range of values to normalize the dataset.
Model Development
Baseline Model
We started with a baseline model using a Random Forest Classifier (RFC) to establish a benchmark. This helped us understand the importance of different features and guided our feature engineering process.

Final Model
After testing various gradient boosting algorithms, we selected the CatBoost model for its superior performance. The CatBoost model achieved an AUC-ROC score of 0.9214 on the test set, correctly identifying 89% of fake accounts.

Model Evaluation
The final model's performance was evaluated using several metrics:

AUC-ROC Score: 0.9214
Confusion Matrix: Showed 6 false negatives and 3 false positives.
Recall Score: The model correctly flagged 89% of fake accounts.
Conclusion
Our project successfully identified patterns differentiating fake Instagram accounts from real ones. The CatBoost model proved to be highly effective in detecting fake accounts, with new features like the activity ratio and the followers-follows ratio significantly enhancing its predictive power.

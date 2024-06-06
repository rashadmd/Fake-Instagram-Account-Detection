# Fake Instagram Account Detection

## Project Overview

This project aims to detect fake Instagram accounts using machine learning. The dataset contains various features extracted from Instagram profiles, and the target variable indicates whether an account is fake or not. We have developed and evaluated several machine learning models, and our final model is based on the CatBoost algorithm.

## Dataset

The dataset used in this project consists of Instagram profile data with the following features:

- **profile_pic:** A binary feature indicating whether an account has a profile picture (1) or not (0).
- **nums/length username:** A continuous feature representing the ratio of numerical characters in the username to the total length of the username.
- **fullname words:** A continuous feature representing the total number of words in the full name.
- **nums/length fullname:** A continuous feature representing the ratio of numerical characters in the full name to the total length of the full name.
- **name == username:** A binary feature indicating whether the full name is the same as the username (1) or not (0).
- **description length:** A continuous feature representing the length of the profile description (bio).
- **external URL:** A binary feature indicating whether the profile has an external URL in its bio (1) or not (0).
- **private:** A binary feature indicating whether the profile is private (1) or public (0).
- **#posts:** A continuous feature representing the total number of posts made by the profile.
- **#followers:** A continuous feature representing the total number of followers of the profile.
- **#follows:** A continuous feature representing the total number of accounts the profile follows.
- **fake:** The target variable, a binary feature indicating whether the account is fake (1) or real (0).

Additionally, we created two new features during the feature engineering process:

- **Activity Ratio:** A continuous feature calculated as the number of posts divided by the number of followers.
- **#Followers > #Follows?:** A binary feature indicating whether the number of followers is greater than the number of accounts followed (1) or not (0).

## Data Preprocessing

Before training the model, we performed several data preprocessing steps:

1. **Checking for missing values:** We ensured there were no missing values in the dataset.
2. **Handling duplicates:** We removed duplicate rows to prevent bias and overfitting.
3. **Feature scaling:** We applied standard scaling to features with a large range of values to normalize the dataset.

## Model Development

### Baseline Model

We started with a baseline model using a Random Forest Classifier (RFC) to establish a benchmark. This helped us understand the importance of different features and guided our feature engineering process.

### Feature Engineering

We created two additional features that showed significant impact on the model's performance:

- **Activity Ratio:** Accounts with a higher number of posts relative to their followers tend to be real accounts.
- **#Followers > #Follows?:** Fake accounts often follow more people than the number of followers they have.

### Final Model

After testing various gradient boosting algorithms, we selected the CatBoost model for its superior performance. The CatBoost model achieved an AUC-ROC score of 0.9214 on the test set, correctly identifying 89% of fake accounts.

## Model Evaluation

The final model's performance was evaluated using several metrics:

- **AUC-ROC Score:** 0.9214
- **Confusion Matrix:** Showed 6 false negatives and 3 false positives.
- **Recall Score:** The model correctly flagged 89% of fake accounts.

## Conclusion

Our project successfully identified patterns differentiating fake Instagram accounts from real ones. The CatBoost model proved to be highly effective in detecting fake accounts, with new features like the activity ratio and the followers-follows ratio significantly enhancing its predictive power.

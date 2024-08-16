# Data driven insight into Bank Marketing using different classifiers
Comparing performance of different classifier models to predict if the client will subscribe a bank term deposit after the campaign.
Jupiter notebook with code, experimentation, implementation is located [here](https://github.com/mimibhatt/Classifier-Comparison/blob/main/Practical_Application_3_Final.ipynb)

# Business Goals
Banks conduct several marketing campaigns to get customers to sign up for various bank programs. The goal of this analysis is to predict which customers will subsribe to the bank term deposit after the campaign, based on various financial, campaign related and other demographic features.

# Data
The dataset is obtained from https://archive.ics.uci.edu/ml/datasets/bank+marketing. The data set used is 10% random sampling of the original dataset so as to test more computationally demanding machine learning algorithms (e.g., SVM). The data set contains 20 independent variables both numeric and categorical and the target variable is 'Y' - which means the customer subscribed to the bank term deposit as a result of the campaign.

![target_distribution](https://github.com/user-attachments/assets/1baada92-13e0-4f18-a3cd-54b82c54277d)

# Modeling and Performance
In this project, I have used classifier modeling techniques to predict if the client will subscribe to a bank term after the campaign. The models used are:  Logistic Regression, K Nearest Neighbors, Decision Tree and SVM on the given data set- first with the unbalanced data, and next with the balanced data - as the target variable is quite unbalanced.

<img width="548" alt="Screenshot 2024-08-15 195327" src="https://github.com/user-attachments/assets/4133701b-f94b-4d21-8df1-1a6b032772ae">

[results.xlsx](https://github.com/user-attachments/files/16632361/results.xlsx)
As you can see from the chart, Logistic Regression with L1 regularization performed the best.

# Conclusion
On initial analysis, correlation matrix revealed:
1. **duration** (0.42): Highest positive correlation with the target, indicates that longer durations are associated with a higher probability of the target outcome.
2. **pdays** (-0.33): This feature has a moderate negative correlation with the target, indicating that fewer days since the client was last contacted are associated with a higher probability of the target outcome.
3. **previous** (0.26): This feature has a moderate positive correlation with the target, indicating that clients contacted in previous campaigns are more likely to result in the target outcome.

From the modeling perspective:
Since we are trying to predict how many customers signed up for the bank term after the campaign, it is important we get the correct 'true positive' and reduce false positive - which means we should go for the model that gives a high 'recall' value. **Logistic Regression** with L1 regularization had the highest recall, but **KNN and SVM** on balanced data also gave a high recall.

# Actionable Insights
1. Focusing on longer duration of call may lead to higher outcome
2. Also reducing the gap when the client was last contacted may lead to a higher outcome
3. Clients who were contacted in the previous campaign have more likelyhood to sign up hence should be contacted again
4. Some of the important features as per the models is Housing - yes, Marital - single, day_of_the_Week_thu, should be taken into consideration during the campaign for a more positive outcome


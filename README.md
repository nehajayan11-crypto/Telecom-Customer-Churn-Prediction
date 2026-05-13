# Telecom-Customer-Churn-Prediction
Developed an AI-powered Customer Churn Intelligence System that can accurately predict customers who are likely to churn. By leveraging predictive analytics, the solution will help telecom companies proactively identify at-risk customers, improve retention strategies, reduce revenue leakage, and enhance long-term customer relationships.

# Business Context
The telecom industry is highly competitive, with customers frequently switching providers due to poor service quality, high monthly charges, limited contract benefits, attractive competitor offers, and ineffective customer support. Since acquiring new customers is far more expensive than retaining existing ones, customer churn has become a critical business challenge.
Many telecom companies struggle to identify which customers are likely to leave, understand the reasons behind churn, and implement effective retention strategies. This leads to revenue loss, higher customer acquisition costs, reduced customer lifetime value, and unstable recurring revenue streams.

# Business Objective
Developing an AI-powered Customer Churn Intelligence System that can accurately predict customers who are likely to churn. The system will analyze key customer attributes such as:
•	Tenure 
•	Contract type 
•	Payment method 
•	Monthly charges 
•	Total charges 

# Result Outcome/ Analytics Outcome
In this system I tried to solve analytical questions as follows:
1. Which customers are most likely to churn?
Example:
•	Month-to-month customers 
•	High monthly bill customers 
•	Short-tenure users
2. Which payment methods have highest churn?
Example:
•	Electronic check users often show higher churn patterns.
3. How does contract type impact retention?
Example:
•	Long-term contracts improve customer loyalty.
4. Does tenure impact churn risk?
Example:
•	New customers churn more frequently compared to long-tenure users.

Through Feature Engineering & Machine Learning Models, I was able to analyse and predict whether i customer will churn or not but upon analysing the accuracy of the models prediction I can conclude that the dataset failed to produce the desired percentage within 75%-85%. 

# Model Comparison:
                 Model  Accuracy
0  Logistic Regression     0.733
2              XGBoost     0.730
1        Random Forest     0.703

To understand in its inaccuracy further investigation was conducted through classification report, confusion matrix, feature importance of XGBoost model. By finding the outcomes from these methods I can conclude that  

XGBoost model performs poorly in identifying churn customers (Class 1), despite achieving an overall accuracy of 73%.

# Key Issues Identified
# 1. Severe Class Imbalance

The confusion matrix shows:

Non-churn customers (0): 1466 samples
Churn customers (1): 534 samples

The model correctly predicted:

1455 non-churn customers
Only 5 churn customers

This means the model is heavily biased toward predicting the majority class (non-churn).

# 2. Extremely Low Recall for Churn Class

From the classification report:

- Recall for churn class = 0.01
- F1-score for churn class = 0.02

This indicates the model fails to detect actual churners. Out of 534 churn customers, only 5 were correctly identified, while 529 churners were missed.

This is critical because the business objective is to identify customers likely to leave.

# 3. Misleading Accuracy

Although accuracy is 73%, it is misleading because the dataset is imbalanced.

The model achieves high accuracy simply by predicting most customers as “non-churn.”

In churn prediction, recall and F1-score for the churn class are more important than overall accuracy.

# 4. Weak Feature Relationships

The correlation values show very weak relationships between features and churn:

- Tenure = 0.0089
- MonthlyCharges = 0.0035
- Contract = 0.0031
- PaymentMethod = -0.0051

These near-zero correlations suggest:

Important behavioral features may be missing
Existing variables may not strongly explain churn behavior.

# 5. Feature Engineering Limitations

Some engineered features such as:

- high_monthly_charge
- long_term_contract
- customer_lifetime_value

show little or negative impact, meaning they are not contributing effectively to prediction quality.

 


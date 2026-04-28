# Fraud Detection & Transaction Risk Analytics

## Overview

This project focuses on detecting anomalous and suspicious financial transaction behavior that may indicate fraud, misuse, or weak internal control weaknesses. The goal was to help OOF identify high-risk accounts, devices, locations, merchants, and transaction patterns during ongoing funding cuts.

The project combines Python, machine learning, exploratory data analysis, feature engineering, and Tableau visualization to extract meaningful insights from financial transaction data and support stronger monitoring recommendations.

## Project Objective

The main objective of this project is to identify abnormal transaction activity by analyzing patterns such as transaction frequency, transaction amount, login attempts, device usage, account behavior, transaction timing, and transaction channels.

## Tools and Technologies

- Python
- Google Colab
- pandas
- NumPy
- scikit-learn
- Matplotlib
- Seaborn
- Tableau
- Isolation Forest
- Logistic Regression

## Methodology

The project followed this analytics pipeline:

1. Data inspection and summary statistics
2. Correlation matrix analysis
3. Feature engineering
4. Feature scaling
5. Anomaly detection using Isolation Forest
6. Correlation analysis with fraud labels
7. Logistic Regression modeling
8. Threshold tuning
9. Model evaluation
10. Tableau dashboard and final recommendations

## Feature Engineering

Several new features were created to better detect suspicious behavior:

- `Account_Transaction_Count`: Number of transactions per account
- `Account_Avg_Amount`: Average transaction amount per account
- `Amount_to_Balance`: Transaction amount compared to account balance
- `Hour`: Hour of transaction
- `Weekday`: Day of transaction
- `IsWeekend`: Weekend transaction indicator
- `Accounts_per_Device`: Number of unique accounts connected to the same device

These features helped identify unusual transaction patterns, high-risk devices, and abnormal account behavior.

## Anomaly Detection

An Isolation Forest model was used to detect suspicious transactions.

The model classified transactions as:

- `0` = Normal transaction
- `1` = Suspicious or potential fraud transaction

Isolation Forest was selected because it works well for detecting rare abnormal activity when confirmed fraud labels are not available.

## Predictive Modeling

After creating suspicious transaction labels, a Logistic Regression model was used to predict fraud risk probability. The model included standardized numerical features, train-test splitting, stratified cross-validation, and classification performance metrics.

The project compared different probability thresholds, including:

- 0.3
- 0.4
- 0.5
- 0.6
- 0.7
- 0.8

A threshold of `0.3` was selected because fraud detection should prioritize catching suspicious activity, even if that creates some false alarms.

## Visualizations

The project included several visualizations:

- Correlation matrix
- Accounts per device distribution
- Normal vs suspicious transaction count
- Feature correlation with detected fraud
- Precision, recall, and F1-score by threshold
- Fraud probability distribution
- Tableau dashboard for financial risk insights

## Key Insights

The analysis showed that suspicious transaction behavior can be detected by monitoring account activity, device usage, login attempts, transaction amount patterns, and transaction frequency.

Important risk indicators included:

- Multiple accounts connected to the same device
- Unusual transaction frequency
- Abnormal transaction amount relative to account balance
- High login attempts
- Suspicious timing or channel patterns

## Recommendations

Based on the analysis, OOF should:

1. Monitor devices connected to multiple accounts.
2. Flag accounts with unusually high transaction frequency.
3. Review transactions with abnormal transaction-to-balance ratios.
4. Increase monitoring for accounts with repeated login attempts.
5. Create risk scores for accounts, devices, merchants, and channels.
6. Use Tableau dashboards to prioritize suspicious activity.
7. Apply lower fraud probability thresholds when recall is more important than precision.

## Team Collaboration

Our group worked together by dividing tasks across data analysis, Python modeling, Tableau visualization, presentation design, and final recommendations. Each team member contributed different strengths, including coding, dashboard design, financial reasoning, communication, and presentation organization.

## Limitations

This project was completed for hackathon and educational purposes. The suspicious transaction labels were generated using anomaly detection rather than confirmed fraud labels, so the results should be interpreted as risk signals rather than confirmed fraud cases.

## Future Improvements

Future improvements could include:

- Using confirmed fraud labels
- Adding merchant-level risk scores
- Adding location-based fraud detection
- Testing Random Forest or XGBoost models
- Adding SHAP explainability
- Building a real-time fraud alert dashboard
- Improving threshold selection using business cost analysis

## Suggested Resume Bullet

Built a fraud detection and transaction risk analytics system using Python, Isolation Forest, Logistic Regression, and Tableau to identify suspicious accounts, devices, and transaction patterns, producing data-driven recommendations to strengthen financial monitoring controls.

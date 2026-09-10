# Bank Marketing Subscription Prediction

## Overview

This project develops a machine learning classification model to predict whether a bank client is likely to subscribe to a term deposit.

The project follows an end-to-end machine learning workflow, from data preparation and exploratory analysis to model training, evaluation, threshold optimization, and business visualization.

---

## Business Problem

Banks conduct marketing campaigns to reach potential customers.

The goal of this project is to build a model that can help identify customers who are more likely to subscribe to a term deposit, allowing marketing teams to prioritize potential customers.

---

## Machine Learning Task

This is a binary classification problem.

**Target variable:** `y`

- `yes` → Customer subscribed
- `no` → Customer did not subscribe

---

## Dataset

The project uses the Bank Marketing dataset from the UCI Machine Learning Repository.

- 45,211 instances
- 16 input features
- 1 binary target
- Binary classification task

The raw dataset is not included in this repository.

Dataset source:

https://archive.ics.uci.edu/dataset/222/bank+marketing

---

## Data Preparation

The preprocessing workflow includes:

- Separating features and target
- Train-test split
- Numerical feature scaling
- Categorical feature encoding
- Handling unseen categorical values
- Class imbalance consideration

The `duration` feature was excluded from the primary model because it represents the duration of the current call and would not be available before the interaction.

---

## Models

Two classification models were evaluated:

### Logistic Regression

- Accuracy: 75.48%
- Precision: 26.62%
- Recall: 62.38%
- F1-score: 37.32%
- ROC-AUC: 77.22%

### Random Forest

- Accuracy: 85.77%
- Precision: 41.41%
- Recall: 52.17%
- F1-score: 46.17%
- ROC-AUC: 79.27%

The Random Forest model was selected as the main model.

---

## Threshold Optimization

The default classification threshold of 0.50 was adjusted to 0.40 to obtain a different precision-recall trade-off.

### Final Random Forest Results

- Decision Threshold: 0.40
- Precision: 41.41%
- Recall: 52.17%
- F1-score: 46.17%
- ROC-AUC: 79.27%

### Confusion Matrix

- True Negative: 7,204
- False Positive: 781
- False Negative: 506
- True Positive: 552

---

## Feature Importance

The most influential features identified by the Random Forest model included:

1. Balance
2. Age
3. Day
4. Campaign
5. Pdays
6. Previous campaign outcome
7. Contact type
8. Previous contacts
9. Housing status
10. Education/job-related features

Feature importance describes how much the model relied on features during prediction. It does not imply causation.

---

## Power BI Dashboard

A Power BI dashboard was created to present the machine learning results from a business perspective.

The dashboard includes:

- Key performance indicators
- Subscription rates by customer characteristics
- Prediction segments
- Prediction outcomes
- Confusion matrix
- Random Forest feature importance
- Interactive filters

![Power BI Dashboard](reports/figures/powerbi_dashboard.png)

---

## Project Structure

```text
bank-marketing-subscription-prediction/
├── notebooks/
├── models/
├── powerbi/
├── reports/
├── README.md
├── requirements.txt
└── .gitignore

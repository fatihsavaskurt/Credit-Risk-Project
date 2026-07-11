# Credit Default Risk Prediction

## Overview

This project presents an end-to-end machine learning pipeline for predicting customer credit default risk using the **Give Me Some Credit** dataset from Kaggle.

The objective is to identify customers who are likely to default within the next two years by comparing multiple machine learning algorithms and selecting the best-performing model based on evaluation metrics suitable for imbalanced classification problems.

---

## Business Problem

Financial institutions face significant losses due to customer defaults. Identifying high-risk customers before approving credit applications helps reduce financial losses and improves risk management.

This project aims to develop a predictive model that supports credit risk assessment by estimating the probability of customer default.

---

## Dataset

- **Source:** Kaggle – Give Me Some Credit
- **Problem Type:** Binary Classification
- **Target Variable:** `SeriousDlqin2yrs`

### Features

The dataset contains customer financial and credit-related information, including:

- Revolving credit utilization
- Age
- Monthly income
- Debt ratio
- Number of open credit lines
- Delinquency history
- Number of real estate loans
- Number of dependents

---

## Project Workflow

The project follows a complete machine learning workflow:

1. Exploratory Data Analysis (EDA)
2. Missing Value Analysis
3. Feature Engineering
4. Data Preprocessing
5. Baseline Model Development
6. Hyperparameter Optimization
7. Model Comparison
8. Final Model Selection
9. Kaggle Submission

---

## Feature Engineering

Several preprocessing techniques were applied before model training:

- Missing values were imputed using the median.
- Special delinquency values (`96` and `98`) were treated as missing values.
- Indicator variables (`is_special`) were created to preserve the information carried by these special values.
- Model performance was evaluated using metrics designed for imbalanced datasets rather than relying solely on accuracy.

---

## Models Evaluated

The following machine learning algorithms were trained and compared:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Random Forest
- XGBoost

Hyperparameter tuning was performed using **GridSearchCV**.

---

## Model Performance

| Model | ROC-AUC | PR-AUC |
|----------------------|:------:|:------:|
| Logistic Regression | 0.83 | 0.36 |
| KNN | 0.79 | 0.30 |
| Random Forest | 0.87 | 0.41 |
| XGBoost | 0.87 | 0.41 |

Both Random Forest and XGBoost achieved the strongest overall performance. The final XGBoost model was selected due to its strong discriminative ability while maintaining competitive precision-recall performance.

---

## Kaggle Results

| Metric | Score |
|---------|------:|
| Public Leaderboard | **0.8610** |
| Private Leaderboard | **0.8674** |

---

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- XGBoost
- Jupyter Notebook
- 
---

## Future Improvements

Possible future improvements include:

- SHAP-based model explainability
- Ensemble learning approaches
- Automated preprocessing pipeline
- Streamlit deployment
- Probability threshold optimization for different business objectives

---

## Results

The project demonstrates a complete machine learning workflow, from data exploration and feature engineering to model selection and Kaggle evaluation.

The final XGBoost model achieved a **Private ROC-AUC score of 0.8674**, showing strong predictive performance for credit default risk estimation.

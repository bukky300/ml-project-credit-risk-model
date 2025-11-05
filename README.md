# Credit Risk Modeling System

A machine learning system that predicts loan default probability and generates an interpretable credit score and rating.
Built with Python, scikit-learn, XGBoost, pandas, and Streamlit.

🧠 Objective

The goal of this project is to assess credit risk by estimating the probability of default (target: default) and assigning a credit score (300–900) based on applicant data.
The model helps financial institutions evaluate lending risk and improve decision-making.

## ⚙️ Data Features
#### Continuous Variables

['age', 'income', 'number_of_dependants', 'years_at_current_address', 'sanction_amount', 'loan_amount', 'processing_fee', 'gst', 'net_disbursement', 'loan_tenure_months', 'principal_outstanding', 'bank_balance_at_application', 'number_of_open_accounts', 'number_of_closed_accounts', 'total_loan_months', 'delinquent_months', 'total_dpd', 'enquiry_count', 'credit_utilization_ratio']

#### Categorical Variables

['gender', 'marital_status', 'employment_status', 'residence_type', 'city', 'state', 'zipcode', 'loan_purpose', 'loan_type', 'default']

The default variable represents whether the borrower failed to meet repayment obligations and serves as the target variable.

## 🔍 Feature Engineering

Created derived features:

Loan-to-Income Ratio

Delinquency Ratio = delinquent_months / total_loan_months

Handled multicollinearity using Variance Inflation Factor (VIF) analysis.

Encoded categorical variables using Weight of Evidence (WoE).

Assessed variable strength with Information Value (IV) to select the most predictive features.

## 🤖 Modeling Approach

Trained multiple models:

Logistic Regression

Random Forest

XGBoost

Best model: Logistic Regression (chosen for interpretability and consistency).

Hyperparameter optimization with Optuna and RandomizedSearchCV.

#### 📈 Model Evaluation
Metric	Score
AUC	0.9837
Gini Coefficient	0.9673
KS Statistic	85%
#### 🎯 Credit Scoring Logic

Credit score = 300 + (1 - default_probability) * 600

Score Range	Rating
300–499	Poor
500–649	Average
650–749	Good
750–900	Excellent

#### 💳 Credit Scoring Logic

After predicting the probability of default, the system converts it into a credit score (300–900) and assigns a rating:

Score Range	Rating
300–499	Poor
500–649	Average
650–749	Good
750–900	Excellent
## 🖥️ Web Interface

An interactive Streamlit dashboard lets users:

Input or upload applicant data

Generate credit scores and risk ratings in real time

Visualize default probabilities and model insights

📊 Feature Importance

A visualization of key features contributing to the final model.


<img width="836" height="392" alt="image" src="https://github.com/user-attachments/assets/504cc881-e444-49c2-bffd-d0b590939a02" />


## 🧰 Tech Stack

Python

pandas, NumPy, scikit-learn, XGBoost

Optuna, RandomizedSearchCV

Matplotlib, Seaborn

Streamlit for web deployment

Joblib for model serialization


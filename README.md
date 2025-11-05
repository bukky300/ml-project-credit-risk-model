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

## 🧩 Modeling Approach

Feature Engineering:

Applied Weight of Evidence (WoE) encoding and Information Value (IV) analysis for categorical variables to assess their predictive strength and ensure monotonic relationships with default risk.

Algorithms Tested: Logistic Regression, Random Forest, XGBoost

Best Model: Logistic Regression (selected for interpretability and stability)

Hyperparameter Tuning: Conducted with Optuna and RandomizedSearchCV

Evaluation Metrics:

ROC-AUC

Gini Coefficient

KS Statistic

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

## 🧰 Tech Stack

Python

pandas, NumPy, scikit-learn, XGBoost

Optuna, RandomizedSearchCV

Matplotlib, Seaborn

Streamlit for web deployment

Joblib for model serialization

🚀 Results

Achieved strong discrimination power using ROC-AUC, Gini, and KS metrics.

Logistic Regression chosen for its balance of performance, interpretability, and consistency.

Credit scores provide transparent, business-friendly insight into borrower risk.

📂 Repository Structure
├── app/
│   ├── main.py                # Streamlit app
│   ├── prediction_helper.py   # Model inference logic
│
├── artifacts/
│   └── model_data.joblib      # Trained model
│
├── notebooks/
│   └── credit-risk-model.ipynb
│
├── dataset/
│    ├── bureau_data                
│    ├── customers.csv
     ├── loans.csv
│
└── README.md
└── requirements.txt

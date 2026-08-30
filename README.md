# 🏦 Loan Default Prediction using Logistic Regression

## 📌 Project Overview

This project focuses on predicting whether a borrower is likely to **Fully Pay** or **Default (Charged Off)** on a loan.

A **Logistic Regression** machine learning model was built using borrower and loan application information such as loan amount, interest rate, annual income, debt-to-income ratio, credit history, and other financial features.

The objective is to help lending institutions identify potential risky borrowers and make better data-driven lending decisions.

---

## 🎯 Business Problem

Loan defaults can result in significant financial losses for banks and lending institutions.

The goal of this project is to build a predictive model that estimates the probability of a borrower defaulting on a loan using information available at the time of application.

This problem is commonly known as **Credit Risk Prediction**.

---

## 📊 Dataset

* Total Records: **355,870**
* Total Features: **27**
* Target Variable: **Loan Status**

### Target Classes:

* **Fully Paid → 0**
* **Charged Off → 1**

The dataset contains information related to:

* Loan Amount
* Interest Rate
* Loan Term
* Loan Grade
* Employment Length
* Annual Income
* Home Ownership
* Verification Status
* Loan Purpose
* Debt-to-Income Ratio (DTI)
* Credit History
* Public Records
* Mortgage Accounts
* Revolving Balance

---

## 🔍 Exploratory Data Analysis (EDA)

The following analyses were performed:

* Target variable distribution
* Loan status analysis by loan term
* Loan status analysis by grade
* Home ownership analysis
* Verification status analysis
* Numerical feature comparison using boxplots
* Correlation analysis using a heatmap

---

## 🛠️ Feature Engineering

Several new features were created to improve the model:

* `term_months`
* `emp_length_num`
* `credit_history_years`
* `pub_rec_flag`
* `mort_acc_flag`
* `pub_rec_bankruptcies_flag`

The target variable was also created as:

```python
Fully Paid = 0
Charged Off = 1
```

---

## ⚠️ Data Quality & Leakage Detection

During EDA, ZIP codes extracted from the address showed suspiciously strong separation between loan outcomes.

This indicated a potential **data leakage or artificially constructed feature**.

Therefore, the `zip_code` feature was intentionally excluded from the final model.

Other preprocessing steps included:

* Missing value treatment
* Median and mode imputation
* Outlier treatment using the IQR method
* Removal of redundant features

---

## 🔄 Data Preprocessing

The following preprocessing techniques were applied:

* Handling missing values
* Outlier capping using IQR
* One-Hot Encoding for categorical variables
* Train-Test Split
* Stratified sampling
* Feature Scaling using StandardScaler

### Train-Test Split

* Training Data: **80%**
* Testing Data: **20%**
* Random State: **42**

---

## 🤖 Machine Learning Model

The project uses:

### Logistic Regression

The model was trained using Scikit-learn's Logistic Regression algorithm.

Additionally, Statsmodels was used to analyze:

* Model coefficients
* P-values
* Odds ratios
* Pseudo R-squared

---

## 📈 Model Evaluation

The model was evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix
* ROC-AUC Curve
* Precision-Recall Curve

### Model Performance

* **Train Accuracy:** ~80.59%
* **Test Accuracy:** ~80.64%
* **ROC-AUC:** ~0.71

⚠️ Accuracy alone was not considered sufficient because the dataset has class imbalance.

At the default threshold of **0.5**, recall for defaulters was relatively low.

Therefore, different classification thresholds were tested to analyze the trade-off between:

* Precision
* Recall
* F1 Score
* Percentage of loans flagged as risky

---

## 💡 Key Business Insights

* Loan **sub-grade** was one of the strongest predictors of default risk.
* Longer **60-month loans** showed higher default risk compared to shorter loans.
* Higher **interest rates** were associated with increased default risk.
* Higher **Debt-to-Income (DTI)** ratios indicated greater financial risk.
* Public records and bankruptcy-related features increased the likelihood of default.
* The default classification threshold should be selected based on business requirements rather than always using the default threshold of 0.5.

---

## 🚀 Business Recommendations

* Use the model as a **risk-ranking tool** instead of a simple approve/reject system.
* Categorize borrowers into different risk tiers.
* Adjust interest rates or lending conditions based on borrower risk.
* Optimize the classification threshold based on the cost of missed defaults versus rejecting good borrowers.
* Regularly monitor model performance.
* Add richer credit and behavioral data to improve predictive performance.

---

## 🧰 Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Statsmodels
* Google Colab

---

## 📁 Project Structure

```text
Loan-Default-Prediction/
│
├── loan_default_prediction.ipynb
├── README.md
└── logistic_regression.csv
```

---

## 👨‍💻 Author

**Rohan Jha**

Aspiring Data Analyst | Python | SQL | Statistics | Machine Learning

---

⭐ If you found this project interesting, feel free to star the repository!


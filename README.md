# 🏦 Loan Default Risk Analysis — Lending Club

> Credit risk analysis of 230,604 Lending Club loans to identify default patterns, build a predictive model, and deliver actionable lending strategy recommendations.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/saharshsaraf03/Loan-Default-Risk-Analysis/blob/main/Loan_Default_Risk_Analysis.ipynb)

---

## 📌 Project Overview

As a data analyst at a lending institution, the goal is to understand which borrower characteristics predict loan default so the firm can make better lending decisions and minimize portfolio losses.

This project analyzes real Lending Club loan data (2.26M records, sampled to 400K) and delivers a complete end-to-end analysis: data cleaning → exploratory analysis → feature engineering → predictive modeling → business recommendations.

---

## 🔑 Key Findings

| Finding | Detail |
|---------|--------|
| **Grade is the #1 predictor** | Grade A defaults at 6.2%, Grade G at 49.7% — an 8x increase |
| **Interest rate confirms risk** | Defaulted loans: median 15.05% vs 12.29% for paid loans |
| **Small business loans are riskiest** | 29.8% default rate — highest among all loan purposes |
| **DTI above 25 is a red flag** | Default rate jumps to 25-32% for high-DTI borrowers |
| **Credit utilization matters** | Maxed-out borrowers: 27.1% default vs 16.1% for low utilization |

---

## 📊 Model Performance

| Metric | Value |
|--------|-------|
| Accuracy | 80.0% |
| ROC-AUC | 0.7035 |
| Precision (Default) | 54% |
| Recall (Default) | 6% |

> **Note:** The 80% accuracy is misleading due to class imbalance (80/20 split). The AUC of 0.70 is the more honest metric — the model can meaningfully rank borrowers by risk, and a bank would use probability scores rather than binary predictions.

---

## 🎯 Business Recommendations

| Risk Zone | Grades | Default Rate | Recommendation |
|-----------|--------|-------------|----------------|
| ✅ Safe | A-B | 6-14% | Approve with standard terms |
| ⚠️ Caution | C | 23% | Require income verification |
| 🔶 Restrict | D-E | 31-39% | Require collateral, lower limits |
| 🔴 Deny | F-G | 45-50% | Interest premium unlikely to compensate |

---

## 🛠️ Tech Stack

- **Language:** Python
- **Data Manipulation:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn, Plotly
- **Machine Learning:** Scikit-learn (Logistic Regression)
- **Environment:** Google Colab

---

## 📂 Dataset

- **Source:** [Lending Club Loan Data — Kaggle](https://www.kaggle.com/datasets/adarshsng/lending-club-loan-data-csv)
- **Original Size:** 2.26M loans, 145 features
- **Analysis Sample:** 400K loans → 230,604 with clear outcomes (Fully Paid / Charged Off)
- **Features Used:** 42 (16 numeric + 4 categorical one-hot encoded)

---

## 🔍 Methodology
Raw Data (2.26M rows, 145 cols)
↓ Random sampling (400K rows)
↓ Filter for clear outcomes (230K rows)
↓ Drop high-missing & data leakage columns (145 → 68 cols)
↓ Exploratory Data Analysis (univariate + bivariate)
↓ Data cleaning (missing values, outliers)
↓ Feature engineering (7 new features → 75 cols)
↓ One-hot encoding (42 model features)
↓ Train-test split (80/20, stratified)
↓ Logistic Regression model
↓ Evaluation (AUC, confusion matrix, feature importance)
↓ Business recommendations

---

## ⚠️ Challenges Faced

1. **Massive missing data** — 111 of 145 columns had missing values, 46 columns were >40% empty
2. **Data leakage** — Identified and removed 15 post-loan columns that would have inflated model performance
3. **Class imbalance** — Only 20% defaults, causing the model to favor predicting "Fully Paid"
4. **Extreme outliers** — Income up to $9.5M, DTI values of 999 — required careful capping based on EDA
5. **Multicollinearity** — Feature pairs with 0.85-0.98 correlation required careful selection

---

## 📈 Future Improvements

- Ensemble models (Random Forest, XGBoost) for higher recall
- SMOTE or class weighting to handle imbalanced data
- Time-based train-test split for realistic deployment simulation
- External macroeconomic features (unemployment rate, GDP)
- Probability calibration for reliable risk scoring

---

## 👤 Author

**Saharsh Saraf**
- GitHub: [@saharshsaraf03](https://github.com/saharshsaraf03)

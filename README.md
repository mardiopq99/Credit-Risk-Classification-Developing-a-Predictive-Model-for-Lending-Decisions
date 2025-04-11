# 💳 CREDIT RISK CLASSIFICATION: DEVELOPING A PREDICTIVE MODEL FOR LENDING DECISIONS

## 📌 Overview
This project aims to build a **predictive machine learning model** that classifies the creditworthiness of borrowers to support better lending decisions. Using historical Lending Club data (2007–2014), we clean, analyze, and model the data to **minimize financial risk** and improve profitability through more accurate credit approvals.

---

## 🎯 Business Objective
Lending institutions want to reduce the **number of defaulted loans** and optimize the approval process by:
- **Identifying good borrowers** who can repay on time.
- **Avoiding bad loans** by reducing false positives.
- Increasing **total profit** by filtering high-risk applications more accurately.

---

## 📊 Dataset Summary
- **Rows**: 466,285
- **Initial Features**: 75
- **Target Variable**: `status_loan` (1 = Good loan, 0 = Bad loan)
- Includes borrower info, loan details, payment history, and credit behavior.

---

## 🔧 Data Preprocessing Summary

| Step | Description |
|------|-------------|
| ❌ Missing Values | Dropped 5 highly missing columns (`mths_since_last_delinq`, etc.) and imputed minor ones |
| 🔁 Duplicates | No duplicates found |
| 🧠 Feature Engineering | Added `loan_age`, `credit_history`, `days_since_last_credit_pull` |
| 🏷️ Label Encoding | `term`, `grade`, `emp_length`, `pymnt_plan`, `initial_list_status` |
| 🧩 One Hot Encoding | `home_ownership`, `verification_status`, `loan_status`, `purpose`, `addr_state` |
| ✂️ Feature Selection | Used Mutual Information (MI Scores) and dropped 5 highly correlated features |
| 🧽 Standardization | Applied to selected numerical columns only (e.g., `recoveries`, `int_rate`) |
| 📈 Final Features | 20 selected features used for modeling |

---

## 📈 Exploratory Data Analysis (EDA)

- **Grade**: Lower grade borrowers (F, G) have higher default risk.
- **Verification Status**: Verified borrowers tend to have more approved loans.
- **Term**: 36-month loans are safer than 60-month loans.
- **Purpose**: Debt consolidation is common; education/small business riskier.
- **Multicollinearity** handled through correlation and VIF analysis.

---

## 🤖 Model Building

**Models Compared:**
- Logistic Regression
- Decision Tree
- Random Forest
- **XGBoost** (Best)

**Main Metric: `Precision`**  
Chosen to **minimize false positives**, as false approval of risky borrowers leads to **greater losses** than rejecting a good borrower.

---

## ✅ Modeling Results (After Hyperparameter Tuning)

| Model              | Precision (Test) | Recall (Test) | F1 Score (Test) | Accuracy (Test) |
|-------------------|------------------|---------------|-----------------|-----------------|
| Logistic Regression | 0.99856         | 0.99856       | 0.99856         | 0.99856         |
| Decision Tree       | 0.99924         | 0.99924       | 0.99924         | 0.99924         |
| Random Forest       | 0.99940         | 0.99940       | 0.99940         | 0.99940         |
| **XGBoost**         | **0.99964**     | **0.99964**   | **0.99964**     | **0.99964**     |

📌 **XGBoost** was selected as the final model due to:
- Highest **precision**
- Robustness to **outliers**
- Strong performance on **imbalanced data**
- Efficient training time

---

## 📉 Confusion Matrix (XGBoost)
|               | Predicted: Bad | Predicted: Good |
|---------------|----------------|-----------------|
| Actual: Bad   | 11,044 (TN)    | 22 (FP)         |
| Actual: Good  | 12 (FN)        | 82,179 (TP)     |

✔️ **Interpretation**:
- Only **22 false positives** (bad loans mistakenly approved).
- Model performs extremely well in distinguishing loan quality.

---

## 💼 Business Simulation

| Scenario         | Profit |
|------------------|--------|
| Without ML       | Rp2,070,380,000 |
| With ML (XGBoost)| **Rp3,284,740,000** |

✅ Using ML increases profit by **Rp1.21 billion** while minimizing default risk.

---

## 🎓 Key Takeaways
- **XGBoost** delivers exceptional performance and is ideal for high-stakes decisions like credit approval.
- Focusing on **precision** helps **avoid false approvals**, saving money and reducing credit risk.
- ML implementation in lending decisions can boost profits by **millions**, as shown in the simulation.
- **Data Scientists** play a crucial role in bridging data and business, providing both **technical accuracy** and **strategic impact**.

---

## 📎 Resources

- [📂 Google Drive Report & Files](https://drive.google.com/drive/folders/1_uR_YipSPmBbYhCLf89GG8H16lwM9SGP?usp=sharing)
- [💻 Colab Notebook](https://colab.research.google.com/drive/1OWWQWzBc1I5vV1dB0mQ3ipCbWn29qfyk#scrollTo=wXlvBOXaQiPb)
- [🔗 LinkedIn](https://www.linkedin.com/in/mardio-edana-putra-2076b6160/)
- [💼 Portfolio Projects](https://github.com/mardiopq99)

---

## 🙌 About the Author
**Mardio Edana Putra**  
📧 mardiopq@gmail.com  
📍 Aspiring Data Analyst | Rakamin Academy Bootcamp Graduate  
🔗 [GitHub](https://github.com/mardiopq99) | [LinkedIn](https://www.linkedin.com/in/mardio-edana-putra-2076b6160/)

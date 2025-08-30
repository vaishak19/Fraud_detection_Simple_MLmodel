# Fraud_detection_Simple_MLmodel

# 💳 Fraud Detection using Machine Learning

This project is part of an assignment to build a **fraud detection model** for financial transactions.  
The dataset simulates transactions from a payment system and the goal is to identify **fraudulent transactions**.  

---

## 📂 Project Structure

- `Fraud_Detection_Assignment.ipynb` → Jupyter notebook with data preprocessing, model training, evaluation, and business insights.
- `README.md` → Project documentation (this file).

---

## 📊 Dataset

The dataset used is the **PaySim synthetic financial dataset** (fraud.csv).  
- **Size:** ~6.3M rows, 11 columns  
- **Target column:** `isFraud`  
- **Not uploaded to GitHub** due to size and licensing.  

👉 You can download the dataset from [this Google Drive link](https://drive.google.com/uc?id=1VQ-HAm0oHbv0GmDKP2iqqFNc5aI91OLn&export=download).  
Place the CSV file in the project root as `fraud.csv`.

---

## 🧹 Data Preprocessing

Steps taken before modeling:
- Dropped identifier columns: `nameOrig`, `nameDest`
- Dropped rule-based column: `isFlaggedFraud`
- Handled missing values (merchants have missing balances → filled with 0)
- One-hot encoded transaction `type`
- Checked and documented outliers and multicollinearity

---

## 🤖 Models Used

1. **Logistic Regression** (baseline, interpretable)  
   - Handles class imbalance with `class_weight='balanced'`.   

---

## 📈 Model Evaluation

Metrics used:
- **Accuracy**  
- **Precision, Recall, F1 Score**  
- **ROC AUC**  
- **PR AUC (Precision-Recall AUC)**  
- **Confusion Matrix**  


---

## 🔑 Key Findings

- Fraudulent transactions are concentrated in `TRANSFER` and `CASH_OUT`.  
- Balance inconsistencies (`oldbalanceOrg - amount ≠ newbalanceOrg`) are strong predictors of fraud.  
- Fraud transactions are typically **large transfers** with incorrect balance updates.

---

## 🛡️ Business Recommendations

- Deploy a **real-time fraud scoring system**.  
- Apply additional verification (OTP, MFA) on high-value `TRANSFER` and `CASH_OUT` transactions.  
- Monitor transaction velocity (too many transfers in a short period).  
- Continuously retrain model to adapt to new fraud patterns.  

---

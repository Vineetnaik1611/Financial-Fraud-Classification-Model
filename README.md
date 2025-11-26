
# Financial Transaction Fraud Detection System  
### Machine Learning Model for Detecting Fraudulent Transactions (6.3 Million Records)

---

## Overview

This project builds a **logistic learning–based fraud detection system** using a Kaggle dataset containing **6.3 million financial transactions**, each labeled as *fraudulent* or *legitimate*.  
The primary objective is to develop a **high-precision fraud detection model** that minimizes false alarms while still capturing a meaningful portion of real fraud cases.

Because fraud investigation teams have limited time and resources, reducing false positives is critical. This project focuses on **precision-first optimization** through hyperparameter tuning and threshold engineering.

---

## Dataset Description

**Source:**  
[Kaggle – Fraud Detection Dataset](https://www.kaggle.com/datasets/amanalisiddiqui/fraud-detection-dataset)

**Dataset Size:**  
- **6.3 million transaction records**  
- Highly imbalanced (fraud ≈ 0.13%)

**Features include:**  
- `step` — time step (simulation hour)  
- `amount` — transaction amount  
- `oldbalanceOrg` / `newbalanceOrig`  
- `oldbalanceDest` / `newbalanceDest`  
- `nameOrig` / `nameDest` — anonymized IDs  
- `isFraud` — real fraud indicator  
- `isFlaggedFraud` — rule-based system flag  

The dataset simulates **general financial transaction fraud**, such as money transfers and cash-out fraud.

---

## Project Goals

- Handle extreme class imbalance in large-scale data  
- Train and evaluate multiple ML models  
- Improve precision while keeping recall usable  
- Reduce false positives using **threshold optimization (0.999)**  
- Analyze fraud behavior across millions of transactions  
- Produce a model that is *practically deployable* in real financial systems

---

## Final Results (After Hyperparameter + Threshold Tuning)

### High-Precision Settings
- **Optimal Threshold:** `0.999`  
- **Accuracy:** `0.9989`  
- **Precision:** `0.5654`  
- **Recall:** `0.5347`  
- **F1-Score:** `0.5496`

### Before vs After Comparison
| Metric | Before Tuning | After Tuning |
|--------|---------------|--------------|
| **Precision** | 0.0226 | 0.5654 |
| **Recall** | 0.9324 | 0.5347 |
| **F1-Score** | Very Low | 0.5496 |

Precision Improvement: **+2401.8%**

---

## Interpretation of Results

- Precision jumped from **2.26% → 56.54%**, meaning the model now produces far fewer false fraud alerts.  
- Recall decreased intentionally (93% → 53%) to make the system **conservative and highly reliable**.  
- The threshold of **0.999** flags only the most confident fraud cases.  
- The tuned model is now **practically usable** in real-world environments where false positives are costly.

---


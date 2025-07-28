# 💳 Credit Card Fraud Detection Using Machine Learning

This project applies classical machine learning models to detect fraudulent credit card transactions using a publicly available dataset. 

## 📌 Objective

To identify and prevent fraudulent transactions in real-time by analyzing patterns and anomalies in transaction data. The main challenge lies in the severe class imbalance, where frauds represent only 0.17% of the data.

## 🗃️ Dataset Overview

- **Source**: Credit card transactions from European cardholders in September 2013
- **Size**: 284,807 transactions
- **Fraud Cases**: 492 (0.172%)
- **Features**: 30 total — PCA-transformed V1–V28, `Time`, `Amount`
- **Target**: `Class` (0 = non-fraud, 1 = fraud)

Due to the imbalance, model evaluation focuses on **precision**, **recall**, and **F1-score**, especially for the fraud class. Accuracy alone is not informative in this context.

## 🧠 Models Used

Five machine learning models were trained and evaluated:

| Model                  | Precision | Recall | F1 Score | Accuracy |
|------------------------|-----------|--------|----------|----------|
| Logistic Regression    | 0.83      | 0.64   | 0.72     | 99.92%   |
| K-Nearest Neighbors    | 0.92      | 0.83   | 0.87     | 99.96%   |
| Naïve Bayes            | —         | —      | —        | —        |
| Linear Discriminant Analysis (LDA) | —    | —      | —        | —        |
| Quadratic Discriminant Analysis (QDA) | — | High recall, low precision | — | — |

<img width="1345" height="343" alt="image" src="https://github.com/user-attachments/assets/3a2f36c4-790e-4527-8976-193198edbc21" />


> 🔍 *KNN delivered the best trade-off with 92% precision and 87% F1-score.*

## ⚙️ Methodology

1. **Data Splitting**: 80% train, 20% test
2. **Evaluation Metrics**: Precision, Recall, F1-score
3. **Handling Imbalance**: Careful metric selection; no resampling or weighting used in this version

## 📈 Results

- KNN (k=3) captured non-linear patterns effectively
- Logistic Regression offered a solid baseline
- QDA had high recall but lower precision, indicating false alarms
- Emphasis on model interpretability and efficiency for real-time deployment

## 🔮 Future Work

- Incorporate SMOTE or class weighting to address imbalance
- Try ensemble models like Random Forest or XGBoost
- Use SHAP for model interpretability
- Explore anomaly detection techniques

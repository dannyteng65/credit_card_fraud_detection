# Credit Card Fraud Detection with Explainable AI

**Department of Data Science, Soochow University**
**Bachelor's Senior Project (Group 14)**

## 📖 Project Overview
With the rapid growth of digital financial transactions, credit card fraud detection has become a critical issue for financial risk management. However, real-world transaction data often presents challenges such as **extreme class imbalance** and **highly abstracted features (PCA)**.

This project aims to build a fraud detection system that balances **performance** and **interpretability**. We integrated data preprocessing, SMOTE, class-weight strategies, Optuna hyperparameter optimization, and Stacking Ensemble models. Furthermore, we introduced **SHAP** and **LIME** (XAI tools) to ensure transparency in the model's decision-making process.

## 👥 Authors
* **Advisor:** Prof. Hong-Wen Cheng
* **Members:** Yu-Jou Tu, Chih-Ling Hsu, Yun-Chen Wu, Chun-Lin Teng

## 📂 Dataset
Due to the large file size, the raw dataset is not included in this repository. You can download it directly from Kaggle:
**[Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/code/janiobachmann/credit-fraud-dealing-with-imbalanced-datasets/input)**

Please place the downloaded `creditcard.csv` file into the `data/` directory:
```text
credit_card_fraud_detection/
├── data/
│   └── creditcard.csv  <-- Place file here
├── notebooks/
├── outputs/
├── README.md
└── requirements.txt
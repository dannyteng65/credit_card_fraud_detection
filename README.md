# Credit Card Fraud Detection

This project aims to detect fraudulent credit card transactions using machine learning techniques.  
The primary challenge of this task lies in the **extreme class imbalance**, where fraudulent transactions account for only a very small fraction of all observations.

The project emphasizes robust model evaluation, proper handling of imbalanced data, and model interpretability for real-world financial applications.

---

## Dataset

- **Source (Kaggle)**:  
  Credit Card Fraud Dataset  
  https://www.kaggle.com/code/janiobachmann/credit-fraud-dealing-with-imbalanced-datasets/input

- **Overview**:
  - Total transactions: 284,807  
  - Fraudulent transactions: 492 (approximately 0.17%)
  - Features:
    - `V1`–`V28`: Anonymized features obtained via PCA transformation
    - `Time`: Seconds elapsed between each transaction and the first transaction
    - `Amount`: Transaction amount
    - `Class`: Target variable (1 = fraud, 0 = non-fraud)

- **Data Notice**:
  - The original dataset is **not included** in this repository.
  - Please download `creditcard.csv` from Kaggle and place it in the `data/` directory before running the notebooks.

---

## Problem Description

Credit card fraud detection is a binary classification problem with highly imbalanced classes.  
Using accuracy alone is misleading in this scenario; therefore, this project focuses on more appropriate metrics such as **Precision, Recall, F1-score, and ROC-AUC**, along with decision threshold optimization.

---

## Methodology

### Data Preprocessing
- Stratified train / validation / test split
- Feature scaling applied only on training data to prevent data leakage
- Imbalanced data handling using:
  - SMOTE (Synthetic Minority Over-sampling Technique)
  - Class-weighted learning (depending on the model)

### Models
- Logistic Regression (baseline model)
- LightGBM
- XGBoost
- Ensemble / Stacking model (final approach)

### Threshold Optimization
- Classification threshold selected based on validation set performance
- Test set used only for final evaluation

---

## Evaluation Metrics

Due to the imbalanced nature of the dataset, the following metrics are emphasized:

- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion Matrix

---

## Results

The final ensemble model demonstrates strong performance while maintaining a balanced trade-off between false positives and false negatives.

- **Best Model**: Stacking Ensemble  
- **Optimal Threshold**: 0.65  

**Test Set Performance**:
- Precision: 0.94
- Recall: 0.85
- F1-score: 0.89
- ROC-AUC: 0.98

Evaluation figures and additional outputs can be found in the `outputs/` directory.

---

## Model Interpretability

To improve transparency and explainability, this project incorporates:

- **SHAP (SHapley Additive exPlanations)** for global and local feature importance analysis
- **LIME (Local Interpretable Model-agnostic Explanations)** for instance-level explanations

These methods help explain model predictions, which is essential for deploying machine learning systems in financial risk management.

---

## Project Structure

credit_card_fraud_detection/
├─ README.md
├─ requirements.txt
├─ notebooks/
│ ├─ data_exploration.ipynb
│ ├─ model_training.ipynb
│ └─ model_evaluation.ipynb
├─ outputs/
│ ├─ figures/
│ ├─ confusion_matrix.png
│ └─ evaluation_results.json
└─ data/
└─ (creditcard.csv not included)

## How to Run

1. Install required dependencies:pip install -r requirements.txt
2. Download the dataset from Kaggle
3. Run the Jupyter notebooks 
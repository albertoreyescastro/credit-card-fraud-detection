# Credit Card Fraud Detection

<p align="center">
  <img src="assets/images/cover.png" alt="Credit Card Fraud Detection cover" width="900">
</p>

## Overview

This repository presents a complete machine learning workflow for **credit card fraud detection** using the public Kaggle Credit Card Fraud Detection dataset.

The project focuses on a highly imbalanced binary classification problem, where fraudulent transactions are extremely rare compared with legitimate transactions. Because of this imbalance, the workflow goes beyond simple accuracy and focuses on metrics that are more meaningful for fraud detection, such as precision, recall, F1-score, ROC-AUC, Precision-Recall analysis and confusion matrices.

The project was developed as part of my MSc in **Artificial Intelligence Technology with Advanced Practice** at **Northumbria University London** and received a **Distinction mark of 85/100**.

---

## Project Links

- **Kaggle Notebook:**  
  https://www.kaggle.com/code/albertoreyescastro20/credit-card-fraud-detection-using-machine-learning

- **Dataset:**  
  https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

- **Technical Report:**  
  `reports/credit-card-fraud-detection-report.pdf`

---

## Problem Statement

Credit card fraud detection is a high-impact machine learning problem because fraudulent transactions are rare, costly and difficult to detect using simple rules.

The main challenge is the severe class imbalance. A model can achieve very high accuracy by predicting almost every transaction as legitimate, while still failing to detect most fraud cases. For this reason, the project treats fraud detection as an imbalance-aware classification problem where false negatives and false positives must both be considered.

In this context:

- **False negatives** represent fraudulent transactions that escape detection.
- **False positives** represent legitimate transactions incorrectly flagged as suspicious.

Both errors have operational consequences. Missed fraud can lead to financial loss, while excessive false positives can increase review workload, interrupt legitimate payments and reduce customer trust.

---

## Objectives

The main objectives of this project are to:

- explore the structure and quality of the dataset,
- analyse the severe class imbalance,
- examine feature distributions, outliers and correlations,
- build a leakage-controlled preprocessing workflow,
- compare multiple machine learning models,
- evaluate different imbalance-handling strategies,
- tune and assess the strongest models,
- and produce a clear technical report suitable for a professional portfolio.

---

## Dataset

This project uses the public **Credit Card Fraud Detection** dataset hosted on Kaggle:

https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The dataset contains anonymised credit card transactions made by European cardholders. The features `V1` to `V28` are anonymised numerical components, while `Time`, `Amount` and `Class` remain directly available.

The target variable is:

- `Class = 0`: legitimate transaction
- `Class = 1`: fraudulent transaction

The dataset is not included in this repository due to size and licensing considerations. Please download it directly from Kaggle before running the notebook locally.

---

## Workflow

The project follows a structured end-to-end machine learning workflow.

### 1. Exploratory Data Analysis

The exploratory analysis investigates:

- dataset shape and structure,
- missing values,
- class distribution,
- feature behaviour,
- transaction amount outliers,
- correlation patterns,
- and signs of usable predictive structure.

The analysis confirms that the dataset is clean and fully numerical, but extremely imbalanced.

### 2. Data Preprocessing

The preprocessing stage includes:

- feature-target separation,
- stratified train-test splitting,
- leakage prevention,
- feature scaling,
- and evaluation of whether outlier filtering should be retained.

Although IQR-based filtering was explored, extreme transaction amounts were not removed from the final modelling workflow because unusual values may contain useful fraud-related signal.

### 3. Imbalance Handling

Several imbalance-handling strategies were explored, including:

- random under-sampling,
- random over-sampling,
- SMOTE,
- and class-weighted learning.

The goal was not to assume that balancing automatically improves performance, but to evaluate how each strategy affects the trade-off between fraud capture and false alarms.

### 4. Model Development

The project compares several machine learning models, including:

- Logistic Regression,
- Decision Tree,
- Random Forest,
- XGBoost,
- K-Nearest Neighbours,
- and neural-network-based approaches.

The model-development process includes baseline comparison, cross-validation, hyperparameter tuning and final model selection.

### 5. Model Evaluation

The final models are evaluated using metrics suited to imbalanced classification, including:

- precision,
- recall,
- F1-score,
- ROC-AUC,
- Average Precision,
- confusion matrices,
- ROC curves,
- Precision-Recall curves,
- and threshold-based analysis.

This allows the project to evaluate performance in terms of practical fraud-detection trade-offs rather than relying on accuracy alone.

---

## Key Findings

The analysis showed that the dataset contains useful predictive structure despite its severe imbalance and anonymised features.

The strongest final models were based on tree-based ensemble methods, particularly **Random Forest** and **XGBoost**. Random Forest offered strong precision and fewer false positives, while XGBoost achieved a strong overall balance across recall, F1-score, ROC-AUC and Average Precision.

Because missed fraud is especially costly, the final recommendation favoured **XGBoost** as the preferred model configuration, supported by its strong fraud-detection performance and overall evaluation profile.

---

## Repository Structure

```text
credit-card-fraud-detection/
├── README.md
├── notebooks/
│   └── credit_card_fraud_detection.ipynb
├── reports/
│   └── credit-card-fraud-detection-report.pdf
├── assets/
│   └── images/
│       └── cover.png
├── figures/
├── requirements.txt
└── .gitignore
```

---

## How to Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/albertoreyescastro/credit-card-fraud-detection.git
cd credit-card-fraud-detection
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Download the dataset

Download the dataset from Kaggle:

https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

Then place the file locally as:

```text
data/creditcard.csv
```

The `data/` folder is intentionally not tracked by Git.

### 4. Run the notebook

Open and run:

```text
notebooks/credit_card_fraud_detection.ipynb
```

---

## Suggested Requirements

```text
numpy
pandas
matplotlib
seaborn
scikit-learn
xgboost
imbalanced-learn
jupyter
```

---

## Skills Demonstrated

This project demonstrates practical skills in:

- Python programming,
- exploratory data analysis,
- supervised machine learning,
- imbalanced classification,
- fraud detection,
- preprocessing and leakage prevention,
- model comparison,
- hyperparameter tuning,
- threshold analysis,
- technical reporting,
- and portfolio-level project documentation.

---

## Academic Context

This project was completed as part of my MSc in **Artificial Intelligence Technology with Advanced Practice** at **Northumbria University London**.

It received a **Distinction mark of 85/100** and forms part of my wider portfolio in machine learning, applied AI, data analysis and technical documentation.

---

## Why This Project Matters

Fraud detection is not only a technical classification problem. It is also a practical decision-making problem where model outputs can affect financial loss, customer trust, review workload and operational efficiency.

This project therefore focuses not only on building predictive models, but also on interpreting their performance in a realistic fraud-detection context.

---

## Author

**Alberto Reyes Castro**  
Physics Graduate · MSc Artificial Intelligence Student

- **GitHub:** https://github.com/albertoreyescastro
- **Kaggle:** https://www.kaggle.com/albertoreyescastro20
- **LinkedIn:** https://www.linkedin.com/in/alberto-reyes-ba5546238/

---

## Acknowledgements

- Kaggle for hosting the notebook and dataset.
- The dataset contributors for making the credit card fraud dataset publicly available.
- Northumbria University London for the academic project context.

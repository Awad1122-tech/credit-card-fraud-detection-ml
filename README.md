# Credit Card Fraud Detection (Machine Learning)

## Overview
This project focuses on detecting fraudulent credit card transactions in a highly imbalanced dataset, where fraudulent cases represent a very small fraction of total transactions. The objective is not to maximise accuracy, but to design and evaluate models that balance fraud detection effectiveness with operational practicality, minimising unnecessary customer friction while still capturing the majority of fraudulent activity.

The project progresses from simple baseline models to an ensemble approach, analysing how different algorithms behave under extreme class imbalance and why certain models are more suitable for real-world fraud detection systems.

## Dataset
This project uses the Credit Card Fraud Detection dataset (European cardholders), originally published by the Université Libre de Bruxelles (ULB) on Kaggle.

- The dataset contains anonymised transaction features transformed using PCA
- Fraud cases account for approximately 0.17% of all transactions
- The target variable indicates whether a transaction is fraudulent or legitimate

Due to file size limitations, the dataset is not included in this repository.

### How to run the notebook
1. Download the dataset from Kaggle
2. Place the file named `creditcard.csv` in the root directory of this repository
3. Run the notebook normally

Official dataset source:  
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

> Note: A Kaggle account is required to download the dataset.

## Methodology

### Logistic Regression (Baseline)
Logistic Regression was used as a baseline model to establish reference performance under severe class imbalance.

- Achieved high fraud recall and strong ROC-AUC, indicating good ranking ability
- Produced extremely low fraud precision, resulting in a large number of false positives
- Demonstrated why accuracy and ROC-AUC alone are insufficient for fraud detection

### Decision Tree
A Decision Tree model was evaluated to capture non-linear decision rules and feature interactions.

- Multiple maximum depths were tested to study model complexity
- Moderate depth produced the best precision–recall balance
- Deeper trees overfit and became unstable

### Random Forest (Final Model)
A Random Forest ensemble was implemented to overcome the limitations of single models.

- Aggregates multiple decision trees trained on different data and feature subsets
- Reduces variance and overfitting
- Preserves non-linear modelling capability

The Random Forest achieved a stable and operationally realistic error profile with strong fraud recall, high precision, and low false positives.

## Model Evaluation Strategy
Given the extreme class imbalance, models were evaluated using:
- Confusion matrices
- Fraud precision and recall
- ROC-AUC
- Precision–Recall curves

Accuracy was intentionally avoided as a primary metric.

## Final Conclusion
The Random Forest model was selected as the final model due to its robustness, stability, and superior balance between fraud detection performance and customer impact. This reflects real-world fraud detection priorities, where controlling false positives is as important as detecting fraud.

## Technologies Used
- Python
- pandas, numpy
- scikit-learn
- matplotlib

## Notes
This project emphasises decision-driven modelling and operational considerations rather than metric optimisation alone, reflecting real-world constraints faced by fraud detection teams.

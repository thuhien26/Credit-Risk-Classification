# Credit Risk Classification

## Project Overview

A supervised machine learning project for analyzing credit records and predicting five-category debt risk groups. The recorded experiment used **27,001 labeled records** and generated predictions for **25,000 out-of-sample records**, targeting `NHOMNO` and `NHOMNOMOI`.

## Methodology & Implementation

- Explored data quality, class distributions, and relationships between credit-related features.
- Performed data preprocessing and feature engineering, including date-based and loan-related variables.
- Trained and compared **Logistic Regression** and **Random Forest** classifiers.
- Applied cross-validation and hyperparameter tuning, then assessed performance using Accuracy, Macro-F1, and confusion matrices.

## Results & Key Findings

The tuned **Random Forest** models produced the following results on the held-out test set:

| Classification Target | Accuracy | Macro-F1 |
|---|---:|---:|
| `NHOMNO` | 83.03% | 54.94% |
| `NHOMNOMOI` | 82.63% | 54.13% |

Macro-F1 provides important context because the debt groups are imbalanced. Results are from the notebook's recorded experiment. **The original credit datasets are not included in this repository.**

## Technologies

Python, Jupyter Notebook, pandas, NumPy, scikit-learn, Matplotlib, Seaborn.

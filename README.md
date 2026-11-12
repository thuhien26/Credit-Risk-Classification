# Credit Risk Classification

A Python machine learning project that analyzes credit records and predicts debt classification groups. The workflow covers data exploration, preprocessing, feature engineering, model comparison, evaluation, and out-of-sample prediction.

## Dataset Overview

The original notebook run used:

- **Training data:** 27,001 labeled records from `Data_credit_rating_VN.xlsx` (worksheet `saoke_td_ct`).
- **Out-of-sample data:** 25,000 unlabeled records from `Out_of_sample_data106.csv`.
- **Input features:** 18 variables describing loan balances, interest rates, dates, account types, and other credit-related attributes.
- **Prediction targets:** `NHOMNO` and `NHOMNOMOI`, each with five debt-group categories.

The target-related column `NHOMNO_TCBS` is excluded from model inputs to reduce leakage risk.

## Technologies Used

- **Language and environment:** Python, Jupyter Notebook
- **Data processing:** pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine learning:** scikit-learn

## Methodology

1. **Data exploration and cleaning:** Check missing values, duplicate records, class imbalance, date formats, and numerical outliers.
2. **Feature engineering:** Create loan-term and date features, flags for invalid terms, and log-transformed balance features; encode categorical variables and impute missing values.
3. **Leakage-aware evaluation:** Use an approximately 80/20 train/test split that keeps identical input records in the same partition. Perform feature selection on the development data.
4. **Model training:** Compare Multinomial Logistic Regression and Random Forest, using class weighting and three-fold group-aware cross-validation for hyperparameter tuning.
5. **Model evaluation:** Report Accuracy, Macro-F1, Balanced Accuracy, confusion matrices, and multiclass AUC. Also examine temporal sensitivity and feature importance.
6. **Prediction:** Refit the selected model specifications on labeled data and generate predictions for the out-of-sample dataset.

## Model Results

In the notebook's recorded run, **tuned Random Forest** was selected for both targets using development cross-validation Macro-F1. Results on the held-out test set were:

| Target | Accuracy | Macro-F1 |
|---|---:|---:|
| `NHOMNO` | 83.03% | 54.94% |
| `NHOMNOMOI` | 82.63% | 54.13% |

The recorded run generated predictions for all 25,000 out-of-sample records with no missing predicted labels.

Since the target groups are imbalanced, Accuracy should be interpreted together with Macro-F1 and class-level results. These figures are from the original notebook's saved execution and have not been independently reproduced without the source datasets.

## How to Run

1. Install Python 3 and Jupyter Notebook.
2. Install the required libraries:

   ```bash
   pip install notebook pandas numpy matplotlib seaborn scikit-learn openpyxl
   ```

3. Place `Data_credit_rating_VN.xlsx` and `Out_of_sample_data106.csv` in the same folder as `credit_risk_classification.ipynb`. The Excel workbook must contain a worksheet named `saoke_td_ct`.
4. Open Jupyter Notebook from the project folder, then open `credit_risk_classification.ipynb` and run the cells in order.
5. The notebook saves the prediction file to `outputs_final_report/Out_of_sample_data106_predictions.csv`, preserving the original input rows and adding `NHOMNO` and `NHOMNOMOI` prediction columns.

## Data Availability

The source credit datasets and generated predictions are **not included** in this public repository. Reproducing the notebook requires authorized access to the two input files.

The code is provided for portfolio review and educational demonstration, not for automated credit decisions.

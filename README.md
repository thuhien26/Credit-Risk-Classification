# Credit Risk Classification

A Python machine learning project that analyzes credit records and predicts debt classification groups using supervised learning methods.

## Technologies Used

* Python and Jupyter Notebook
* pandas, NumPy, Matplotlib, Seaborn
* scikit-learn

## Main Features

* Data cleaning, exploratory data analysis, and feature engineering
* Handling class imbalance and selecting useful features
* Comparing Multinomial Logistic Regression and Random Forest classifiers
* Group-aware train/test evaluation and hyperparameter tuning
* Predicting two credit classification targets: `NHOMNO` and `NHOMNOMOI`

## How to Run

1. Install Python 3 and Jupyter Notebook.
2. Install the required libraries:

```bash
   pip install notebook pandas numpy matplotlib seaborn scikit-learn openpyxl
   ```

3. Place `Data\_credit\_rating\_VN.xlsx` and `Out\_of\_sample\_data106.csv` in the same folder as the notebook. The Excel file must contain a worksheet named `saoke\_td\_ct`.
4. Open `credit_risk_classification.ipynb` in Jupyter Notebook or VS Code and run its cells in order.
5. Prediction results are saved to `outputs\_final\_report/Out\_of\_sample\_data106\_predictions.csv`.

**Data availability:** The required input datasets are not included in this public repository. Run the notebook only with datasets you are authorized to use.


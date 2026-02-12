# Loan Approval Classifier — SVM on Loan Status Dataset

## Short description

SVM-based loan approval classifier built from the `loan_status.csv` dataset. The analysis is implemented in `LoanStatus.ipynb` and includes EDA, simple preprocessing (missing-value removal and categorical encoding), model training (linear SVM), evaluation, and a single-applicant example prediction cell.

## Files

- `LoanStatus.ipynb` — Jupyter notebook with the full workflow.
- `loan_status.csv` — dataset used by the notebook.

## Notebook overview

1. Import libraries and load `loan_status.csv`.
2. Exploratory data analysis: countplots for categorical features grouped by loan status.
3. Preprocessing: drop missing rows and encode categorical columns (Gender, Married, Dependents, Education, Self_Employed, Property_Area, Loan_Status).
4. Train/test split and train a linear SVM classifier.
5. Evaluate accuracy on the test set.
6. Example input cell to run a single-applicant prediction.

## How to run

1. Create (or activate) a Python environment and install dependencies:

```bash
python -m venv .venv
.venv\Scripts\activate
```

2. Open `LoanStatus.ipynb` in Jupyter or VS Code and run the cells sequentially.

## Example input mapping

The example prediction cell expects a tuple matching the notebook's encoded feature order (example tuple included in the notebook):

- Feature order used in the example: Gender, Married, Dependents, Education, Self_Employed, ApplicantIncome, CoapplicantIncome, LoanAmount, Loan_Amount_Term, Credit_History, Property_Area
- Encodings used in the notebook:
  - Gender: Male=1, Female=0
  - Married: Yes=1, No=0
  - Dependents: 0, 1, 2, 3+ -> 4
  - Education: Graduate=0, Not Graduate=1
  - Self_Employed: Yes=1, No=0
  - Property_Area: Rural=0, Semiurban=1, Urban=2

Example tuple in notebook: `(1, 1, 0, 0, 0, 5000, 0, 128, 360, 1, 1)`

## Notes & next steps

- The notebook removes rows with missing values for simplicity; consider more robust imputation for production work.
- You may want to add feature scaling, cross-validation, and hyperparameter tuning to improve performance.

---


## Credit Score Model

This project focuses on **predicting the probability of a person experiencing serious delinquency in the next two years** based on historical credit data.  
It uses **machine learning models** to process financial and demographic information and outputs a risk score.

---

##  Dataset

The project uses two datasets provided:

- **Training Data:** `cs-training.csv`  
- **Test Data:** `cs-test.csv`  
- **Sample Submission Format:** `sampleEntry.csv`  
- **Data Dictionary:** `Data Dictionary.xls`

**Target Variable:**  
- `SeriousDlqin2yrs` → Binary indicator (1 if the person experienced serious delinquency, 0 otherwise)

**Key Features:**  
| Feature | Description |
|---------|-------------|
| RevolvingUtilizationOfUnsecuredLines | Total balance on credit cards and personal lines of credit, excluding real estate and no installment debt, divided by the sum of credit limits |
| age | Age of the borrower in years |
| NumberOfTime30-59DaysPastDueNotWorse | Number of times borrower has been 30–59 days past due but not worse in the last 2 years |
| DebtRatio | Monthly debt payments, alimony, living costs divided by monthly gross income |
| MonthlyIncome | Monthly income |
| NumberOfOpenCreditLinesAndLoans | Number of open loans (installment loans such as car loan or mortgage) and lines of credit (e.g., credit cards) |
| NumberOfTimes90DaysLate | Number of times borrower has been 90 days or more past due |
| NumberRealEstateLoansOrLines | Number of mortgage and real estate loans including home equity lines of credit |
| NumberOfTime60-89DaysPastDueNotWorse | Number of times borrower has been 60–89 days past due but not worse in the last 2 years |
| NumberOfDependents | Number of dependents in the family (excluding spouse) |

---

## ⚙️ Methodology

1. **Data Cleaning & Preprocessing**
   - Filled missing `MonthlyIncome` with median from training set.
   - Filled remaining missing values with median of respective columns.
   - Removed duplicates (if any).
   - Scaled features using `StandardScaler`.

2. **Feature Engineering**
   - No categorical encoding required (all features numeric).
   - Removed target variable from features for training.

3. **Model Selection**
   - Trained and tuned the following models:
     - Random Forest (`rf_grid`)
     - XGBoost (`xgb_grid`)
   - Performed hyperparameter tuning using GridSearchCV.

4. **Evaluation Metrics**
   - AUC-ROC Score
   - Log Loss
   - Accuracy (less important for an imbalanced dataset)

---

##  Results

- **Best Model:** XGBoost Classifier  
- **Best AUC Score:** *(add final score here)*  
- **Feature Importance:** `RevolvingUtilizationOfUnsecuredLines` and `age` had the highest influence.

---

## Resources 
- Dataset: https://www.kaggle.com/competitions/GiveMeSomeCredit/data

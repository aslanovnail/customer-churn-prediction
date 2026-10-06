# Customer Churn Prediction

## Business Problem
Customer churn is one of the costliest problems for subscription businesses — acquiring a new customer costs far more than retaining one. This project builds a model to flag customers who are likely to leave, so retention efforts can target the right people before they go.

## Data
Telecom customer dataset with features including:
- Demographics: age, geography
- Account: balance, tenure, products held
- Behavior: activity status, credit score

Target variable: **Churn** (0 = stayed, 1 = left)

> Note: this project was developed in a training environment where datasets were accessed via platform paths (`/datasets/...`), so raw data files are not included in this repo.

## Approach
1. **Data cleaning & preprocessing** — handled missing values, encoded categoricals, scaled numerics
2. **Exploratory analysis** — churn rates by segment, correlation with balance/age/activity
3. **Feature engineering** — interaction features from account and behavior signals
4. **Modeling** — compared Logistic Regression, Random Forest, and CatBoost with cross-validation
5. **Evaluation** — ROC-AUC and accuracy on a held-out test set

## Results
**Best model: CatBoost** — **0.97 ROC-AUC** and **93% accuracy** on the held-out test set, beating Logistic Regression and Random Forest baselines. Strong enough to drive real retention targeting.

## Business Takeaways
- Customers with **low balance + high age** churn at the highest rates
- **Inactive members** are the top risk segment — win-back campaigns should start here
- The model can score the full customer base monthly to prioritize outreach

## Tech
Python · pandas · scikit-learn · CatBoost · matplotlib/seaborn

## Run it
```bash
pip install -r requirements.txt
jupyter notebook telecom_churn_prediction.ipynb
```

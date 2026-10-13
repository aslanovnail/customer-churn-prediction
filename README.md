# Customer Churn Prediction

## Business Problem

Customer churn is one of the costliest problems for subscription businesses — acquiring a new customer costs far more than retaining one. This project builds a model to flag customers who are likely to leave, so retention efforts can target the right people before they go.

## Data

Telecom customer dataset — 7,000+ subscriber records with tenure and service-usage signals.

Six features engineered from the raw data:

- `tenure_days` — how long the customer has been subscribed
- `total_services` — number of services on the account
- `avg_monthly_spend_est` — estimated average monthly spend
- three contract begin-date parts (year / month / day of signup)

Target variable: **Churn** (0 = stayed, 1 = left)

> Note: this project was developed in a training environment where datasets were accessed via platform paths (`/datasets/...`), so raw data files are not included in this repo.

## Approach

1. **Data cleaning & preprocessing** — handled missing values, encoded categoricals, scaled numerics
2. **Exploratory analysis** — churn-rate distributions and correlations with key features
3. **Feature engineering** — six features from tenure, spend, and signup-date signals
4. **Modeling** — CatBoost classifier
5. **Evaluation** — ROC-AUC and accuracy on a held-out test set

## Results

**CatBoost** — **0.97 ROC-AUC** and **93% accuracy** on the held-out test set. Strong enough to drive real retention targeting.

## Business Takeaways

- A churn classifier is a targeting tool: score the full subscriber base and direct retention offers to the customers most likely to leave.
- ROC-AUC (0.97) is the metric that matters here — it measures ranking quality, which is exactly what a prioritized outreach list runs on.

## Tech

Python · pandas · scikit-learn · CatBoost · matplotlib/seaborn

## Run it

```
pip install -r requirements.txt
jupyter notebook telecom_churn_prediction.ipynb
```

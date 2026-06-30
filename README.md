# Telecom Marketing Campaign — Predicting Customer Subscription

End-to-end data science project analysing a telecommunications marketing campaign to identify which customers are most likely to subscribe to a new plan, and to build predictive models that support smarter, more cost-effective targeting.

## Project Overview

Marketing campaigns are expensive, and contacting the wrong customers wastes resources. This project explores a telecom dataset of ~41,000 customer records to understand what drives subscription behaviour, then builds and compares two predictive models to support targeted outreach decisions.

The project is split into two phases:

**Phase 1 — Exploratory Data Analysis** 
- Data cleaning, handling of missing/"unknown" values, duplicate removal
- Univariate, bivariate, and multivariate analysis
- Correlation analysis (Pearson for numeric, Cramér's V for categorical)
- Key finding: call duration, prior campaign outcome, contact method, and timing were stronger predictors than demographics

**Phase 2 — Predictive Modelling** 
- Feature engineering: binary, ordinal, and one-hot encoding via `ColumnTransformer` pipelines
- KNN imputation and group-based imputation for missing values
- Two models built and compared: **Logistic Regression** (parametric, interpretable) and **Random Forest** (non-parametric, higher raw accuracy)
- Stratified 5-fold cross-validation, full metric suite (Accuracy, Precision, Recall, F1, ROC-AUC)
- Business-driven model selection based on the cost trade-off between missed leads and wasted calls

## Key Results

| Metric | Logistic Regression | Random Forest |
|---|---|---|
| Accuracy | 0.826 | 0.893 |
| Precision | 0.351 | 0.549 |
| Recall | 0.644 | 0.272 |
| F1-Score | 0.454 | 0.364 |
| ROC-AUC | 0.799 | 0.781 |

**Logistic Regression was recommended for lead targeting** — it identifies 137% more true subscribers than Random Forest, which matters more than raw accuracy when the cost of missing a lead outweighs the cost of an unnecessary call. Random Forest is better suited for bulk forecasting and resource planning at scale.

## Business Recommendations

- Prioritise outreach in **March and October** (strongest positive predictors of conversion)
- Re-contact customers with a **previous successful campaign outcome**
- Avoid contacting the same customer more than ~10 times — returns diminish sharply after the first few attempts
- Target **retired customers and those without housing/personal loans** as higher-likelihood segments

## Tools & Methods

Python (Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn), Jupyter/Google Colab, Logistic Regression, Random Forest, KNN Imputation, Stratified Cross-Validation, ColumnTransformer Pipelines

## Repository Structure

```
telecom-marketing-prediction/
├── data/
│   └── TeleCom_Data-1.xlsx
├── 01_EDA.ipynb
├── 02_Modelling.ipynb
└── reports/
    ├── EDA_Report.pdf
    └── Modelling_Report.pdf
```

## Dataset

Based on the UCI Bank Marketing dataset (commonly used for telemarketing/subscription prediction research), adapted here for a telecommunications context. ~41,000 records covering customer demographics, financial attributes, contact history, and macroeconomic indicators.

## Author

Vanshika Lakhani — Master of Business Analytics, University of Technology Sydney
[LinkedIn](https://www.linkedin.com/in/vanshika-lakhani2002)

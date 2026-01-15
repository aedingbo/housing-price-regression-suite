# Housing Price Regression Suite

Predict housing sale prices using regression techniques. This repo includes two notebooks:

- **01_workbook.ipynb** — full class workflow + notes (EDA → least squares → ridge → bayesian)
- **02_clean.ipynb** — minimal, portfolio-ready version with a concise conclusion

---

## Problem
Given housing features (e.g., living area and year built), predict **SalePrice**.  
This project focuses on comparing regression approaches and understanding tradeoffs between baseline fit, regularization, and probabilistic modeling.

---

## Skills Demonstrated
- **Exploratory Data Analysis (EDA):** Used `pandas` and `matplotlib` to inspect feature distributions, relationships, and outliers relevant to SalePrice.
- **Numerical Programming:** Implemented key regression concepts (matrix operations, error measurement, and optimization patterns) to reinforce fundamentals.
- **Regression Modeling:** Built and compared **Least Squares (OLS)**, **Ridge Regression**, and **Bayesian Regression**.
- **Model Evaluation:** Measured error using **RMSE** and interpreted how modeling choices affect fit and stability.
- **Critical Thinking:** Explained tradeoffs (baseline vs. regularized vs. probabilistic) and why different assumptions lead to different coefficients and behavior.

---

## Project Workflow (01_workbook.ipynb)
### 1) Data Cleaning & EDA
- Loaded the housing dataset and validated data quality.
- Visualized relationships between key predictors and SalePrice.

### 2) Least Squares Regression (Baseline)
- Fit a baseline regression model and evaluated error.
- RMSE was computed to quantify predictive performance.

### 3) Ridge Regression (Regularization + Tuning)
- Introduced L2 regularization to control coefficient magnitude and improve stability.
- Performed a simple grid search to select a good regularization strength.

### 4) Bayesian Regression (MAP + Uncertainty)
- Modeled regression using a Bayesian perspective (MAP estimation).
- Computed predictive uncertainty using a posterior covariance matrix.

---

## Results (Summary)
- **Baseline (Least Squares):** RMSE observed in the workflow was **~53,092.48**.
- **Ridge (alpha = 100000)** reduced the YearBuilt coefficient from **~1045.86 → ~970.06**, demonstrating how regularization shrinks coefficients and stabilizes the model.
- **Ridge tuning:** best lambda found during the notebook’s grid search was **~2.94**.
- **Bayesian Regression:** produced MAP/ML weights (Base $, $/sqft, $/yr) of  
  `[-2.292e6, 59.25, 1207.80]` and estimated noise **σ² ≈ 1.471e9 (dollars²)**.  
  An example prediction (1700 sqft, year 1980) produced a mean of **~158,742** with an associated prediction variance.

---

## Repo Contents
- `01_workbook.ipynb` — full workflow + notes
- `02_clean.ipynb` — minimal version for portfolio review
- *(dataset file used in the notebook)*

---

## Acknowledgments
Completed as part of the Applied Machine Learning Bootcamp (Columbia University).

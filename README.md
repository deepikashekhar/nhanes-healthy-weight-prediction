# Healthy-Weight Prediction Using NHANES 2017–2018

## QM640 Data Analytics Capstone

**Student:** Deepika Shekhar  
**Institution:** Walsh College  
**Course:** QM640 – Data Analytics Capstone  
**Mentor:** Mr. Smritraj Raut  
**Term:** Term 3, 2026

## Project Overview

This study investigates whether depressive symptom severity,
measured using the Patient Health Questionnaire-9 (PHQ-9),
provides incremental predictive value for healthy-weight
classification beyond demographic, socioeconomic, and lifestyle
predictors.

The analysis uses NHANES 2017–2018 data from 4,657 adults
aged 20 years or older.

## Research Questions

RQ1. To what extent is depressive symptom severity associated
with healthy-weight status?

RQ2. Does adding PHQ-9 improve prediction beyond demographic
and lifestyle variables?

RQ3. Which statistical or machine-learning model provides the
best predictive performance?

RQ4. How can Explainable Artificial Intelligence improve model
transparency and interpretation?

## Analytical Approach

Three model families were evaluated:

- Logistic Regression
- Random Forest
- XGBoost

Each model was evaluated using a baseline predictor set and an
extended specification adding PHQ9_TOTAL.

The dataset was divided using an 80/20 stratified train-test split.
Model development used 5-fold stratified cross-validation on the
training data.

SHAP was used for global and local explainability.

## Key Results

The final analytical cohort contained 4,657 adults.

PHQ-9 was independently associated with healthy-weight status
(adjusted OR = 0.9729 per PHQ-9 point, p = .0034), but the
effect size was small.

Adding PHQ-9 produced negligible changes in held-out ROC-AUC:

- Logistic Regression: +0.0024
- Random Forest: +0.0024
- XGBoost: -0.0002

Paired-bootstrap 95% confidence intervals for all three changes
included zero.

Baseline XGBoost achieved the highest held-out ROC-AUC:

**ROC-AUC = 0.7109**

## Main Conclusion

Depressive symptom severity is statistically associated with
healthy-weight status but does not provide meaningful incremental
predictive discrimination beyond demographic and lifestyle
predictors in this dataset.

SHAP analysis nevertheless showed that PHQ9_TOTAL influenced
individual predictions and ranked seventh in global importance
within the extended XGBoost model.

This demonstrates an important distinction between statistical
association, incremental predictive value, and individual feature
contribution.

## Repository Structure

- `notebooks/` – complete executable analysis
- `data/processed/` – final analytical dataset
- `data/documentation/` – variable/data dictionary
- `results/tables/` – final numerical results
- `results/figures/` – model and SHAP visualizations
- `report/` – final QM640 capstone report

## Reproducing the Analysis

1. Install the packages in `requirements.txt`.
2. Open the final Jupyter notebook.
3. Run all cells sequentially from top to bottom.
4. Outputs will reproduce the statistical analyses, predictive
   models, model comparison, robustness analyses, and SHAP
   explanations.

Random seed: 42.

## Data Source

National Health and Nutrition Examination Survey (NHANES),
2017–2018 cycle, National Center for Health Statistics,
Centers for Disease Control and Prevention.

## Important Interpretation

This study is observational and cross-sectional. Results should
not be interpreted as causal or as a clinical diagnostic tool.
The predictive analysis did not incorporate the complex NHANES
survey design and therefore should not be interpreted as
nationally representative population estimates.

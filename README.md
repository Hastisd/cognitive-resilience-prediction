# Predicting Executive Function Decline

**A rigorous clinical prediction modeling pipeline** following best practices from *Machine Learning in Clinical Neuroscience* (Staartjes et al., 2022)

---

## Project Overview

This project implements a complete machine learning pipeline to predict the risk of executive function decline.  
It strictly follows the methodological recommendations from Chapters 2–6 of *Machine Learning in Clinical Neuroscience*, including:

- Proper data preprocessing (no data leakage)
- Nested cross-validation
- Multiple model comparison
- Full discrimination + calibration evaluation
- Decision Curve Analysis for clinical utility

The goal is to demonstrate correct and transparent clinical prediction modeling rather than chasing the highest possible accuracy.

---

## Key Methodological Features

| Concept                         | Implementation                              | Book Chapter |
|--------------------------------|---------------------------------------------|--------------|
| 4-step predictive workflow     | Full pipeline structure                     | Chapter 2    |
| Overfitting prevention         | Nested Cross-Validation + class weighting   | Chapter 3    |
| Discrimination metrics         | AUC, Sensitivity, Specificity, PPV, NPV, F1 | Chapter 4    |
| Calibration                    | Calibration plot, Brier score               | Chapter 4    |
| Clinical utility               | Decision Curve Analysis                     | Chapter 4/15 |
| Binary classification practice | End-to-end implementation                   | Chapter 5    |

---

## Models Used

- Logistic Regression (with class weighting)
- Random Forest
- XGBoost

All models were evaluated using **5-fold nested cross-validation**.

---

## Results Summary

| Model                 | AUC   | Sensitivity | Specificity | PPV   | NPV   | Brier |
|-----------------------|-------|-------------|-------------|-------|-------|-------|
| Logistic Regression   | 0.696 | 0.614       | 0.657       | 0.199 | 0.925 | 0.217 |
| Random Forest         | 0.688 | 0.007       | 0.994       | 0.067 | 0.877 | 0.104 |
| XGBoost               | 0.662 | 0.074       | 0.971       | 0.257 | 0.882 | 0.111 |

**Best model according to AUC:** Logistic Regression

---

## Project Structure

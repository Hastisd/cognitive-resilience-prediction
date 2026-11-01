# Predicting Executive Function Decline in Healthcare Workers

**A rigorous clinical prediction modeling pipeline following best practices from *Machine Learning in Clinical Neuroscience* (Staartjes et al., 2022)**

## Motivation

Healthcare workers are at high risk of cognitive fatigue and decline in executive function due to shift work, high workload, and chronic stress.  
Early identification of individuals at risk can support timely interventions and improve both worker well-being and patient safety.

This project implements a complete, methodologically rigorous machine learning pipeline to predict executive function decline, strictly following the recommendations in Chapters 2–6 of *Machine Learning in Clinical Neuroscience*.


## Key Methodological Principles Applied

This project deliberately demonstrates mastery of the following concepts:

- Clear separation of **explanatory vs predictive modeling**
- Strict prevention of **overfitting** and **data leakage**
- **Nested cross-validation** for honest performance estimation
- Full **discrimination + calibration** evaluation
- **Decision Curve Analysis** for clinical utility
- Transparent reporting aligned with TRIPOD principles


## Dataset

A realistic **simulated dataset** was created to reflect typical ergonomics and occupational health variables:

**Features include:**
- Demographics (age, gender, years of experience)
- Work-related factors (weekly working hours, night shift frequency, overtime)
- Psychosocial factors (perceived stress, sleep quality, recovery)
- Basic cognitive indicators (baseline executive function score)

**Target:**  
Binary outcome – Executive Function Decline (Yes/No) within 6 months

The simulation script is fully available in `data/generate_simulated_data.py` for full reproducibility.


## Pipeline Overview (4-Step Workflow)

1. **Data Preparation**  
   - Cleaning, encoding, scaling  
   - Missing data handling (imputer fitted only on training data)

2. **Model Training**  
   - Nested cross-validation (outer 5-fold, inner 3-fold)
   - Model comparison: Logistic Regression, Random Forest, XGBoost
   - Hyperparameter tuning + class imbalance handling

3. **Evaluation**  
   - Discrimination: AUC, Sensitivity, Specificity, PPV, NPV, F1
   - Calibration: Calibration plot, Intercept, Slope, Brier Score
   - Clinical Utility: Decision Curve Analysis

4. **Validation & Reporting**  
   - Out-of-fold performance aggregation  
   - Variable importance  
   - Transparent reporting of all steps


## How to Run

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Generate simulated data
python data/generate_simulated_data.py

# 3. Run the full pipeline
python src/pipeline.py

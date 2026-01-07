# Myocardial Infarction Risk Prediction & Feature Selection

## 1. Project Overview
This project focuses on predicting post–myocardial infarction outcomes using high-dimensional clinical data.  
The primary objective is to identify a compact and interpretable set of clinical risk factors while maintaining strong predictive performance.

- **Dataset size:** 1,700 patients  
- **Number of features:** 124 clinical variables  
- **Target variable:** `let_is` (multi-class myocardial infarction outcome)

The key challenge lies in handling missing data, multicollinearity, and high feature dimensionality while producing results that remain interpretable for downstream decision-making.

---

## 2. Motivation
Real-world clinical datasets are often noisy, incomplete, and high-dimensional.  
While complex machine learning models can achieve strong predictive performance, they are frequently difficult to interpret and validate in practice.

This project explores how **hybrid feature selection strategies** can balance:
- predictive accuracy,
- robustness and generalization,
- and interpretability of selected clinical risk factors.

---

## 3. Data Preparation
To ensure data quality and modeling stability, the following preprocessing steps were applied:

- Removed samples with more than **20% missing values**
- Dropped features with more than **30% missingness**
- Imputed missing values:
  - Median imputation for continuous variables
  - Mode imputation for categorical variables
- Reduced multicollinearity using **Variance Inflation Factor (VIF)** filtering  
  - VIF threshold = 5  
  - Feature count reduced from 115 to 100

These steps resulted in a clean and stable feature set for downstream modeling.

---

## 4. Modeling Strategy
A **hybrid modeling approach** was adopted to combine predictive performance with interpretability:

1. **Random Forest**
   - Captures non-linear relationships and feature interactions
   - Provides an initial ranking of feature importance

2. **Recursive Feature Elimination (RFE)**
   - Further refines the feature set within an interpretable framework
   - Reduces redundancy while preserving predictive signal

3. **Multinomial Logistic Regression**
   - Serves as the final predictive model
   - Enables interpretability of selected predictors

This approach leverages the strengths of both non-parametric and parametric methods.

---

## 5. Results
- **Final selected features:** 11 predictors  
- **Cross-validation accuracy:** approximately 0.84  
- **Test accuracy:** approximately 0.86  

Cross-validation and test performance are closely aligned, indicating good generalization.  
Several clinical and biochemical indicators consistently ranked as important, highlighting the multifactorial nature of myocardial infarction outcomes.

---

## 6. Key Insights
- Myocardial infarction outcomes are influenced by **multiple interacting clinical factors**, rather than a single dominant variable.
- Hybrid feature selection improves interpretability without sacrificing predictive performance.
- The final model achieves a practical balance between complexity and explainability.

---

## 7. Limitations & Future Work
Several limitations should be noted.  
Class imbalance may affect accuracy-based evaluation metrics, particularly for underrepresented outcome classes.

Potential future improvements include:
- applying class-weighted models to better handle minority classes,
- using alternative evaluation metrics such as macro-F1,
- exploring regularized regression approaches (e.g., LASSO) for additional feature selection stability.

---

## 8. Repository Structure

```text
mi-risk-prediction/
├── README.md
├── notebooks/
│   └── MI_Risk_Analysis_interview.ipynb
├── data/
│   └── processed datasets (optional)
└── report/
    └── Bio_Final_Report.pdf

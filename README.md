# mi-risk-prediction
Myocardial infarction outcome prediction and feature selection
Myocardial Infarction Risk Prediction & Feature Selection
1. Project Overview
This project focuses on predicting post–myocardial infarction outcomes using high-dimensional clinical data.
The primary objective is to identify a compact, interpretable set of clinical risk factors while maintaining strong predictive performance.
Dataset size: 1,700 patients
Number of features: 124 clinical variables
Target variable: let_is (multi-class myocardial infarction outcome)
The key challenge lies in handling missing data, multicollinearity, and high feature dimensionality while producing results that remain interpretable for downstream decision-making.
2. Motivation
Real-world clinical datasets are often noisy, incomplete, and high-dimensional.
While complex machine learning models can achieve strong predictive performance, they are often difficult to interpret and validate in practice.
This project aims to explore how hybrid feature selection strategies can balance:
predictive accuracy,
robustness and generalization,
and interpretability of selected risk factors.
3. Data Preparation
To ensure data quality and modeling stability, the following preprocessing steps were applied:
Removed samples with more than 20% missing values
Dropped features with more than 30% missingness
Imputed missing values:
Median imputation for continuous variables
Mode imputation for categorical variables
Reduced multicollinearity using Variance Inflation Factor (VIF) filtering
VIF threshold = 5
Feature count reduced from 115 to 100
These steps provided a clean and stable feature set for downstream modeling.
4. Modeling Strategy
A hybrid modeling approach was adopted to combine predictive power with interpretability:
Random Forest
Captures non-linear relationships and feature interactions
Provides an initial ranking of feature importance
Recursive Feature Elimination (RFE)
Further refines the feature set within an interpretable framework
Reduces redundancy while preserving predictive signal
Multinomial Logistic Regression
Serves as the final predictive model
Enables interpretability of selected predictors
This hybrid approach leverages the strengths of both non-parametric and parametric methods.
5. Results
Final selected features: 11 predictors
Test accuracy: approximately 89%
Cross-validation and test performance are closely aligned, indicating good generalization.
Several clinical and biochemical indicators consistently ranked as important, highlighting the multifactorial nature of myocardial infarction outcomes.
6. Key Insights
Myocardial infarction outcomes are influenced by multiple interacting clinical factors, rather than a single dominant variable.
Hybrid feature selection improves interpretability without sacrificing model performance.
The resulting model provides a practical balance between complexity and explainability.
7. Limitations & Future Work
Class imbalance may affect accuracy-based evaluation metrics.
Future improvements could include:
class-weighted models,
alternative metrics such as macro-F1,
regularized regression methods (e.g., LASSO).
## 8. Repository Structure
mi-risk-prediction/
├── README.md
├── notebooks/
│   └── MI_Risk_Analysis.ipynb
├── data/
│   └── processed datasets 
└── report/
    └── Bio_Final_Report.pdf

9. Notes
Due to data-sharing restrictions, raw clinical data are not publicly included.
All preprocessing and modeling steps are fully documented in the notebook.

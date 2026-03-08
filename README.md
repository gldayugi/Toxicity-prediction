**SCT213-C002-0072/2023**

**GERALD AYUGI**

**Project Description**

The goal of this project is to classify chemical compounds as Toxic or NonToxic. Predicting toxicity is a critical step in drug discovery and environmental safety. 

This notebook handles high-dimensional chemical data by implementing custom feature engineering and comparing various dimensionality reduction techniques to visualize the "Chemical Space."

**Key Features**

Dimensionality Reduction: Comparison of PCA, 3D-PCA, and UMAP to visualize how toxic and non-toxic compounds cluster in lower dimensions.

Correlation Analysis: A network-based approach to visualize feature dependencies and a custom transformer to remove highly collinear variables.

Automated Pipeline: A Scikit-Learn Pipeline that integrates:

     Variance Thresholding (removing low-information features).

     Custom Collinearity Filtering.

     Feature Selection via SelectFromModel (Random Forest).

     Balanced Random Forest Classification to handle class imbalance.

Validation: 5-Fold Stratified Cross-Validation with comprehensive evaluation using Confusion Matrices and Classification Reports.

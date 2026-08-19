

---

## **Project Description**

The goal of this project is to classify chemical compounds as **Toxic** or **Non-Toxic**. Predicting toxicity is a critical step in drug discovery and environmental safety.

This notebook handles high-dimensional chemical data by implementing custom feature engineering and comparing various dimensionality reduction techniques to visualize the *Chemical Space*.

---

## **Key Features**

### **Dimensionality Reduction**

Comparison of PCA and UMAP to visualize how toxic and non-toxic compounds cluster in lower dimensions.

### **Correlation Analysis**

A network-based approach to visualize feature dependencies and a custom transformer to remove highly collinear variables.

---

## **Pipeline**

A full machine learning pipeline was implemented to ensure consistent and leak-free preprocessing:

### **Variance Threshold**

Removes low-variance (uninformative) features.

### **DropHighCorr (Custom Transformer)**

Eliminates highly correlated features (threshold = 0.9).
Reduces redundancy and multicollinearity.

### **StandardScaler**

Standardizes features for better model performance.

### **Feature Selection (SelectFromModel)**

Uses a Random Forest model to select important features.

### **Final Classifier**

Support Vector Machine (SVM) used for prediction.

---

## **Baseline Model**

The pipeline was first evaluated without hyperparameter tuning using **Stratified 5-Fold Cross-Validation**.

### **Output:**

* Mean accuracy
* Standard deviation across folds

---

## **Hyperparameter Tuning**

My goal in conducting hyperparameter tuning was to optimize model performance and understand how different hyperparameters influence results.

Before tuning, the model achieved:

**Accuracy: 0.6373109243697479**

This serves as my reference point for evaluating improvements.

---

## ⚙️ **Hyperparameter Tuning Techniques**

### **1. 🎲 Randomized Search**

I used **RandomizedSearchCV** to sample a subset of hyperparameter combinations.

### **Parameters Tuned:**

* `C`
* `gamma`
* `kernel`
* `feature_selection__threshold`

### 📈 **Insight:**

Random search improved performance from:

**0.6373 → 0.6669**

by efficiently exploring a wide parameter space.

---

### **2. 🔍 Grid Search**

I used **GridSearchCV** to exhaustively test all parameter combinations in a defined grid.

### **Parameters Tuned:**

* `C`
* `gamma`
* `kernel`

### 📈 **Insight:**

Grid search slightly outperformed random search:

**0.6669 → 0.6726**

---

## **Final Performance Comparison**

* **Baseline:** 0.6373
* **Random Search:** 0.6669
* **Grid Search:** 0.6726

---

## **Takeaways**

* Hyperparameter tuning improved model performance compared to baseline
* Grid Search achieved the best performance due to exhaustive evaluation
* Random Search provided competitive results with lower computational cost


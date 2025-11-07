# Contextual-Backorder-Prediction-for-Supply-Chain-Resilience

# Step 1 — Data Loading & Preprocessing

## 🎯 Objective
Simulate, clean, and prepare a large-scale supply chain dataset (~1.7M rows) for backorder prediction.

---

## 🧩 Steps Completed
1. Generated a realistic manufacturing dataset with:
   - Forecast, sales, and inventory metrics
   - Supply chain risk indicators
   - Target: `went_on_backorder`
2. Cleaned data (handled missing values)
3. Explored class imbalance (≈7% positive class)
4. Encoded categorical variables
5. Split data into train/test sets
6. Scaled features for model training

---

## 📁 Outputs
- `df`: Full preprocessed dataset
- `X_train_scaled`, `X_test_scaled`: Ready for ML modeling
- `y_train`, `y_test`: Target labels

---

# Step 2 — Feature Engineering & Imbalance Handling

## 🎯 Objective
Enhance predictive power by creating domain-based features, fix skewed distributions, and handle dataset imbalance.

---

## 🧩 Steps Completed
1. **Feature Engineering**
   - Created ratio and volatility-based features to reflect inventory-demand tension.
   - Derived a composite `risk_score` to capture manufacturing and supply risk.
2. **Feature Transformation**
   - Applied PowerTransformer for skewness correction.
3. **Class Imbalance Handling**
   - Used SMOTE to upsample minority (backorder) class → improved model fairness.
4. **Feature Insights**
   - Analyzed feature correlations to understand key drivers.
5. **Dimensionality Reduction (Optional)**
   - Applied PCA for stability and interpretability.

---

## 📁 Outputs
- `X_train_bal`, `y_train_bal`: Balanced feature set for model training
- `X_test_trans`, `y_test`: Validation set
- `X_train_pca`: Optional compressed version for interpretability

---

# Step 3 — Model Training & Evaluation

## 🎯 Objective
Train and evaluate multiple ML models to identify the best baseline for backorder prediction.

---

## 🧩 Steps Completed
1. **Model Setup**
   - Trained Logistic Regression, Decision Tree, Random Forest, and LightGBM.
2. **Performance Evaluation**
   - Compared Accuracy, Precision, Recall, F1-score, ROC-AUC.
   - Plotted ROC curves for visual comparison.
3. **Model Selection**
   - Selected best-performing model based on highest AUC and recall (typically LightGBM).
4. **Feature Importance**
   - Identified top contributing features impacting backorder risk.

---

## 📁 Outputs
- `metrics_df`: Comparison table of model scores
- `best_model`: Saved best classifier object
- `feature_importances.png`: Plot of top 15 features

---

## 🔮 Next Step (Day 4)
- Apply **SHAP-based Explainable AI (XAI)** for interpretability  
- Integrate RAG module to provide **natural language explanations** for predictions



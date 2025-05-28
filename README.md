# Atomcamp-Project04
This project predicts the chance of admission for applicants using various machine learning regression models. It focuses on model building, optimization, and interpretation.

# 🎓 Graduate Admission Prediction – Global Tech University (Regression Case Study)

## ✅ Final Case Study Summary

| Component                            | Details                                                                 |
|--------------------------------------|-------------------------------------------------------------------------|
| 📊 Dataset                           | Graduate Admission Data (400 records, 7 features + target)               
| 🧹 Data Cleaning                     | Verified no missing/null values. All columns cleaned and cast properly.  
| 📈 Baseline Model                    | Multiple Linear Regression (R² = **0.82**, RMSE = **0.068**)             
| 🔍 Multicollinearity Check           | Used **Variance Inflation Factor (VIF)** to detect collinearity.         
|   ⮡ Action Taken                      | No extreme multicollinearity found (VIF < 10), so all features retained. 
| 🌳 Decision Tree Regressor           | Initial R² = **0.78**; prone to overfitting without tuning                
|     ⮡ Hyperparameter Tuning          | Used **GridSearchCV** to find best `max_depth`, `min_samples_split`, etc. 
|     ⮡ Optimized Performance          | R² improved to **0.795**, RMSE = **0.073**                                
| 🌲 Random Forest Regressor           | Initial R² = **0.81**, RMSE = ~0.070                                    
|     ⮡ Hyperparameter Tuning          | Used **GridSearchCV** to search over `n_estimators`, `max_depth`, etc.  
|     ⮡  GridSearchCV                  | Accurate grid-based search is suitable due to the small feature space    
|     ⮡ Tuned Performance              | R² = **0.81**, stable with reduced error and overfitting                 
| ⭐ Feature Selection (RF Importance)| Top 5: `CGPA`, `GRE Score`, `TOEFL Score`, `University Rating`, `SOP`     
| 🔁 Re-trained Models on Top 5       | Linear (R² = 0.798), DT (R² = 0.778), RF (R² = 0.794) – still strong     
| 📈 Observation on Top 5 Features    | ✅ Simplified models with minimal accuracy loss; slightly reduced R² but improved generalization and interpretability. Ideal for deployment scenarios.                      
| 📉 Residual Analysis               | Random Forest residuals were evenly spread → model generalizes well       
| 🧪 Demo Applicant Test             | 🎓 Predicted Chance: 79.59% → ❌ No Scholarship                         
| 🎓 Scholarship Rule Applied        | IF (Admit > 0.8 AND CGPA > 8.5 AND Research == 1) → ✅ Scholarship       

---

## 📌 Key Modeling Decisions and Justifications

- **🔢 Multiple Linear Regression** was chosen as a baseline for interpretability. Coefficients helped identify key predictors.
- **📉 Multicollinearity** was tested using **VIF**. No predictors were dropped as all VIFs were below acceptable thresholds.
- **🌳 Decision Tree** provided non-linear modeling but needed **hyperparameter tuning** to prevent overfitting.
- **🌲 Random Forest** was chosen for its ensemble strength and robust performance. GridSearchCV was preferred over RandomizedSearchCV due to a manageable search space and the need for deterministic best-fit parameters.
- **🌟 Feature Selection** using feature importances from Random Forest helped simplify models while retaining strong accuracy.
- **📊 Residual Plots** were used to verify random error distribution, confirming models are not biased across prediction ranges.

---

## 🧠 Tools & Libraries Used

- `pandas`, `numpy`, `seaborn`, `matplotlib`
- `sklearn.linear_model`, `sklearn.tree`, `sklearn.ensemble`
- `sklearn.model_selection` for train-test splits and hyperparameter tuning
- `sklearn.metrics` for evaluation

---

### 📊 Models Trained & Performance

| Model                      | R² Score | RMSE      |
|---------------------------|----------|------------|
| Multiple Linear Regression | 0.82     | 0.0679    |
| Decision Tree Regressor    | 0.78     | -         |
| Decision Tree (Tuned)      | 0.795    | 0.0727    |
| Random Forest (Randomized) | 0.808    | -         |
| Random Forest (GridSearch) | 0.812    |  -        |
| Top 5 Features - Linear    | 0.798    | 0.0721    |
| Top 5 Features - DT    | 0.77    | 0.075    |
| Top 5 Features - RF        | 0.794    | 0.0728    |

## 📂 Included in this Notebook

- Exploratory Data Analysis & Cleaning  
- Baseline Model + Coefficient Analysis  
- Multicollinearity Detection (VIF)  
- Model Comparison: Linear, Decision Tree, Random Forest  
- Hyperparameter Optimization (GridSearchCV)  
- Feature Selection & Reduced Modeling  
- Residual Error Analysis  
- Demo Prediction with Scholarship Logic  




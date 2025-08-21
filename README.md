# Data_Science_Task1-Wise

# Customer Churn Prediction with Explainable AI

- This project predicts customer churn (whether a customer is likely to leave or stay) using multiple machine learning models and provides **explainable insights** with SHAP (SHapley values).  
- It is designed to help businesses not only identify customers at risk but also understand **why** they are likely to churn.

---

## Project Overview

- **Goal**: Predict customer churn and explain predictions in human-readable form.
- **Techniques**: Machine Learning classification + Explainable AI (SHAP).
- **Business Value**:  
  - Identify high-risk customers.  
  - Understand drivers of churn (e.g., high charges, low engagement).  
  - Provide actionable recommendations for retention strategies.


## Methodology

1. **Data Exploration**  
   - Checked for missing values, churn distribution, correlations.  
   - Visualized churn balance and feature relationships.  

2. **Feature Engineering**  
   - Derived features:    
     - `AvgTimeBetweenLogins = LastLoginDaysAgo / (LoginsLast30d + 1)`  
   - Encoded categorical variables with `LabelEncoder`.  

3. **Data Split & Scaling**  
   - Train-Test split (80/20, stratified).  
   - Standardized features with `StandardScaler`.  

4. **Model Training & Hyperparameter Tuning**  
   - Trained **9 models**: Logistic Regression, Decision Tree, Random Forest, Extra Trees, Gradient Boosting, AdaBoost, XGBoost, LightGBM, KNN.  
   - Used **GridSearchCV** for hyperparameter tuning.  

5. **Model Evaluation**  
   - Metrics: Accuracy, F1 Score, ROC-AUC.  
   - Selected the **best model** based on F1 Score & ROC-AUC.  

6. **Explainability with SHAP**  
   - Global Feature Importance (bar plots, beeswarm plots).  
   - Individual predictions (waterfall plots, force plots).  
   - Human-readable explanations with actionable insights.  

---

## Results

- **Best Model** : XGBoost(after tuning).  
- **Performance** :  
  - Accuracy: ~0.95050		  
  - F1 Score: ~0.917569  
  - ROC-AUC: ~0.984222  

**Global Feature Importance (SHAP)**
  
  The most influential factors driving churn risk are:
- AvgMonthlyUsageHours
- TotalSpend
- MonthlyCharges
- ActiveDaysLastMonth
- FailedPayments_12m 

---

## Business Insights

- Customers with **high charges and low engagement** are the most at risk.  
- **Unresolved support tickets** strongly increase churn risk.  
- **Loyalty factors** (long tenure, high total spend) protect against churn.  

**Recommendations:**  
- Offer targeted discounts for high-charge customers.  
- Re-engage low-usage customers with personalized campaigns.  
- Prioritize resolving support tickets quickly.  
- Encourage regular logins with reminders or gamification.  

---

## How to Run

1. pip install -r requirements.txt
2. jupyter notebook notebooks/churn_prediction.ipynb



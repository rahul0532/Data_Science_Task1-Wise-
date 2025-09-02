

# 📊 Predictive Customer Churn Model with XAI

## 📌 Project Overview

Customer churn is one of the biggest challenges for subscription-based businesses. This project builds a **machine learning pipeline** that predicts whether a customer is likely to churn (leave) and explains *why* the prediction was made using **Explainable AI (XAI)** tools like **SHAP** and **LIME**.

The goal is to:

* Detect customers who are likely to churn.
* Provide interpretable insights to help businesses **take preventive actions**.
* Deliver a **reproducible pipeline** from data preprocessing to model evaluation and explainability.

---

## 📂 Project Structure

```
├── dataset(G).csv                                # Synthetic dataset (~20,000 customers)
├── Predictive_Customer_Churn_Model_with_XAI.py   # Main project script
├── requirements.txt                              # Python dependencies
├── README.md                                     # Project documentation
```

---

## ⚙️ Features

✔️ **Exploratory Data Analysis (EDA)** – Handling missing values, duplicates, outliers, churn distribution.

✔️ **Feature Engineering** – Derived features like AvgRevnPerUser, AvgTimeBetweenLogins.

✔️ **Preprocessing** – OneHotEncoding for categorical variables, scaling for numerical ones.

✔️ **Model Training** – Logistic Regression, RandomForest, XGBoost, LightGBM compared.

✔️ **Model Evaluation** – F1-score, ROC-AUC, Confusion Matrix, Precision\@K.

✔️ **Explainability (XAI)** – SHAP summary plots & individual force plots.

✔️ **Deployment Ready** – Trained model saved with `joblib` for later use.

---

## 📊 Dataset

The dataset (`dataset(G).csv`) contains \~20,000 synthetic records with \~25 features:

* **Customer Info** : CustomerID, Gender, Age, Country, Plan, ContractType
* **Usage Metrics** : LoginsLast30d, AvgMonthlyUsageHours, ActiveDaysLastMonth
* **Engagement Metrics** : SupportTicketsPerMonth, Upgrades, Downgrades, IsPromoEligible
* **Financial Metrics** : MonthlyCharges, TotalSpend, PaymentDelayDays, FailedPayments\_12m
* **Target Variable** : `Churn` (0 = Retained, 1 = Churned)

⚠️ Note: `TotalSpend` and `NPS` values may contain **noise**; preprocessing steps are applied to normalize them.

---

## 🛠️ Installation

### 1️⃣ Clone the repository

```bash
git clone https://github.com/your-username/churn-prediction-xai.git
cd churn-prediction-xai
```

### 2️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Run the project

```bash
python Predictive_Customer_Churn_Model_with_XAI.py
```

---

## 📈 Model Evaluation

The best models are selected based on **F1-score** (important for imbalanced datasets).

* **Logistic Regression** – interpretable but limited power.
* **RandomForest / XGBoost / LightGBM** – high performance, handles non-linearities.

Metrics:

* **F1-score** → Balance between Precision & Recall.
* **ROC-AUC** → Overall discriminatory power.

---

## 🔎 Explainability (XAI)

Explainable AI methods used:

* **SHAP Summary Plot** – Global feature importance across customers.
* **SHAP Force Plot / Waterfall Plot** – Explains individual churn predictions.
* **LIME** (optional) – Local surrogate explanations.

Example:  A customer might churn due to **high support tickets, low activity, and high payment delays**.

---

## 📌 Results & Insights

* Features like **AvgMonthlyUsageHours and TotalSpend** are strong churn predictors.
* SHAP explanations show **TotalSpend** and **NPS** also influence churn, but sometimes act as noisy features.
* Preventive strategies:

  * Engage customers with declining usage.
  * Offer promotions to those with frequent payment delays.
  * Proactively address support issues.

---

## 🧑‍💻 Author

* **Rahul Raj**

  * 💼 B.Tech in CSE (AI & ML Specialization) – Alliance University, Bangalore
  * 🌱 Focus areas: Machine Learning, Explainable AI, Computer Vision
  * 📧 Contact: *\[Your email here]*
  * 🔗 GitHub: [rahul0532](https://github.com/rahul0532)

---

## 📜 License

This project is licensed under the **MIT License** – feel free to use and adapt it.

---

👉 Rahul, do you want me to also add **usage examples with code snippets** (e.g., how to load the saved model and predict churn for new customer data) inside the README?

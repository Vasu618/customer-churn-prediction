# 📊 Customer Churn Prediction & Retention Strategy System

<div align="center">
  <p><strong>A machine learning pipeline analyzing telecom customer data to understand churn, predict at-risk customers, and drive actionable retention strategies.</strong></p>
</div>

---

## 🚀 Project Overview

Customer churn is one of the most critical metrics for any subscription-based business. This project dives deep into telecom customer data to understand **why customers leave** and builds predictive models to identify **who is likely to leave next**. 

The goal is to help businesses make **data-driven decisions**, intervene early, improve customer retention, and reduce revenue loss.

## 🎯 Objectives
- **Identify** key factors and behaviors contributing to customer churn.
- **Build & Compare** robust machine learning models to predict churn probabilities.
- **Provide Actionable Insights** to stakeholders for designing effective retention strategies.

---

## 📈 Key Visualizations & Insights

The data analysis revealed several critical business insights. Below are some of the key drivers of churn identified by the model:

### 🔹 1. Churn by Contract Type
Customers on **month-to-month contracts** are the most vulnerable, exhibiting the highest churn rate (~42%). 
<br>
<img src="images/Churn_contract.png" alt="Churn vs Contract" width="600"/>

### 🔹 2. Churn by Tenure
The first year is the make-or-break period. Customers in their **first 12 months** show the highest churn (~47%).
<br>
<img src="images/Churn_tenure.png" alt="Churn vs Tenure" width="600"/>

### 🔹 3. Feature Importance
High monthly charges, fiber optic internet, and lack of online security were strongly linked to increased churn risk.
<br>
<img src="images/feature_importance.png" alt="Feature Importance" width="600"/>

### 🔹 4. Model Confusion Matrix
A breakdown of the model's classification performance, emphasizing our focus on correctly identifying actual churners.
<br>
<img src="images/confusion_matrix.png" alt="Confusion Matrix" width="400"/>

---

## 🤖 Models Used & Selection Strategy

* **Logistic Regression**
* **Random Forest** (Final Selected Model)
* **LazyPredict** (Automated benchmarking of 20+ models)

While `LazyPredict` showed that Logistic Regression achieved slightly higher overall accuracy (~80%), **Random Forest was ultimately selected** because it provided:
1. **Better Recall** for actual churn customers (minimizing false negatives).
2. Better handling of **non-linear relationships** in the dataset.
3. Strong **business interpretability** through clear feature importance rankings.

### Model Performance
| Model               | Accuracy |
| ------------------- | -------- |
| Logistic Regression | ~80%     |
| **Random Forest**   | **~78%** |

> ⚠️ **Note on Metrics:** Accuracy is not the only metric that matters. When predicting churn, **Recall** for the churn class (Class 1) is often more important to the business than overall accuracy, as failing to identify a churning customer results in lost revenue.

---

## 💡 Business Impact & Strategy

By deploying this model, the business can:
* **Identify high-risk customers early** and create early-warning systems.
* **Target retention strategies**: e.g., offering discounts to move month-to-month users to 1-year contracts.
* **Over-index on onboarding**: Focus heavily on customer service during the critical first 12 months.
* Ultimately **reduce customer churn and protect revenue**.

---

## 🔍 Key Learnings

* **Class imbalance** must be handled carefully; accuracy alone is misleading for churn problems.
* **Model interpretability** is just as important as predictive power when you need to convince stakeholders to make business changes.

---

## 🛠️ Tech Stack

* **Python** (Pandas, NumPy)
* **Visualization** (Matplotlib, Seaborn)
* **Machine Learning** (Scikit-learn, LazyPredict)
* **Environment** (Jupyter Notebook)

---

## 📂 Project Structure

* `Customer_Churn_Prediction_Retention_Strategy_System.ipynb` → Main analytical notebook containing EDA and model training.
* `ARCHITECTURE.md` → Technical design and pipeline methodology.
* `images/` → Output directory for visualizations.

---

## 🚀 Future Improvements

* **Hyperparameter Tuning:** Implement `GridSearchCV` to squeeze out higher recall.
* **Explainable AI:** Integrate **SHAP** values to explain exactly *why* an individual customer is at risk.
* **Deployment:** Wrap the model in a web application (Streamlit / Flask/ FastAPI) for real-time predictions.

---

## 👨‍💻 Author

**Jyoti Basu**

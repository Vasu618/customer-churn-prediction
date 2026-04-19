# Customer Churn Prediction & Retention Strategy System

## 📌 Project Overview
This project is an end-to-end Machine Learning pipeline designed to predict customer churn and provide actionable business insights for retention strategies. By analyzing customer data, the model identifies key behaviors and demographic profiles associated with high churn risk.

## 🚀 Features
- **Exploratory Data Analysis (EDA):** Visualizing patterns in customer tenure, contracts, and monthly charges.
- **Model Training:** Evaluating multiple models including Random Forest and Logistic Regression.
- **Automated Model Selection:** Using `LazyPredict` to benchmark 20+ ML models quickly.
- **Feature Importance & Interpretability:** Identifying the exact factors that drive customer churn (e.g., Month-to-month contracts, fiber optic internet, first 12 months of tenure).
- **Business Strategy Generation:** Translating ML metrics into concrete retention strategies for stakeholders.

## 🛠️ Technology Stack
- **Python 3**
- **Pandas & NumPy** (Data Manipulation)
- **Scikit-Learn** (Machine Learning & Evaluation)
- **LazyPredict** (Automated Model Benchmarking)
- **Matplotlib & Seaborn** (Data Visualization)
- **Jupyter Notebook** (Development Environment)

## 📊 Key Findings
1. **Contract Type:** Month-to-month contracts have the highest churn rate (~42%).
2. **Tenure:** The first 12 months are the most critical period for customer retention (highest churn risk).
3. **Model Performance:** Logistic Regression proved to be the best overall model (Accuracy: ~80%, F1-Score: ~80%), with high recall for detecting actual churners.

## ⚙️ How to Run Locally

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Vasu618/customer-churn-prediction.git
   cd customer-churn-prediction
   ```

2. **Set up a virtual environment:**
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows use `.venv\Scripts\activate`
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```
   Open `Customer_Churn_Prediction_Retention_Strategy_System.ipynb` to view the analysis.

## 🤝 Next Steps / Improvements
- Extract model logic into modular Python scripts (`train.py`, `predict.py`).
- Develop a REST API using FastAPI for real-time churn prediction.
- Implement SHAP (SHapley Additive exPlanations) for individual customer churn reasoning.

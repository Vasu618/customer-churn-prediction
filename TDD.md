# Technical Design Document (TDD) / Architecture

## 1. System Overview
The Customer Churn Prediction System is designed as an analytical machine learning pipeline. Its primary purpose is to process historical customer data, train classification algorithms to predict the probability of a customer canceling their service, and interpret the model features to generate actionable business insights.

## 2. Architecture & Pipeline Flow
The project follows a standard Data Science/Machine Learning pipeline:

### A. Data Ingestion & Preprocessing
- **Input:** Raw customer dataset (CSV format), typically containing demographic, service usage, and billing information.
- **Preprocessing:**
  - Handling missing values.
  - Encoding categorical variables (One-Hot Encoding / Label Encoding).
  - Feature scaling for linear models (StandardScaler/MinMaxScaler).
  - Handling class imbalance (if applicable, e.g., SMOTE).

### B. Exploratory Data Analysis (EDA)
- Statistical summaries of features.
- Univariate and bivariate analysis correlating features (like `tenure`, `Contract`) with the target variable (`Churn`).
- Output: Visualizations (saved in the `images/` directory) and derived insights.

### C. Model Training & Selection
- **Algorithm Candidates:** Logistic Regression, Random Forest, AdaBoost, SVC, etc.
- **Automated Benchmarking:** Using `LazyPredict` to quickly train and evaluate over 20 base models on metrics such as Accuracy, Balanced Accuracy, ROC AUC, and F1-Score.
- **Selected Model:** Logistic Regression was chosen for its high accuracy (~80%) and interpretability.

### D. Model Evaluation & Interpretability
- **Metrics:** Precision, Recall, F1-Score, and Confusion Matrix.
- **Interpretability:**
  - *Random Forest:* Uses `feature_importances_` to rank factors.
  - *Logistic Regression:* Analyzes coefficients to identify positive/negative correlations with churn.

### E. Strategy Generation
- Translating ML outputs into plain-English business rules (e.g., targeting customers in their first 12 months, or upselling 1-year contracts to month-to-month users).

## 3. Directory Structure
```
customer-churn-prediction/
│
├── Customer_Churn_Prediction_Retention_Strategy_System.ipynb  # Main ML pipeline notebook
├── README.md                                                  # Project overview and setup
├── ARCHITECTURE.md                                            # Technical design and methodology
├── requirements.txt                                           # Python dependencies
├── .gitignore                                                 # Ignored files/directories
├── .venv/                                                     # Virtual environment (ignored)
└── images/                                                    # Exported plots/visualizations
    ├── Churn_contract.png
    ├── Churn_tenure.png
    ├── confusion_matrix.png
    └── feature_importance.png
```

## 4. Future Architecture (Production Scope)
If this project is moved to production, the architecture should evolve into a microservices pattern:
1. **Model Training Service:** A scheduled job (e.g., Airflow/Cron) to retrain the model on fresh data and log artifacts using MLflow.
2. **Prediction API:** A REST API (FastAPI) serving the serialized model (e.g., `.pkl` or `.joblib`), exposing a `/predict` endpoint.
3. **Frontend Dashboard:** A UI (Streamlit or Next.js) where retention teams can input user IDs to see churn probabilities and SHAP-based explanations.

# 📡 Telco Customer Churn Prediction – Supervised Learning Pipeline

**Predicting customer churn using logistic regression, feature engineering, and model evaluation metrics.**

---

## 📌 Project Overview

This project implements a **data-driven churn prediction pipeline** for a telecommunications company using historical customer data.  
The goal is to **identify at-risk customers**, analyze churn drivers, and optimize retention strategies through **machine learning techniques**.  

Key objectives:

- Perform comprehensive **EDA and feature engineering**  
- Train and evaluate **Logistic Regression models**  
- Apply **hyperparameter tuning** to improve performance  
- Generate visualizations and performance metrics for actionable insights  

---

## 🎯 Objectives

- Clean and preprocess the Telco customer dataset  
- Engineer new features to capture customer behavior  
- Build a predictive model for churn classification  
- Evaluate performance using metrics like **accuracy, ROC AUC, and confusion matrices**  
- Provide insights into factors influencing customer churn  

---

## 📊 Dataset

**File:** `WA_Fn-UseC_-Telco-Customer-Churn.csv`  
**Source:** Public Telco customer churn dataset  

Key features include:

- Customer demographics (gender, senior citizen status, etc.)  
- Account information (tenure, contract type, payment method)  
- Service usage (InternetService, MonthlyCharges, TotalCharges)  
- Target variable: `Churn` (Yes/No)  

---

## 🛠 Data Preparation & Feature Engineering

1. **Data Cleaning**
   - Converted `TotalCharges` to numeric  
   - Filled missing numeric values with column mean  
   - Encoded `Churn` as binary (1 = Yes, 0 = No)  

2. **Feature Engineering**
   - Created `AvgMonthlySpend = TotalCharges / tenure`  
   - Binned `tenure` into categories: `0-12`, `12-24`, `24-36`, `36-48`, `48-60`, `60+`  
   - Dropped irrelevant columns (e.g., `customerID`)  

3. **Data Transformation**
   - Applied **StandardScaler** to numerical columns  
   - Applied **OneHotEncoder** to categorical columns  
   - Combined processed features into a **final dataset** ready for modeling  

4. **Exploratory Data Analysis**
   - Distribution of churn, gender, senior citizen status  
   - Boxplots for `tenure` and `MonthlyCharges` vs churn  
   - Stacked bar chart for `InternetService` vs churn  

---

## 🧠 Modeling Approach

### Logistic Regression

- Baseline classification model for predicting churn  
- Evaluated using:
  - Accuracy  
  - Confusion matrix  
  - Classification report (precision, recall, F1-score)  
  - ROC AUC score and ROC curve  

### Hyperparameter Tuning

- Used **GridSearchCV** to optimize the regularization parameter `C`  
- Retrained model with best hyperparameters to improve performance  

---

## 📈 Model Performance

| Metric | Baseline | Tuned Model |
|--------|---------|------------|
| Accuracy | 0.801 | 0.812 |
| ROC AUC | 0.857 | 0.869 |
| Precision | 0.735 | 0.746 |
| Recall | 0.620 | 0.639 |

**Key Insights:**

- High monthly charges and short tenure are associated with churn  
- Contract type and InternetService significantly affect churn probability  
- Model can be used for **targeted retention campaigns**  

---

## 🔍 Visualizations

- **Churn Distribution:** Bar chart  
- **Tenure vs Churn:** Box plot  
- **Monthly Charges vs Churn:** Box plot  
- **Internet Service vs Churn:** Stacked bar chart  
- **Confusion Matrices:** Heatmaps for baseline and tuned models  
- **ROC Curves:** Comparison of baseline and tuned model performance  

![Churn Distribution](churn_distribution.png)  
![Tenure Distribution](Tenure_distribution.png)  
![Monthly Charges Distribution](MonthlyCharges_Distribution.png)  
![ROC Curve](ROCCurve.png)  

---

## 📂 Project Structure

```text
Telco-Churn-Prediction/
│
├── data/                  # Raw dataset files
├── notebooks/             # EDA, preprocessing, and modeling notebooks
├── figures/               # Visualizations and plots
├── models/                # Saved trained models (churn_model.pkl)
├── processed_data/        # Transformed and feature-engineered datasets
├── reports/               # Confusion matrices, ROC curves, and metrics
└── README.md
````

---

## 🔮 Future Improvements

* Test **ensemble models** (Random Forest, XGBoost, Gradient Boosting) for improved performance
* Include additional behavioral features such as **service usage patterns**
* Automate model monitoring for **live churn prediction**
* Deploy a **dashboard for business stakeholders** with interactive insights

---

## ⚖ Ethical Considerations

* Customer privacy maintained; dataset contains anonymized information
* Predictions intended for **strategic decision-making**, not punitive actions
* Transparency in feature selection and modeling assumptions
* Responsible use to prevent bias in customer targeting

---

## 👤 Author

**Karthika Vellingiri**
Applied Data Science / AI Projects
DSC 680 Coursework

**Tools Used:** Python, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, IPython, Jupyter Notebook, Joblib

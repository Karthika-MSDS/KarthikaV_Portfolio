# ✈️ Airline Delay Prediction | Machine Learning Project

## 📌 Project Summary

Built an end-to-end machine learning solution to predict airline flight delays and identify operational risk factors using historical U.S. flight data.

This project demonstrates applied skills in:

* Data cleaning & feature engineering
* Classification & regression modeling
* Handling class imbalance
* Model evaluation & interpretation
* Business-focused storytelling

---

## 🎯 Business Objective

Flight delays lead to:

* Increased fuel and crew costs
* Disrupted scheduling
* Poor passenger experience

The goal was to:

* Predict whether a flight will be delayed (>15 minutes)
* Estimate expected delay duration
* Identify operational drivers of delays
* Provide actionable insights for airline planning teams

---

## 📊 Data Overview

* Source: Kaggle Airline Delay Dataset
* Years analyzed: 2018–2020
* Sampled 1,000 complete rows per year
* Removed cancelled and diverted flights

### Key Features Engineered

* Month
* Day of Week
* Departure Hour
* Time Block (Night / Morning / Afternoon / Evening)
* Distance
* Scheduled Elapsed Time

---

## 🧠 Modeling Approach

### Classification Model

* Algorithm: Random Forest Classifier
* Target: Delayed (Yes/No)
* Metrics:

  * Accuracy
  * Precision
  * Recall
  * ROC-AUC

### Regression Model

* Algorithm: Random Forest Regressor
* Target: Arrival Delay (minutes)
* Metrics:

  * MAE
  * RMSE

### Pipeline Implementation

* One-hot encoding for categorical variables
* Median imputation for numeric features
* Implemented using Scikit-learn Pipelines for reproducibility

---

## 📈 Key Insights

* Distance and scheduled flight time are strong delay predictors
* Certain time blocks show higher average delay risk
* Delay prediction is impacted by class imbalance (delays are less frequent)
* Operational patterns vary across carriers and time periods

---

## ⚠️ Challenges & Learnings

* Class imbalance resulted in low recall for delayed flights
* Future improvements could include:

  * SMOTE resampling
  * Class weighting
  * Threshold optimization
  * Hyperparameter tuning

This project strengthened my ability to balance predictive performance with real-world interpretability.

---

## 📊 Visual Outputs

Generated 7 analytical visualizations:

- Arrival delay distribution analysis
- Delay comparison by carrier
- Distance vs delay relationship
- Scheduled elapsed time vs delay relationship
- Average delay by day of week
- Average delay by time block
- Top 15 feature importance ranking

All visualizations are programmatically generated and saved to the `/figures` directory.
---

## 🛠 Tech Stack

* Python
* Pandas & NumPy
* Scikit-learn
* Matplotlib & Seaborn
* Joblib (Model Persistence)

---

## 🚀 What This Project Demonstrates

✔ End-to-end data science workflow
✔ Feature engineering from raw operational data
✔ Model development & evaluation
✔ Interpretability using feature importance
✔ Business-focused recommendations
✔ Clean, reproducible pipeline design


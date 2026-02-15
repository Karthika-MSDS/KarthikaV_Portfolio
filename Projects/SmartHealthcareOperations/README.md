# 🏥 Smart Healthcare Operations

**Leveraging AI for Efficient Staff Allocation and Patient Care**

## 📌 Project Overview

Healthcare systems face constant pressure to balance patient demand, staff availability, and bed capacity. Inefficient allocation can lead to long wait times, staff burnout, and patient refusals.

This project develops an **AI-driven predictive and prescriptive analytics framework** to:

* Forecast patient demand
* Optimize staff allocation
* Analyze absenteeism impact
* Simulate operational improvement scenarios

The goal is to support hospital administrators with **data-driven decision-making** that improves care delivery and operational efficiency.

---

## 🎯 Business Problem

Hospitals struggle with:

* Unpredictable patient inflow
* Limited bed capacity
* Staff absenteeism
* High patient refusal rates

Traditional planning methods often rely on static rules rather than data-driven forecasting.

This project answers:

* How can we predict patient demand accurately?
* How does staff absenteeism affect service delivery?
* What happens if we increase bed capacity?
* What operational interventions reduce patient refusals?

---

## 📊 Dataset

The project uses healthcare operations data including:

* Service type
* Available beds
* Staff count
* Absenteeism rate
* Historical patient demand
* Refusal counts

Data preprocessing included:

* Cleaning missing values
* Feature engineering
* Encoding categorical variables
* Train-test splitting

---

## 🧠 Modeling Approach

### 1️⃣ Demand Prediction (Regression)

* Model: Linear Regression
* Objective: Predict patient demand
* Evaluation: Mean Absolute Error (MAE)

Key features:

* Available beds
* Staff count
* Absenteeism rate
* Service type

---

### 2️⃣ Refusal Prediction (Classification)

* Model: Logistic Regression
* Objective: Predict likelihood of patient refusal
* Output: Probability-based risk estimation

---

## 🔍 Prescriptive Analytics (Scenario Simulation)

### Scenario 1: Increase Bed Capacity by 10%

* Reduced predicted refusal rates
* Improved patient accommodation

### Scenario 2: Improve Staff Morale (Reduced Absenteeism)

* Improved service efficiency
* Reduced patient backlog

### Scenario 3: Combined Intervention

* Significant reduction in patient refusals
* Improved operational stability

---

## 📈 Key Insights

* Higher absenteeism strongly correlates with increased refusals
* Bed capacity directly impacts service throughput
* Combined operational improvements yield exponential benefits
* Predictive modeling enables proactive planning instead of reactive decisions

---

## 🛠 Tools & Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## 📂 Project Structure

```
SmartHealthcareOperations/
│
├── data/
├── notebooks/
├── figures/
├── appendix
└── README.md
```

---

## 🚀 Business Impact

✔ Reduced predicted patient refusals
✔ Improved staffing efficiency
✔ Data-backed operational planning
✔ Supports scalable hospital management strategy

---

## 🔮 Future Improvements

* Implement advanced ensemble models (Random Forest, XGBoost)
* Integrate real-time hospital data streams
* Develop an interactive dashboard (Power BI / Streamlit)
* Incorporate cost-optimization modeling

---

## 👩‍💻 Author

**Karthika Vellingiri**
AI & Healthcare Analytics Enthusiast
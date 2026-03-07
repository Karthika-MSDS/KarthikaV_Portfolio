# 🏠 House Price Prediction Using Regression Models

**Predicting residential house prices using machine learning regression models**

---

## 📌 Project Overview

This project builds a **machine learning regression model** to predict house prices using the **Ames Housing Dataset**. The workflow includes:

- Data cleaning  
- Feature engineering  
- Exploratory data analysis (EDA)  
- Model training  
- Model evaluation  

The goal is to understand how different property features influence house prices and build a model that can accurately estimate the selling price of a home.

---

## 📊 Dataset

**Dataset:** Ames Housing Dataset  
**Source:** Real estate data for residential homes in Ames, Iowa  

The dataset contains multiple features describing houses, including:

- Property size  
- Number of rooms  
- Year built  
- Neighborhood  
- Garage information  
- Lot size  
- Structural characteristics  

**Target Variable:**  

`SalePrice` – The final sale price of the house.

---

## 🛠 Project Workflow

### 1️⃣ Data Preparation

#### Data Cleaning

- **Missing Value Handling**
  - `Lot Frontage`: filled using **median frontage of each neighborhood**  
  - Garage-related columns: filled with `"None"`  
  - `Mas Vnr Area`: missing values replaced with **0**  

- **Irrelevant Columns Removed**
  - PID  
  - Alley  
  - PoolQC  
  - Fence  
  - Misc Feature  

---

### 2️⃣ Feature Engineering

**Total Square Footage**

```

TotalSF = Gr Liv Area + 1st Flr SF + 2nd Flr SF

```

**House Age**

```

HouseAge = Yr Sold - Year Built

```

**Log Transformation**

- Target variable `SalePrice` log-transformed to reduce skewness and stabilize variance.

---

### 3️⃣ Encoding Categorical Variables

- One-hot encoding applied using:

```

pd.get_dummies()

```

This converts categorical values into binary indicator variables for modeling.

---

## 📊 Exploratory Data Analysis (EDA)

- **Sale Price Distribution:** distribution of log-transformed house prices  
- **Sale Price vs Living Area:** scatter plot for relationship between size and price  
- **Correlation Heatmap:** relationships between numerical variables and target  

---

## 🧠 Model Development

### Train-Test Split

- 80% Training Data  
- 20% Testing Data  

```

train_test_split(test_size=0.2, random_state=42)

```

### Feature Scaling

- StandardScaler applied to numerical features:

```

StandardScaler()

```

Ensures all features contribute equally to model training.

---

## 🤖 Machine Learning Model

### Linear Regression

**Why Linear Regression?**

- Simple and interpretable  
- Suitable for predicting continuous variables  
- Helps understand relationships between features and house prices  

---

## 📈 Model Evaluation

| Metric | Value |
| ------ | ------ |
| Mean Squared Error (MSE) | 1,163,680,288.30 |
| Mean Absolute Error (MAE) | 15,150.54 |
| R² Score | 0.8549 |

**Interpretation**

- **R² Score (0.8549):** explains ~85.49% of variance in house prices  
- **MAE:** predictions are ~\$15,150 away from actual prices on average  

---

## 📊 Model Visualization

- **Actual vs Predicted Prices:** scatter plot comparing predictions with true prices  
- **Residual Plot:** check for bias, variance patterns, and prediction errors  

Residuals should ideally scatter randomly around zero.

---

## 🛠 Tools & Technologies

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Matplotlib  
- Seaborn  
- Tabulate  
- Jupyter Notebook  

---

## 📂 Project Structure

```

HousePricePrediction/
│
├── data/          # raw and processed datasets
├── notebooks/     # Jupyter notebooks with EDA and modeling
├── figures/       # visualizations and plots
├── appendix/      # additional analysis, code snippets
└── README.md

```

---

## 🔍 Results

- Linear Regression model achieved strong predictive performance  
- Explains over 85% of variance in house prices  
- Residual analysis indicates some nonlinear relationships remain  

---

## 🔮 Future Improvements

**Advanced Models**

- Random Forest Regressor  
- Gradient Boosting  
- XGBoost  

**Additional Feature Engineering**

- Interaction features  
- Location-based price indicators  
- Renovation/remodeling variables  

**Cross-Validation**

- Apply k-fold cross-validation to improve reliability and reduce overfitting  

**Regularization**

- Ridge Regression  
- Lasso Regression  
- Improve generalization of the model  

---

## 🚀 Business Impact

- Provides actionable insights for real estate pricing  
- Helps identify key property features affecting price  
- Establishes baseline model for more advanced predictions  

---

## 👤 Author

**Karthika Vellingiri**  

**Tools Used:** Python, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, Tabulate, Jupyter Notebook
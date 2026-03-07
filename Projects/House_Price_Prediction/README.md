# House Price Prediction Using Regression Models

## Project Overview
This project builds a **machine learning regression model** to predict house prices using the **Ames Housing Dataset**. The workflow includes **data cleaning, feature engineering, exploratory data analysis (EDA), model training, and evaluation**.  

The goal is to understand how different property features influence house prices and build a model that can accurately estimate the selling price of a home.

---

# Dataset
**Dataset:** Ames Housing Dataset  
**Source:** Real estate data for residential homes in Ames, Iowa.

The dataset contains **multiple features describing houses**, including:

- Property size
- Number of rooms
- Year built
- Neighborhood
- Garage information
- Lot size
- Structural characteristics

**Target Variable**

`SalePrice` – The final sale price of the house.

---

# Project Workflow

## 1. Data Preparation

### Data Cleaning
Several preprocessing steps were performed to ensure high data quality:

- **Missing Value Handling**
  - `Lot Frontage` values were filled using the **median frontage of each neighborhood**
  - Garage-related categorical columns were filled with `"None"`
  - `Mas Vnr Area` missing values were replaced with **0**

- **Irrelevant Columns Removed**
  The following columns were dropped because they provide limited predictive value:

  - PID
  - Alley
  - PoolQC
  - Fence
  - Misc Feature

---

## 2. Feature Engineering

To improve model performance, additional features were created:

### Total Square Footage
A new feature **TotalSF** was created by combining:

- Ground Living Area
- First Floor Area
- Second Floor Area

```
TotalSF = Gr Liv Area + 1st Flr SF + 2nd Flr SF
```

### House Age
Calculated the age of the house when sold:

```
HouseAge = Yr Sold - Year Built
```

### Log Transformation
The target variable **SalePrice** was **log-transformed** to reduce skewness and stabilize variance.

---

## 3. Encoding Categorical Variables

Machine learning models require numerical inputs, so **one-hot encoding** was applied to all categorical variables using:

```
pd.get_dummies()
```

This converts categorical values into binary indicator variables.

---

# Exploratory Data Analysis (EDA)

Several visualizations were generated to understand the data:

### Sale Price Distribution
Shows the distribution of the log-transformed house prices.

### Sale Price vs Living Area
A scatter plot to observe the relationship between **house size and price**.

### Correlation Heatmap
Displays relationships between numerical variables and highlights features strongly correlated with the target variable.

---

# Model Development

## Train-Test Split

The dataset was split into:

- **80% Training Data**
- **20% Testing Data**

```
train_test_split(test_size=0.2, random_state=42)
```

---

## Feature Scaling

Standardization was applied using:

```
StandardScaler()
```

Scaling ensures that all features contribute equally to model training.

---

# Machine Learning Model

## Linear Regression

The project uses **Linear Regression** as the baseline model.

### Why Linear Regression?

- Simple and interpretable
- Suitable for predicting continuous variables
- Helps understand relationships between features and house prices

---

# Model Evaluation

The model was evaluated using three common regression metrics.

| Metric | Value |
|------|------|
| Mean Squared Error (MSE) | 1,163,680,288.30 |
| Mean Absolute Error (MAE) | 15,150.54 |
| R² Score | 0.8549 |

### Interpretation

**R² Score (0.8549)**  
The model explains approximately **85.49% of the variance** in house prices, indicating strong predictive performance.

**MAE**  
On average, the model predictions are approximately **$15,150 away from actual prices**.

---

# Model Visualization

### Actual vs Predicted Prices
Scatter plot comparing predicted prices with true house prices.

### Residual Plot
Residual analysis helps check:

- Model bias
- Variance patterns
- Prediction errors

Ideally, residuals should be randomly scattered around zero.

---

---

# Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Tabulate
- Jupyter Notebook

---

# Results

The Linear Regression model achieved **strong predictive performance**, explaining over **85% of the variance in house prices**.  

However, the residual analysis suggests that some nonlinear relationships remain unexplained.

---

# Future Improvements

To further improve the model:

### Use Advanced Models
- Random Forest Regressor
- Gradient Boosting
- XGBoost

### Add More Feature Engineering
Examples include:

- Interaction features
- Location-based price indicators
- Renovation or remodeling variables

### Use Cross-Validation
Applying **k-fold cross-validation** will help improve model reliability and reduce overfitting.

### Regularization
Use techniques like:

- Ridge Regression
- Lasso Regression

to improve generalization.

---

# Conclusion

This project demonstrates the complete **data science pipeline**, including data preprocessing, feature engineering, regression modeling, and evaluation.

The **Linear Regression model provides strong baseline performance**, and future improvements using ensemble models could further increase prediction accuracy.

---

# Author

**Karthika Vellingiri**  
Applied Data Science Projects 
Machine Learning | Predictive Modeling | Data Analytics
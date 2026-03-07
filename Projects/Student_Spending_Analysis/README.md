# Student Spending Analysis: Data Cleaning, Visualization, and Statistical Modeling

## 📌 Project Overview

This project explores **student spending patterns** using a structured **data analytics workflow**. The main objectives are to:

- Clean and preprocess student spending data
- Handle missing values and outliers
- Conduct descriptive and visual analytics
- Examine relationships between financial aid, income, and spending
- Perform statistical testing and regression modeling

The analysis provides insights into **essential vs. discretionary spending**, income correlations, and factors affecting miscellaneous expenses.

---

## 🗂 Dataset

- **File:** `student_spending.csv`  
- **Contents:** Student demographics and monthly spending across multiple categories such as tuition, housing, food, transportation, books, entertainment, personal care, technology, health & wellness, and miscellaneous expenses.

---

## ⚙️ Project Workflow

### 1. Data Cleaning and Outlier Handling
- Loaded CSV data using `pandas`.
- Replaced infinite values with `NaN` and removed rows with null values.
- Detected and removed outliers using the **Interquartile Range (IQR) method** for numeric columns:

```python
numeric_columns = ['monthly_income', 'tuition', 'housing', 'food', 'transportation', 
                   'books_supplies', 'entertainment', 'personal_care', 'technology', 
                   'health_wellness', 'miscellaneous']
````

* Columns with outliers are reported to the user.
* Reset DataFrame index after cleaning.

---

### 2. Descriptive Statistics and Visualization

* Histograms and **Kernel Density Estimates (KDE)** for numeric columns.
* Frequency distributions for categorical columns (`gender`, `year_in_school`, `major`).
* Key metrics computed:

  * Mean, Median, Mode
  * Standard Deviation, Variance
  * Skewness, Kurtosis
  * Quartiles (Q1, Q3), IQR, Tails
  * Mode frequency, unique values, missing entries for categorical variables

Example columns analyzed:

```python
columns_to_plot = ['age', 'gender', 'year_in_school', 'major', 
                   'monthly_income', 'financial_aid', 'tuition']
```

---

### 3. Spending Analysis

* Aggregated **Essential Spending**:

```python
essential_categories = ['housing', 'food', 'transportation', 'books_supplies']
df['essential_spending'] = df[essential_categories].sum(axis=1)
```

* Aggregated **Discretionary Spending**:

```python
discretionary_categories = ['entertainment', 'personal_care', 
                            'technology', 'health_wellness', 'miscellaneous']
df['discretionary_spending'] = df[discretionary_categories].sum(axis=1)
```

* **PMF (Probability Mass Function)** plotted for both spending types side by side.
* **CDF (Cumulative Distribution Function)** plotted for monthly income.
* **Normal distribution fitting** applied to monthly income to examine theoretical distribution.

---

### 4. Relationship Analysis

* **Scatter Plots and Correlation:**

  * Financial Aid vs Tuition
  * Monthly Income vs Essential Spending
* **Statistics reported:**

  * Covariance
  * Pearson correlation coefficient
  * Trend lines using regression plots

---

### 5. Hypothesis Testing

* **Permutation Test** to compare mean spending between **essential** and **discretionary** categories:

```python
# Null hypothesis (H0): No significant difference
# Alternative hypothesis (H1): Significant difference
```

* P-value, observed difference, and permutation differences computed.
* Decision rule applied at α = 0.05 to accept or reject the null hypothesis.

---

### 6. Regression Modeling

* **Multiple Linear Regression** using `statsmodels`:

  * Dependent variable: `miscellaneous` spending
  * Independent variables: `age`, `year_in_school`, `monthly_income`, `tuition`
* Model fitted using **Ordinary Least Squares (OLS)**
* Model summary includes:

  * Coefficients and p-values
  * R-squared and adjusted R-squared
  * Standard errors and confidence intervals

---

## 🔍 Key Insights

* Essential spending consistently accounts for the largest share of student expenses.
* Strong correlation observed between financial aid and tuition.
* Monthly income shows moderate correlation with essential spending.
* Permutation tests indicate whether the difference between essential and discretionary spending is statistically significant.
* Regression analysis identifies factors significantly influencing miscellaneous spending.

---

## 🛠 Dependencies

* Python 3.x
* pandas
* numpy
* matplotlib
* seaborn
* scipy
* statsmodels
* IPython (for HTML display in notebooks)

---

## 📊 Usage

1. Place `student_spending.csv` in the project folder.
2. Run the Python scripts or Jupyter Notebook in the following sequence:

   * `clean_data()` → handle missing values and outliers
   * `describe_and_plot()` → generate descriptive statistics and histograms
   * Spending aggregation and PMF/CDF plotting
   * Scatter plots and correlation analysis
   * Permutation testing for hypothesis validation
   * Regression modeling for miscellaneous spending analysis
3. Review outputs and plots for insights.

---

## 📝 References

* [Pandas Documentation](https://pandas.pydata.org/)
* [Seaborn Documentation](https://seaborn.pydata.org/)
* [SciPy Stats](https://docs.scipy.org/doc/scipy/reference/stats.html)
* [Statsmodels Regression Analysis](https://www.statsmodels.org/)

---

## 🔗 Author

**Karthika Vellingiri**
Applied Data Analytics – Statistical & Data Science Workflow

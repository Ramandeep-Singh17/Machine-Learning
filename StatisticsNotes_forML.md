# 📊 Statistics for Machine Learning

> Comprehensive and ML-focused guide to Statistics with key concepts, formulas, explanations, and examples.

---

## 📌 Table of Contents

1. [Descriptive Statistics](#1-descriptive-statistics)
2. [Measures of Central Tendency](#2-measures-of-central-tendency)
3. [Measures of Dispersion](#3-measures-of-dispersion)
4. [Skewness & Kurtosis](#4-skewness--kurtosis)
5. [Standardization & Normalization](#5-standardization--normalization)
6. [Outliers & Z-Score](#6-outliers--z-score)
7. [Correlation vs Covariance](#7-correlation-vs-covariance)
8. [ANOVA](#8-anova)
9. [Chi-Square Test](#9-chi-square-test)
10. [Tips & Real-World Examples](#10-tips--real-world-examples)

---

## 1. 📈 Descriptive Statistics

**Purpose**: Summarize and describe data.

* **Types**:

  * Central tendency (mean, median, mode)
  * Dispersion (range, variance, standard deviation)

```python
import numpy as np
import pandas as pd

data = [10, 20, 30, 40, 50]
np.mean(data), np.median(data), pd.Series(data).mode()
```

---

## 2. 📍 Measures of Central Tendency

| Metric | Use Case      | ML Use                  | Formula                         |
| ------ | ------------- | ----------------------- | ------------------------------- |
| Mean   | Avg           | Used in feature scaling | \$\mu = \frac{\Sigma x\_i}{n}\$ |
| Median | Middle        | Handles skewed data     | Middle value                    |
| Mode   | Most frequent | Categorical data        | Most freq. value                |

> **ML Tip**: Use median when outliers are present (robust).

---

## 3. 📏 Measures of Dispersion

* **Range**: `max - min`
* **Variance**: Spread of data
* **Standard Deviation**: Square root of variance

```python
np.std(data), np.var(data)
```

> **In ML**: High std → spread out data → affects model stability

---

## 4. 🧭 Skewness & Kurtosis

* **Skewness**: Symmetry of data

  * `0` → symmetric
  * `> 0` → right-skewed
  * `< 0` → left-skewed

* **Kurtosis**: Tails of the distribution

  * High kurtosis → more outliers

```python
from scipy.stats import skew, kurtosis
skew(data), kurtosis(data)
```

---

## 5. 📐 Standardization & Normalization

| Method          | Range            | Use                           |
| --------------- | ---------------- | ----------------------------- |
| Standardization | Mean = 0, SD = 1 | Algorithms like SVM, KNN      |
| Normalization   | \[0,1]           | Image processing, neural nets |

```python
# StandardScaler
from sklearn.preprocessing import StandardScaler
X_scaled = StandardScaler().fit_transform(X)

# MinMaxScaler
from sklearn.preprocessing import MinMaxScaler
X_norm = MinMaxScaler().fit_transform(X)
```

> 🔎 **Standardized data mostly lies between -3 to +3**

---

## 6. ⚠️ Outliers & Z-Score

* **Outlier**: Data point far from other values
* **Z-Score**:

  * Formula: \$z = \frac{(x - \mu)}{\sigma}\$
  * If \$|z| > 3\$ → likely outlier

```python
from scipy import stats
z = np.abs(stats.zscore(df))
df_outliers = df[(z < 3).all(axis=1)]
```

> Use boxplots, IQR method, or Z-score for outlier detection.

---

## 7. 🔄 Correlation vs Covariance

| Property | Correlation       | Covariance       |
| -------- | ----------------- | ---------------- |
| Range    | \[-1, 1]          | -∞ to ∞          |
| Scale    | Standardized      | Not standardized |
| ML Use   | Feature selection | PCA              |

```python
# Correlation
corr_matrix = df.corr(numeric_only=True)

# Covariance
cov_matrix = df.cov()
```

---

## 8. 📊 ANOVA (Analysis of Variance)

* Compares means across 3+ groups
* Tests **whether differences are significant**

```python
from scipy.stats import f_oneway
f_oneway(group1, group2, group3)
```

> In ML, used for **feature selection**

---

## 9. 🧪 Chi-Square Test

* Tests independence between categorical variables

```python
from scipy.stats import chi2_contingency
chi2_contingency(pd.crosstab(df['Gender'], df['Purchase']))
```

> In ML, used in feature selection for classification

---

## 10. 💡 Tips & Real-World Examples

* **Always check for outliers before training**
* **Standardize features when using distance-based models** (KNN, SVM)
* **Visualize distributions using histograms/boxplots**
* Use `sklearn.feature_selection.SelectKBest` with `f_classif` or `chi2` for stat-based feature selection

---

## ✅ Recommended Tools & Libraries

* `NumPy`, `Pandas`
* `scipy.stats`, `statsmodels`
* `sklearn.preprocessing`, `sklearn.feature_selection`

---

## 📌 Summary

> Statistical understanding is the backbone of data preprocessing and model performance in ML. Master these to build reliable models.

---




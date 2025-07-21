# 📊 Statistics for Machine Learning (Hinglish)

> Ekdam clear aur ML-focused guide to statistics — saare concepts short, crisp, aur real-life + ML examples ke sath.

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

**Use**: Data ko summarize aur describe karna.

* **Types**:

  * Central Tendency (mean, median, mode)
  * Dispersion (range, std dev, variance)

```python
import numpy as np
import pandas as pd

data = [10, 20, 30, 40, 50]
np.mean(data), np.median(data), pd.Series(data).mode()
```

---

## 2. 📍 Measures of Central Tendency

| Metric | Kya karta hai | ML Me Use                  | Formula                       |
| ------ | ------------- | -------------------------- | ----------------------------- |
| Mean   | Average       | Feature scaling me         | \$μ = \frac{\Sigma x\_i}{n}\$ |
| Median | Middle value  | Skewed data ke liye better | Middle value                  |
| Mode   | Most frequent | Categorical data me        | Most frequent value           |

> **ML Tip**: Median better hota hai jab outliers ho.

---

## 3. 📏 Measures of Dispersion

* **Range**: `max - min`
* **Variance**: Kitna spread hai
* **Standard Deviation (SD)**: Variance ka square root

```python
np.std(data), np.var(data)
```

> High SD → zyada spread → model par effect padta hai

---

## 4. 🧭 Skewness & Kurtosis

* **Skewness**: Data symmetric hai ya nahi

  * `0` → perfect symmetric
  * `> 0` → right skewed (tail right side)
  * `< 0` → left skewed

* **Kurtosis**: Tails aur outliers kitne zyada hain

  * High kurtosis → zyada outliers

```python
from scipy.stats import skew, kurtosis
skew(data), kurtosis(data)
```

---

## 5. 📐 Standardization & Normalization

| Method          | Range            | Kaha Use Hota Hai       |
| --------------- | ---------------- | ----------------------- |
| Standardization | Mean = 0, SD = 1 | SVM, KNN jaise algo     |
| Normalization   | \[0,1]           | Neural nets, Image data |

```python
# StandardScaler
from sklearn.preprocessing import StandardScaler
X_scaled = StandardScaler().fit_transform(X)

# MinMaxScaler
from sklearn.preprocessing import MinMaxScaler
X_norm = MinMaxScaler().fit_transform(X)
```

> 🔎 **Standardized data mostly -3 to +3 ke beech hota hai**

---

## 6. ⚠️ Outliers & Z-Score

* **Outlier**: Aise points jo sabse alag hoon
* **Z-Score**:

  * Formula: \$z = \frac{(x - \mu)}{\sigma}\$
  * Agar \$|z| > 3\$ hai → outlier hai

```python
from scipy import stats
z = np.abs(stats.zscore(df))
df_outliers = df[(z < 3).all(axis=1)]
```

> Boxplot, IQR, aur Z-Score se outliers pakad sakte hain

---

## 7. 🔄 Correlation vs Covariance

| Property | Correlation       | Covariance          |
| -------- | ----------------- | ------------------- |
| Range    | \[-1, 1]          | -∞ to ∞             |
| Scale    | Standardized      | Not standardized    |
| ML Me    | Feature selection | PCA me use hota hai |

```python
# Correlation
corr_matrix = df.corr(numeric_only=True)

# Covariance
cov_matrix = df.cov()
```

---

## 8. 📊 ANOVA (Analysis of Variance)

* 3 ya zyada groups ke means ko compare karta hai
* Dekhta hai ki kya difference significant hai ya nahi

```python
from scipy.stats import f_oneway
f_oneway(group1, group2, group3)
```

> ML me **feature selection** ke liye use hota hai

---

## 9. 🧪 Chi-Square Test

* Categorical variables ke beech dependency check karta hai

```python
from scipy.stats import chi2_contingency
chi2_contingency(pd.crosstab(df['Gender'], df['Purchase']))
```

> ML me classification problems ke liye feature selection me use hota hai

---

## 10. 💡 Tips & Real-World Examples

* 🔍 Model train karne se pehle outliers check karo
* 📏 Distance-based models (KNN, SVM) ke liye standardization zaroori hai
* 📊 Visualizations like boxplot aur histogram help karte hain
* 🧠 Use `SelectKBest` + `chi2` ya `f_classif` for stat-based feature selection

---

## ✅ Recommended Tools & Libraries

* `NumPy`, `Pandas`
* `scipy.stats`, `statsmodels`
* `sklearn.preprocessing`, `sklearn.feature_selection`

---

## 📌 Summary

> Agar tumhe ML models banane hain to statistics ka strong base zaroori hai — ye sari cheeze preprocessing, feature selection, aur analysis me kaam aati hain.

---


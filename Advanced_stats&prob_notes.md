# 📊 Advanced Statistics & Probability for Machine Learning – Part 2

> **Level**: Intermediate to Advanced
> **Goal**: Boost your ML interviews, A/B testing skills, and real project intuition

---

## 📌 Table of Contents

1. [Hypothesis Testing (Z-Test, T-Test)](#1-hypothesis-testing-z-test-t-test)
2. [p-value & Statistical Significance](#2-p-value--statistical-significance)
3. [Confidence Intervals](#3-confidence-intervals)
4. [Central Limit Theorem](#4-central-limit-theorem)
5. [Law of Large Numbers](#5-law-of-large-numbers)
6. [Chi-Square Test](#6-chi-square-test)
7. [ANOVA (Analysis of Variance)](#7-anova-analysis-of-variance)
8. [Covariance vs Correlation](#8-covariance-vs-correlation)
9. [Bayes Theorem](#9-bayes-theorem)
10. [Entropy & Information Gain](#10-entropy--information-gain)
11. [KL Divergence & Cross Entropy](#11-kl-divergence--cross-entropy)
12. [Key Distributions](#12-key-distributions)
13. [Sampling Techniques](#13-sampling-techniques)
14. [Bias-Variance Tradeoff](#14-bias-variance-tradeoff)
15. [Outliers & Influence Points](#15-outliers--influence-points)

---

## 1. Hypothesis Testing (Z-Test, T-Test)

* **What**: Statistical method to compare groups and validate assumptions
* **When**: Model improvements, A/B testing, feature impact analysis
* **Why**: Ensures ML decisions aren't based on random chance
* **Use in ML**: Testing model improvements, user experiments

```python
from scipy.stats import ttest_ind
sample1 = [23, 21, 18, 25, 22]
sample2 = [30, 28, 27, 35, 33]
t_stat, p_val = ttest_ind(sample1, sample2)
```

---

## 2. p-value & Statistical Significance

* **p-value < 0.05** → statistically significant result
* Helps reject the **null hypothesis**

🧠 **ML Example**: Testing if two models have significantly different RMSE

---

## 3. Confidence Intervals

* **What**: Range of values where the true parameter lies
* **Use**: Model predictions, test results interpretation
* **Example**: "Model accuracy is 85% ± 2%"

```python
import scipy.stats as st
conf_interval = st.norm.interval(0.95, loc=85, scale=2)
```

---

## 4. Central Limit Theorem (CLT)

* Aggregated means of samples ≈ normal distribution
* **Use in ML**: Any sampling-based technique, bootstrapping

---

## 5. Law of Large Numbers

* More data = more stable and true average
* Important in model training → more data = better model generalization

---

## 6. Chi-Square Test

* Tests dependency between **categorical variables**
* **ML Use**: Feature selection, independence test

```python
from scipy.stats import chi2_contingency
obs = [[50, 30], [20, 80]]
chi2, p, dof, expected = chi2_contingency(obs)
```

---

## 7. ANOVA (Analysis of Variance)

* Compares 2+ groups (means)
* **ML Use**: Model comparisons, group performance

```python
from scipy.stats import f_oneway
f_stat, p_val = f_oneway(group1, group2, group3)
```

---

## 8. Covariance vs Correlation

| Term        | Meaning                        | Use in ML              |
| ----------- | ------------------------------ | ---------------------- |
| Covariance  | How 2 variables change         | Raw relation           |
| Correlation | Scaled (–1 to +1) relationship | Feature selection, EDA |

---

## 9. Bayes Theorem

$P(A|B) = \frac{P(B|A) \times P(A)}{P(B)}$

* **Use in ML**: Naive Bayes, spam detection, probabilistic models

---

## 10. Entropy & Information Gain

* **Entropy**: Measure of randomness/uncertainty
* **Information Gain**: How much entropy was reduced by a feature
* **ML Use**: Decision trees (ID3, CART)

---

## 11. KL Divergence & Cross Entropy

* **KL Divergence**: Measure difference between two distributions
* **Cross Entropy**: Used as loss in classification

```python
from scipy.special import rel_entr
kl = sum(rel_entr(P, Q))
```

---

## 12. Key Distributions

| Distribution | When to Use              | Use in ML             |
| ------------ | ------------------------ | --------------------- |
| Bernoulli    | Single binary event      | Binary classification |
| Binomial     | # of successes in trials | A/B testing           |
| Poisson      | Count events/time        | Arrival rates         |
| Gaussian     | Natural continuous data  | Linear regression     |

---

## 13. Sampling Techniques

* **Simple Random**, **Stratified**, **Bootstrapping**
* ML Use: Better generalization, confidence intervals

---

## 14. Bias-Variance Tradeoff

| Term     | Meaning                  |
| -------- | ------------------------ |
| Bias     | Error due to assumptions |
| Variance | Error due to sensitivity |

* **Goal**: Find best balance (not too biased or too varied)

---

## 15. Outliers & Influence Points

* Can break models (especially regression)
* Use **boxplot**, **IQR**, **Z-score** to detect

```python
from scipy import stats
z_scores = stats.zscore(data)
outliers = data[(z_scores > 3)]
```

---

## ✅ Conclusion

This part completes the **core + advanced** statistics & probability foundation for Machine Learning.

> 

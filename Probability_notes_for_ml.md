# 🎲 Probability for Machine Learning (English)

> A crystal-clear and ML-oriented guide to **Probability** — all essential concepts with real-world and ML examples in short, crisp format.

---

## 📌 Table of Contents

1. [What is Probability?](#1-what-is-probability)
2. [Types of Probability](#2-types-of-probability)
3. [Basic Probability Rules](#3-basic-probability-rules)
4. [Conditional Probability](#4-conditional-probability)
5. [Bayes’ Theorem](#5-bayes-theorem)
6. [Probability Distributions](#6-probability-distributions)
7. [Bernoulli & Binomial Distribution](#7-bernoulli--binomial-distribution)
8. [Normal Distribution](#8-normal-distribution)
9. [Central Limit Theorem (CLT)](#9-central-limit-theorem-clt)
10. [Applications in ML](#10-applications-in-ml)

---

## 1. 🎯 What is Probability?

**Probability** measures the likelihood of an event occurring.

* Formula: ( P(E) = \frac{Favorable\ outcomes}{Total\ outcomes} \ )
* Range: ( 0 \leq P(E) \leq 1 \ )

> Example: Probability of getting heads in a coin toss = 0.5

---

## 2. 📂 Types of Probability

| Type         | Description                   |
| ------------ | ----------------------------- |
| Theoretical  | Based on logical reasoning    |
| Experimental | Based on actual trials        |
| Axiomatic    | Based on set rules and axioms |

---

## 3. ⚖️ Basic Probability Rules

* **Addition Rule** (OR): ( P(A \cup B) = P(A) + P(B) - P(A \cap B) \ )
* **Multiplication Rule** (AND): ( P(A \cap B) = P(A) \cdot P(B|A) \ )
* **Complement Rule**: ( P(A') = 1 - P(A) \ )

> Used in decision trees, naive bayes, etc.

---

## 4. 🔄 Conditional Probability

Probability of A given B has already occurred:

\[ P(A|B) = \frac{P(A \cap B)}{P(B)} \ ]

> Important in Naive Bayes, recommender systems, etc.

---

## 5. 🧠 Bayes’ Theorem

Bayes' Rule allows reversing conditional probabilities:

\[ P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)} \ ]

* **Prior**: P(A)
* **Likelihood**: P(B|A)
* **Posterior**: P(A|B)

> Very useful in spam filtering, disease prediction, etc.

---

## 6. 🧾 Probability Distributions

Describes how probabilities are distributed over values:

* **Discrete** → Finite outcomes (Bernoulli, Binomial)
* **Continuous** → Infinite outcomes (Normal, Exponential)

---

## 7. ⚪ Bernoulli & Binomial Distribution

* **Bernoulli**: 1 trial, 2 outcomes (e.g., success/failure)
* **Binomial**: n independent Bernoulli trials

```python
from scipy.stats import bernoulli, binom
bernoulli.pmf(1, 0.5)
binom.pmf(2, 5, 0.5)  # 2 successes in 5 trials with p=0.5
```

> Used in binary classification, A/B testing

---

## 8. 📊 Normal Distribution

* Bell-shaped curve
* Mean = Median = Mode
* 68-95-99.7 Rule:

  * 68% data within 1 std dev
  * 95% within 2
  * 99.7% within 3

```python
from scipy.stats import norm
norm.pdf(0, loc=0, scale=1)  # Standard normal
```

> Assumption in many ML models (e.g., Linear Regression)

---

## 9. 🔁 Central Limit Theorem (CLT)

> Sample means from any distribution will tend to follow a normal distribution if sample size is large enough (n > 30).

* Helps justify using normal assumptions in hypothesis testing.

---

## 10. 🤖 Applications in ML

* **Naive Bayes** → Conditional Probabilities
* **Logistic Regression** → Based on Sigmoid (probability curve)
* **Random Forest / XGBoost** → Use probability of class
* **Uncertainty estimation** → Confidence intervals, error ranges

---

## ✅ Summary

> Understanding Probability is foundational for machine learning — from model assumptions to feature engineering and real-world applications like fraud detection, search ranking, and medical diagnosis.

---


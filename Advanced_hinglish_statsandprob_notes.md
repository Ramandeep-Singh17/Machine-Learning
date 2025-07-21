# 📊 Statistics + 🎲 Probability for Machine Learning (Hinglish)

> Crystal-clear, beginner-friendly Hinglish notes for ML — 📘 **GitHub-ready**, markdown styled with real-world ML examples.

---

## 📌 Table of Contents

### 📊 Statistics:
1. What is Statistics?
2. Types of Statistics
3. Types of Data
4. Levels of Measurement
5. Measures of Central Tendency
6. Measures of Dispersion
7. Skewness & Kurtosis
8. Outliers
9. Correlation vs Causation
10. Applications in ML

### 🎲 Probability:
11. What is Probability?
12. Types of Probability
13. Basic Probability Rules
14. Conditional Probability
15. Bayes' Theorem
16. Independent vs Dependent Events
17. Probability Distributions
18. Bernoulli, Binomial, Normal
19. Central Limit Theorem (CLT)
20. Real-Life & ML Examples

---

# 📊 1. What is Statistics?

Science of collecting, analyzing, interpreting & presenting data.

---

## 2. Types of Statistics

- **Descriptive**: Summarize data (mean, median, mode, etc.)
- **Inferential**: Prediction ya decision lena sample data se.

---

## 3. Types of Data

| Type     | Description              | Example           |
|----------|--------------------------|-------------------|
| Qualitative | Non-numeric (categorical) | Colors, Gender    |
| Quantitative | Numeric values           | Age, Salary       |

---

## 4. Levels of Measurement

1. **Nominal** – Labels (e.g., Gender)
2. **Ordinal** – Order without fixed interval (e.g., Rank)
3. **Interval** – Ordered + equal interval (e.g., Temperature)
4. **Ratio** – Interval + true zero (e.g., Weight)

---

## 5. Central Tendency

- **Mean**: Average  
- **Median**: Middle value  
- **Mode**: Most frequent value

---

## 6. Measures of Dispersion

- **Range**: Max - Min  
- **Variance**: Spread from mean  
- **Standard Deviation**: Square root of variance  
- **IQR**: Q3 - Q1

---

## 7. Skewness & Kurtosis

- **Skewness**: Distribution tilt (Left/Right)
- **Kurtosis**: Peakedness of curve (High = sharp peak)

---

## 8. Outliers

Extreme values — affect mean badly

- Detect: IQR, Z-score
- Fix: Remove or transform

---

## 9. Correlation vs Causation

- **Correlation**: Two variables move together
- **Causation**: One variable causes the change

> ML me mostly correlation dekhte hai, causation proof nahi hota easily.

---

## 10. ML Me Statistics ka Use

- Feature engineering → Mean/Std
- Outlier detection
- Correlation heatmap
- Hypothesis testing
- Normalization, scaling

---

# 🎲 11. What is Probability?

Kisi event ke hone ki possibility.

**Formula**:  
P(E) = Favorable Outcomes / Total Outcomes

---

## 12. Types of Probability

| Type            | Description            | Example                         |
|-----------------|------------------------|---------------------------------|
| Theoretical     | Math-based assumption  | Coin toss: 0.5                  |
| Experimental    | Observation based      | 100 baar me 45 heads → 0.45     |
| Axiomatic       | Rules-based approach   | P(A ∪ B) = P(A) + P(B) − P(A ∩ B) |

---

## 13. Basic Probability Rules

- **Addition Rule**:  
  P(A ∪ B) = P(A) + P(B) − P(A ∩ B)

- **Multiplication Rule**:  
  P(A ∩ B) = P(A) × P(B|A)

- **Complement Rule**:  
  P(Not A) = 1 − P(A)

---

## 14. Conditional Probability

```
P(A|B) = P(A ∩ B) / P(B)
```

**Example**:  
P(Spam | "Buy now" in email)

---

## 15. Bayes' Theorem

```
P(A|B) = (P(B|A) × P(A)) / P(B)
```

- ML Use: Naive Bayes Classifier
- Example: Medical diagnosis

---

## 16. Independent vs Dependent Events

| Type         | Definition                             | Example                       |
|--------------|----------------------------------------|-------------------------------|
| Independent  | Ek event doosre ko affect nahi karta   | Coin toss, dice roll          |
| Dependent    | Ek event ka doosre pe effect hota hai  | Bag se 2nd draw without replacement |

---

## 17. Probability Distributions

Probability ka spread:

- **Discrete** → Specific values
- **Continuous** → Infinite range

---

## 18. Bernoulli, Binomial, Normal

| Distribution   | Use                        | Example                       |
|----------------|----------------------------|-------------------------------|
| Bernoulli      | Single yes/no event        | Coin toss                     |
| Binomial       | Fixed trials + success     | 10 tosses → # of heads        |
| Normal         | Bell curve                 | Heights, salaries, exam marks |

**Code Example**:

```python
from scipy.stats import norm
import numpy as np
x = np.linspace(-3, 3, 1000)
y = norm.pdf(x, 0, 1)
```

---

## 19. Central Limit Theorem (CLT)

Jab sample size bada ho, toh sample means approx normal distribute honge — even if data original normal nahi hai.

> ML me: confidence intervals, testing

---

## 20. Real-Life + ML Examples

- 📧 Spam detection → Conditional Probability
- ⚕️ Disease prediction → Bayes' Theorem
- 📈 A/B Testing → Binomial Dist.
- 🤖 Naive Bayes → Probabilistic ML

---

## ✅ Summary

- Stats & Probability = Core ML ke pillars
- Data samajhne, saaf karne, aur model decisions ke liye essential
- Use hoti hai: Preprocessing, EDA, Feature Engineering, Model Evaluation

---

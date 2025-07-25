# 📘 Supervised Machine Learning — Regression (Hinglish GitHub Notes)

---

## 🧠 Supervised Machine Learning kya hota hai?

Supervised Machine Learning ek aisa technique hai jisme model ko **labeled data** diya jata hai — yaani **input (X)** aur **output (Y)** dono known hote hain.

### 📌 Kaise kaam karta hai:

* **Input:** X (features)
* **Output:** Y (target/label)
* Model `X` aur `Y` ke relation ko learn karta hai
* Fir naye `X` pe `Y` predict karta hai

### 🧪 Supervised Learning ke Types:

| Type           | Description                         | Example                         |
| -------------- | ----------------------------------- | ------------------------------- |
| Regression     | Jab output **continuous** ho        | Salary prediction, house price  |
| Classification | Jab output **categorical/label** ho | Spam detection, tumor detection |

### ✅ Kyu Important Hai?

* Output already known hota hai → training easy hoti hai
* Real-world problems mostly supervised hote hain
* ML ka foundation hai

### 🌍 Applications:

| Domain     | Use Case                           |
| ---------- | ---------------------------------- |
| Finance    | Stock prediction, fraud detection  |
| Healthcare | Disease detection (classification) |
| E-commerce | Product recommendation             |
| Email      | Spam vs Non-Spam filtering         |
| Marketing  | Customer churn prediction          |

---

## 📈 Linear Regression

Linear Regression ek supervised learning algorithm hai jo **continuous output** predict karta hai.

### 📌 Best-Fit Line:

> Goal: ek aisi line `y = mx + c` nikalna jo data ko best represent kare

* `y` = predicted output
* `x` = input
* `m` = slope (1 unit x badhne pe y kitna badhega)
* `c` = intercept (jab x = 0 ho to y kitna hai)

#### 🖊️ Example:

> Experience ke basis pe salary predict karna

![Best Fit Line](https://upload.wikimedia.org/wikipedia/commons/3/3a/Linear_regression.svg)

---

## 📉 Residuals & Cost Function

### 📌 Residual:

> Actual value aur predicted value ka difference:

```
Residual = Actual y - Predicted y
```

### 📌 Cost Function:

> Har prediction error ka total loss calculate karta hai (generally MSE)

$$
J(\theta) = \frac{1}{m} \sum_{i=1}^{m}(\hat{y}_i - y_i)^2
$$

🎯 Goal: `J(θ)` ko minimize karna by adjusting slope & intercept.

---

## 🔁 Gradient Descent

> Cost function ko minimize karne ke liye use hota hai

### ⚙️ Kaise kaam karta hai:

* Random values se `θ₀`, `θ₁` start karte hain
* Cost ka gradient calculate karte hain
* Gradually `θ` update karte hain minimum error ke direction me

![Gradient Descent](https://upload.wikimedia.org/wikipedia/commons/e/ec/Gradient_descent.svg)

### ⚠️ Learning Rate (α):

* Ye batata hai ki step kitna bada hoga
* Zyada bada → overshoot
* Zyada chhota → slow learning

---

## 🧠 Global Minima

Cost curve ka wo point jaha error sabse kam hota hai — Gradient Descent wahi tak pahuchta hai.

---

## 🤖 Multiple Linear Regression

Jab ek se zyada input features ho, tab use hota hai:

```
y = θ₀ + θ₁x₁ + θ₂x₂ + ... + θₙxₙ
```

Example: Age, BMI, smoker status se insurance charges predict karna

---

## 🧪 Project: Insurance Charges Prediction

**Goal**: Linear Regression se insurance cost predict karna

### Steps:

1. `pd.read_csv()` se data load karo
2. `.head()`, `.info()` se data explore karo
3. `sns.scatterplot()` se visualize karo
4. Categorical features encode karo (e.g. smoker → 0/1)
5. `train_test_split()` se split karo
6. `LinearRegression()` se model train karo
7. `.score()` se performance evaluate karo

📊 Example Code:

```python
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
X = df[['age', 'bmi', 'smoker']]
y = df['charges']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
model = LinearRegression()
model.fit(X_train, y_train)
model.score(X_test, y_test)
```

---

## 📊 Evaluation Metrics

| Metric      | Explanation (Hindi)                            |
| ----------- | ---------------------------------------------- |
| R² Score    | Model kitna variance explain karta hai         |
| Adjusted R² | Feature ke count ke hisaab se adjust karta hai |
| MAE         | Mean Absolute Error                            |
| MSE         | Mean Squared Error                             |
| RMSE        | Root Mean Squared Error                        |

### 📈 R² vs Adjusted R²:

| R²   | Adjusted R² | Features Count | Meaning            |
| ---- | ----------- | -------------- | ------------------ |
| 0.81 | 0.79        | 1              | Good fit           |
| 0.88 | 0.86        | 2              | Better             |
| 0.99 | 0.96        | 3              | May be overfitting |

---

## 🚧 Underfitting vs Overfitting

| Condition    | Training Accuracy | Test Accuracy | Bias | Variance |
| ------------ | ----------------- | ------------- | ---- | -------- |
| Underfitting | ❌ Low             | ❌ Low         | High | Low      |
| Overfitting  | ✅ High            | ❌ Low         | Low  | High     |
| Good Fit     | ✅ High            | ✅ High        | Low  | Low      |

![Overfitting vs Underfitting](https://upload.wikimedia.org/wikipedia/commons/6/68/Overfitting.svg)

---

## 🧱 Regularization (Overfitting se bachne ka tareeka)

### 📌 Types:

* **Ridge (L2)**: θ² ka penalty add karta hai
* **Lasso (L1)**: |θ| ka penalty add karta hai

```
Cost = MSE + λ * (Σ|θ|)   ← Lasso
Cost = MSE + λ * (Σθ²)    ← Ridge
```

---


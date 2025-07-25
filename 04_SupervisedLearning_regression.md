# 📘 Supervised Machine Learning — Regression (Complete Markdown Notes for GitHub)

---

## 🧠 What is Supervised Machine Learning?

Supervised Machine Learning is an approach where the model is trained on **labeled data** — that is, both **inputs (X)** and their corresponding **outputs (Y)** are known.

### 📌 How it Works:

* **Input:** Feature(s) (X)
* **Output:** Label (Y)
* The model learns the mapping `f(X) → Y`
* Then it predicts Y for new/unseen X

### 🧪 Types of Supervised Learning:

| Type           | Description                      | Example                              |
| -------------- | -------------------------------- | ------------------------------------ |
| Regression     | Output is **continuous**         | Salary prediction, house price       |
| Classification | Output is **categorical/labels** | Spam detection, tumor classification |

### ✅ Why is it Important?

* Output is **clearly known** → more effective training
* Covers most real-world problems (finance, healthcare, etc.)
* Foundation for most ML algorithms

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

Linear Regression is a supervised ML algorithm used to predict a **continuous target variable** using one or more input variables.

### 📌 Best-Fit Line:

> The goal is to find the **best-fit line**: `y = mx + c`

Where:

* `y` = predicted value
* `x` = input feature
* `m` = slope (how much y changes per unit x)
* `c` = intercept (value of y when x = 0)

#### 🖊️ Example:

> Predicting salary (`y`) based on years of experience (`x`).

![Best Fit Line](https://upload.wikimedia.org/wikipedia/commons/3/3a/Linear_regression.svg)

---

## 📉 Residuals & Cost Function

### 📌 Residual:

> The **difference** between the actual value and the predicted value:

```
Residual = Actual y - Predicted y
```

### 📌 Cost Function:

> Measures total error over all training points (commonly used: **MSE**)

$$
J(\theta) = \frac{1}{m} \sum_{i=1}^{m}(\hat{y}_i - y_i)^2
$$

Goal: **Minimize cost function** by adjusting slope & intercept.

---

## 🔁 Gradient Descent

> Optimization algorithm used to **minimize the cost function**

### ⚙️ How it works:

* Start with random `θ₀` and `θ₁`
* Calculate gradient (slope of cost function)
* Update `θ` values to move toward **global minimum**

### 📉 Visual:

![Gradient Descent](https://upload.wikimedia.org/wikipedia/commons/e/ec/Gradient_descent.svg)

### ⚠️ Learning Rate (α):

* Controls step size in each iteration
* Too small → slow learning
* Too large → may overshoot minimum

---

## 🧠 Global Minima

* The point on the cost curve where the error is **minimum**.
* Gradient Descent aims to reach this point by updating parameters iteratively.

---

## 🤖 Multiple Linear Regression

> When we have **multiple input features**, it's called **Multiple Regression**.

Equation:

```
y = θ₀ + θ₁x₁ + θ₂x₂ + ... + θₙxₙ
```

Use case: Predicting insurance cost based on age, BMI, smoker status, etc.

---

## 🧪 Project: Predicting Insurance Charges

**Goal**: Predict medical insurance charges using linear regression.

### Steps:

1. Load dataset using `pd.read_csv()`
2. Explore data with `.info()`, `.head()`, `.describe()`
3. Visualize relationships (e.g., `sns.scatterplot()` for BMI vs Charges)
4. Encode categorical variables (e.g., smoker: yes/no → 1/0)
5. Split data using `train_test_split()`
6. Train model using `LinearRegression()` from `sklearn`
7. Predict and evaluate with `.score()` (R²)

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

## 📊 Model Evaluation Metrics

| Metric      | Use                                  |
| ----------- | ------------------------------------ |
| R² Score    | % of variance explained by the model |
| Adjusted R² | Adjusted for number of features      |
| MAE         | Mean of absolute errors              |
| MSE         | Mean of squared errors               |
| RMSE        | Square root of MSE                   |

### 📈 R² vs Adjusted R²:

| R²   | Adjusted R² | Features Count | Interpretation |
| ---- | ----------- | -------------- | -------------- |
| 0.81 | 0.79        | 1              | Good fit       |
| 0.88 | 0.86        | 2              | Better         |
| 0.99 | 0.96        | 3              | Overfit risk   |

---

## 🚧 Underfitting vs Overfitting

| Condition    | Training Accuracy | Test Accuracy | Bias | Variance |
| ------------ | ----------------- | ------------- | ---- | -------- |
| Underfitting | ❌ Low             | ❌ Low         | High | Low      |
| Overfitting  | ✅ High            | ❌ Low         | Low  | High     |
| Ideal Fit    | ✅ High            | ✅ High        | Low  | Low      |

![Overfitting vs Underfitting](https://upload.wikimedia.org/wikipedia/commons/6/68/Overfitting.svg)

---

## 🧱 Regularization

> Techniques to avoid overfitting by **penalizing large coefficients**

### 📌 Types:

* **Ridge Regression (L2)**: Adds squared penalty to cost function
* **Lasso Regression (L1)**: Adds absolute value penalty

Equation:

```
Cost = MSE + λ * (Σ|θ|)  ← Lasso
Cost = MSE + λ * (Σθ²)   ← Ridge
```

---



*✅ Combined from handwritten notes, Collab comments, and PDF project. Ready for GitHub.*

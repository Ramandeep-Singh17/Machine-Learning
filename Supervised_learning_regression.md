# 📘 Supervised Machine Learning — Regression (Markdown Notes for GitHub)

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

![Linear Regression Diagram](https://upload.wikimedia.org/wikipedia/commons/3/3a/Linear_regression.svg)

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

```
         |
 Cost    |     .-'''
         |  .-'
         |/__________
              Theta
```

### ⚠️ Learning Rate (α):

* Controls step size in each iteration
* Too small → slow learning
* Too large → may overshoot minimum

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

* **Adjusted R²** is more reliable when there are multiple features.

---

## 🤖 Multiple Linear Regression

> When we have **multiple input features**, it's called **Multiple Regression**.

Equation:

```
y = θ₀ + θ₁x₁ + θ₂x₂ + ... + θₙxₙ
```

Use cases: Salary prediction based on age, experience, education, etc.

---

## 🚧 Underfitting vs Overfitting

| Situation        | Train Accuracy | Test Accuracy | Bias | Variance |
| ---------------- | -------------- | ------------- | ---- | -------- |
| Underfitting     | ❌ Low          | ❌ Low         | High | Low      |
| Overfitting      | ✅ High         | ❌ Low         | Low  | High     |
| Good Fit (Ideal) | ✅ High         | ✅ High        | Low  | Low      |

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

## ✅ Summary

> Linear Regression is the base of most ML regression tasks. It's easy to interpret, mathematically elegant, and scalable. Real power comes when you combine theory (as you’ve written) with real-world code and projects.

---

## 🔚 Coming Next:

* Logistic Regression
* Polynomial Regression
* Feature Scaling
* Model Tuning
* Real Projects with sklearn & pandas

---

*Created by combining handwritten notes + Colab theory comments. Ready to be pushed on GitHub with pride 🚀*

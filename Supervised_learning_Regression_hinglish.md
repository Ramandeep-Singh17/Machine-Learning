📘 Supervised Machine Learning — Regression (Hinglish Notes for GitHub)
🧠 Supervised Machine Learning kya hota hai?
Supervised Machine Learning ek aisi technique hai jisme model ko labeled data diya jata hai — yaani X (input) aur Y (output) dono known hote hain.

📌 Kaise kaam karta hai:
Input (X): Features/columns

Output (Y): Target label

Model ye seekhta hai ki X se Y kaise predict kare

Fir naye data pe prediction karta hai

🧪 Supervised Learning ke Types:
Type	Kya hota hai	Example
Regression	Jab output continuous ho	Salary prediction, house price
Classification	Jab output label ho	Spam detection, tumor detection

✅ Kyu important hai?
Output pehle se known hota hai → model easily sikh jata hai

Real-world me kaafi use hota hai

ML ka base yahi hota hai

🌍 Kahaan use hota hai:
Domain	Use Case
Finance	Stock prediction, loan default
Healthcare	Disease detection
E-commerce	Product recommendations
Email	Spam filter
Marketing	Customer churn prediction

📈 Linear Regression
Linear Regression ek supervised ML algorithm hai jo continuous value predict karta hai.

📌 Best-Fit Line kya hoti hai:
Goal: y = mx + c jaise line banana jo data ke sabse close ho

y = predicted output

x = input feature

m = slope (kitna change aayega y me agar x badhe)

c = intercept (jab x = 0 ho tab y ka value)

🖊️ Example:
Salary predict karna based on experience



📉 Residuals & Cost Function
📌 Residual:
Actual aur Predicted ke beech ka difference:

ini
Copy
Edit
Residual = Actual y - Predicted y
📌 Cost Function:
Saare errors ka total measure karta hai (generally MSE)

𝐽
(
𝑡
ℎ
𝑒
𝑡
𝑎
)
=
𝑓
𝑟
𝑎
𝑐
1
𝑚
𝑠
𝑢
𝑚
𝑖
=
1
𝑚
(
ℎ
𝑎
𝑡
𝑦
𝑖
−
𝑦
𝑖
)
2
J(
theta)=
frac1m
sum 
i=1
m
​
 (
haty 
i
​
 −y 
i
​
 ) 
2
 
Goal: Error (cost) ko minimum banana.

🔁 Gradient Descent
Ek optimization algorithm hai jo cost function ko minimize karta hai

⚙️ Kaise kaam karta hai:
Random θ₀ aur θ₁ se start karta hai

Gradient (slope) nikalta hai

Gradually parameters ko update karta hai global minimum tak

📉 Visual:


⚠️ Learning Rate (α):
Ye decide karta hai ki har step kitna bada hoga

Zyada bada → overshoot

Zyada chhota → slow training

🧠 Global Minima
Curve ka wo point jaha cost sabse kam hota hai

Gradient Descent wahi tak pahuchne ki koshish karta hai

🤖 Multiple Linear Regression
Jab 1 se zyada input features ho → Multiple Linear Regression use karte hain

Equation:

ini
Copy
Edit
y = θ₀ + θ₁x₁ + θ₂x₂ + ... + θₙxₙ
Example: Age, BMI, smoker status se insurance charges predict karna

🧪 Mini Project: Insurance Charges Prediction
Goal: Linear regression use karke insurance charges predict karna

Steps:
read_csv() se data load karo

.info(), .head() se explore karo

sns.scatterplot() se visualize karo

Categorical columns ko encode karo

train_test_split() se split karo

LinearRegression() se model train karo

.score() se accuracy check karo

📊 Code Example:

python
Copy
Edit
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
X = df[['age', 'bmi', 'smoker']]
y = df['charges']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
model = LinearRegression()
model.fit(X_train, y_train)
model.score(X_test, y_test)
📊 Model Evaluation Metrics
Metric	Use (Hindi Me)
R² Score	Model ne kitna variation explain kiya
Adjusted R²	Feature badhne pe adjust karta hai
MAE	Average absolute error
MSE	Average squared error
RMSE	MSE ka square root (original unit me)

📈 R² vs Adjusted R²:
R²	Adjusted R²	Features	Meaning
0.81	0.79	1	Achha model
0.88	0.86	2	Aur better
0.99	0.96	3	Overfitting risk

🚧 Overfitting vs Underfitting
Condition	Train Acc	Test Acc	Bias	Variance
Underfitting	❌ Low	❌ Low	High	Low
Overfitting	✅ High	❌ Low	Low	High
Best Fit	✅ High	✅ High	Low	Low



🧱 Regularization
Jab model overfit kare to use control karne ke liye regularization lagate hain

📌 Types:
Ridge (L2): θ² add karta hai cost me

Lasso (L1): |θ| add karta hai cost me

Equation:

ini
Copy
Edit
Cost = MSE + λ * (Σ|θ|)  ← Lasso
Cost = MSE + λ * (Σθ²)   ← Ridge

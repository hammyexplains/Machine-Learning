# Regression Evaluation Metrics: MAE, MSE, RMSE, and R² Score

Before deploying a regression model, we need a way to measure how well it performs.

A model that predicts house prices, salaries, sales revenue, or temperatures will rarely make perfect predictions. There will almost always be some difference between the predicted value and the actual value.

This difference is called **Error**.

To quantify how much error a model makes, we use **Regression Evaluation Metrics**.

In this markdown, we will understand:

1. What is regression?
2. What is prediction error?
3. MAE (Mean Absolute Error)
4. MSE (Mean Squared Error)
5. RMSE (Root Mean Squared Error)
6. R² Score (Coefficient of Determination)

---

# What is Regression?

Regression is a type of supervised learning used when the target variable is a continuous numerical value.

Examples:

- Predicting House Prices
- Predicting Salaries
- Predicting Sales Revenue
- Predicting Temperature
- Predicting Stock Prices (basic use case)

A regression model learns patterns from historical data and predicts numerical values.

---

# Example Regression Problem

Suppose we want to predict house prices.

| House Size (sq ft) | Actual Price (Lakhs) |
|-------------------|----------------------|
| 1000 | 25 |
| 1200 | 30 |
| 1500 | 40 |
| 1800 | 50 |

After training, the model starts making predictions.

---

# Actual vs Predicted Values

Suppose the model produces the following predictions:

| Actual Price | Predicted Price |
|-------------|----------------|
| 25 | 27 |
| 30 | 29 |
| 40 | 42 |
| 50 | 47 |

The predictions are close, but not perfect.

---

# What is Error?

Error is simply the difference between the actual value and the predicted value.

Formula:

```text
Error = Actual Value - Predicted Value
```

Example:

```text
Actual Price = 25
Predicted Price = 27

Error = 25 - 27
      = -2
```

The model made an error of 2 units.

---

# Why Can't We Simply Add All Errors?

Consider these errors:

```text
-5
+5
```

Adding them gives:

```text
0
```

This incorrectly suggests that the model made no error.

To solve this problem, we use specialized evaluation metrics.

---

# 1. Mean Absolute Error (MAE)

MAE measures the average absolute error made by the model.

The word "absolute" means we ignore the sign.

Formula:

```text
MAE = Σ |Actual - Predicted| / n
```

---

# Example

Actual Values:

```text
[10, 20, 30]
```

Predicted Values:

```text
[12, 18, 35]
```

Errors:

```text
10 - 12 = -2
20 - 18 = 2
30 - 35 = -5
```

Absolute Errors:

```text
2
2
5
```

MAE:

```text
(2 + 2 + 5) / 3

= 9 / 3

= 3
```

---

# Interpretation of MAE

```text
MAE = 3
```

This means:

> On average, the model is making an error of 3 units.

---

# Advantages of MAE

- Easy to understand
- Same unit as the target variable
- Less sensitive to outliers

---

# Disadvantages of MAE

- Does not heavily penalize large errors
- Treats all errors equally

---

# 2. Mean Squared Error (MSE)

MSE measures the average squared error.

Instead of taking the absolute value, we square the errors.

Formula:

```text
MSE = Σ (Actual - Predicted)² / n
```

---

# Example

Errors:

```text
-2
2
-5
```

Squared Errors:

```text
4
4
25
```

MSE:

```text
(4 + 4 + 25) / 3

= 33 / 3

= 11
```

---

# Why Square the Errors?

Squaring provides two benefits:

## 1. Removes Negative Signs

```text
(-5)² = 25
```

---

## 2. Penalizes Large Errors

Consider:

```text
Error = 2
Squared Error = 4

Error = 10
Squared Error = 100
```

Large mistakes become much more significant.

---

# Interpretation of MSE

Lower MSE:

```text
Good Model
```

Higher MSE:

```text
Poor Model
```

The goal is to minimize MSE.

---

# Advantages of MSE

- Widely used in Machine Learning
- Strongly penalizes large errors
- Useful for optimization algorithms

---

# Disadvantages of MSE

- Difficult to interpret
- Units become squared

Example:

```text
Price Unit = Rupees

MSE Unit = Rupees²
```

Which doesn't have a practical meaning.

---

# 3. Root Mean Squared Error (RMSE)

RMSE solves the interpretability issue of MSE.

It simply takes the square root of MSE.

Formula:

```text
RMSE = √MSE
```

---

# Example

Suppose:

```text
MSE = 11
```

Then:

```text
RMSE = √11

≈ 3.31
```

---

# Interpretation of RMSE

```text
RMSE = 3.31
```

This means:

> The model is making an average error of approximately 3.31 units.

Unlike MSE, RMSE is in the same unit as the target variable.

---

# Advantages of RMSE

- Easy to interpret
- Same unit as target variable
- Penalizes large errors

---

# Disadvantages of RMSE

- Sensitive to outliers
- Large errors influence the score heavily

---

# MAE vs MSE vs RMSE

Consider these errors:

```text
1
2
3
20
```

The error 20 is much larger than the others.

### MAE

```text
(1 + 2 + 3 + 20) / 4

= 6.5
```

---

### MSE

```text
(1² + 2² + 3² + 20²) / 4

= (1 + 4 + 9 + 400) / 4

= 103.5
```

Notice how the large error dominates.

---

### RMSE

```text
√103.5

≈ 10.17
```

---

# 4. R² Score (Coefficient of Determination)

MAE, MSE, and RMSE tell us how much error the model makes.

But they don't tell us:

> How much of the variation in the data is explained by the model?

This is where R² Score comes in.

---

# What Does R² Measure?

R² measures how well the regression model explains the variability of the target variable.

Formula:

```text
R² = 1 - (Residual Sum of Squares / Total Sum of Squares)
```

You do not need to memorize the formula.

The key idea is:

> R² tells us how much information in the target variable is explained by the model.

---

# R² Score Range

Typically:

```text
0 ≤ R² ≤ 1
```

---

# Interpretation

## R² = 1

Perfect model.

```text
100% of the variation explained.
```

---

## R² = 0

Model performs no better than predicting the mean.

---

## R² = 0.80

```text
80% of the variation is explained by the model.
```

---

## R² = 0.95

```text
95% of the variation is explained by the model.
```

---

# Example

Suppose a house price model has:

```text
R² = 0.90
```

Interpretation:

> The model explains 90% of the variation in house prices.

The remaining 10% is due to unknown factors or noise.

---

# When is a Good R² Score Considered Good?

There is no universal rule.

Typical guideline:

| R² Score | Interpretation |
|-----------|---------------|
| < 0.50 | Weak Model |
| 0.50 - 0.70 | Moderate Model |
| 0.70 - 0.90 | Good Model |
| > 0.90 | Excellent Model |

The acceptable score depends on the problem domain.

---

# Which Metric Should You Use?

## Use MAE When

- Interpretability is important.
- Outliers should not dominate the evaluation.

---

## Use MSE When

- Large errors should be heavily penalized.
- Optimizing Machine Learning models.

---

## Use RMSE When

- You want error in the original unit.
- Large errors are important.

---

## Use R² When

- You want to understand how well the model explains the data.
- Comparing multiple regression models.

---

# Quick Comparison

| Metric | Formula Idea | Unit | Penalizes Large Errors? |
|----------|-------------|------|------------------------|
| MAE | Average Absolute Error | Same Unit | No |
| MSE | Average Squared Error | Squared Unit | Yes |
| RMSE | Square Root of MSE | Same Unit | Yes |
| R² Score | Explained Variance | No Unit | Not an Error Metric |

---

# Summary

Regression models make predictions, and prediction errors are unavoidable.

To measure model performance, we use evaluation metrics:

### MAE

Measures the average absolute error.

```text
Lower is Better
```

---

### MSE

Measures the average squared error.

```text
Lower is Better
```

---

### RMSE

Measures error in the original unit while still penalizing large mistakes.

```text
Lower is Better
```

---

### R² Score

Measures how well the model explains the variation in the data.

```text
Higher is Better
```

A good regression model typically aims for:

```text
Low MAE
Low MSE
Low RMSE
High R² Score
```

# Linear Regression

Linear Regression is one of the simplest and most widely used Machine Learning algorithms.

It is used to predict a **continuous numerical value** by finding the relationship between one or more input features and a target variable.

---

# What Problem Does Linear Regression Solve?

Linear Regression is used when the output is a number.

### Examples

- Predicting house prices
- Predicting employee salaries
- Predicting sales revenue
- Predicting stock prices (basic use case)
- Predicting student marks

Since the output is a numerical value, Linear Regression is considered a **Regression Algorithm**.

---

# A Simple Example

Suppose we have the following data:

| Hours Studied | Marks Scored |
|--------------|--------------|
| 1 | 20 |
| 2 | 35 |
| 3 | 50 |
| 4 | 65 |
| 5 | 80 |

From this data, we can observe:

> As the number of study hours increases, the marks also increase.

Linear Regression tries to learn this relationship and create a mathematical equation that can be used for future predictions.

---

# How Linear Regression Works

Linear Regression attempts to fit the best possible straight line through the data points.

This line is called the **Regression Line** or **Best Fit Line**.

```text
Marks
 ^
 |
 |                         *
 |                     *
 |                 *
 |             *
 |         *
 +------------------------------> Hours Studied
```

The line represents the relationship between the input and output variables.

---

# The Linear Regression Equation

The equation of a straight line is:

```text
y = mx + c
```

In Machine Learning, it is usually written as:

```text
y = β₀ + β₁x
```

Where:

- **y** = Predicted value
- **x** = Input feature
- **β₀** = Intercept
- **β₁** = Slope (Coefficient)

---

# Understanding Slope and Intercept

### Slope (β₁)

The slope tells us how much the target variable changes when the input changes.

Example:

```text
Marks increase by 15
for every additional hour studied.
```

Then:

```text
Slope = 15
```

### Intercept (β₀)

The intercept is the predicted value when the input is zero.

Example:

```text
Hours Studied = 0
Predicted Marks = 5
```

Then:

```text
Intercept = 5
```

The equation becomes:

```text
Marks = 5 + 15 × Hours Studied
```

---

# Making Predictions

Suppose the learned equation is:

```text
Marks = 5 + 15 × Hours Studied
```

For a student who studies 6 hours:

```text
Marks = 5 + (15 × 6)
Marks = 95
```

Predicted Marks:

```text
95
```

---

# How Does the Model Find the Best Line?

Many possible lines can be drawn through the data.

Linear Regression chooses the line that minimizes prediction errors.

The difference between:

```text
Actual Value
```

and

```text
Predicted Value
```

is called the **Error** or **Residual**.

The model tries to find the line with the smallest overall error.

---

# Types of Linear Regression

## 1. Simple Linear Regression

Uses one input feature.

Example:

```text
Hours Studied → Marks
```

Equation:

```text
y = β₀ + β₁x
```

---

## 2. Multiple Linear Regression

Uses multiple input features.

Example:

```text
House Price
```

Based on:

- Area
- Number of Bedrooms
- Location Score
- Age of House

Equation:

```text
y = β₀ + β₁x₁ + β₂x₂ + β₃x₃ + ...
```

---

# Assumptions of Linear Regression

Linear Regression works best when:

1. A linear relationship exists between features and target.
2. Observations are independent.
3. Errors are normally distributed.
4. Variance of errors remains constant.
5. Features are not highly correlated with each other.

---

# Advantages

- Easy to understand
- Fast to train
- Easy to interpret
- Works well for linear relationships
- Serves as a strong baseline model

---

# Limitations

- Assumes a linear relationship
- Sensitive to outliers
- Can underperform on complex datasets
- Not suitable when relationships are highly nonlinear

---

# Real-World Applications

- House price prediction
- Sales forecasting
- Demand forecasting
- Salary prediction
- Revenue estimation
- Business analytics

---

# Summary

Linear Regression is a supervised Machine Learning algorithm used to predict continuous numerical values.

It works by finding the best-fit straight line that describes the relationship between input features and the target variable.

The model learns an equation of the form:

```text
y = β₀ + β₁x
```

and uses it to make predictions on unseen data.

> Linear Regression answers a simple question:
>
> "If the trend observed in the past continues, what value should we expect in the future?"

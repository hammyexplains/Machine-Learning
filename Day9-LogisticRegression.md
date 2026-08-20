# Logistic Regression

Despite its name, **Logistic Regression** is actually a **classification algorithm**, not a regression algorithm.

It is used when the target variable belongs to a category, such as:

- Yes / No
- Pass / Fail
- Spam / Not Spam
- Fraud / Not Fraud
- Disease / No Disease

The goal of Logistic Regression is to predict the probability that a data point belongs to a particular class.

---

# Why Can't We Use Linear Regression for Classification?

Consider a problem where we want to predict whether a student will pass or fail.

| Hours Studied | Result |
|--------------|---------|
| 1 | Fail (0) |
| 2 | Fail (0) |
| 4 | Pass (1) |
| 5 | Pass (1) |

If we use Linear Regression, the predictions could be:

```text
-0.5
0.3
1.2
1.8
```

The problem is that probabilities should always be between:

```text
0 and 1
```

But Linear Regression can produce values less than 0 or greater than 1.

To solve this problem, Logistic Regression uses a special function called the **Sigmoid Function**.

---

# The Sigmoid Function

The Sigmoid Function converts any value into a range between 0 and 1.

Its formula is:

```text
σ(z) = 1 / (1 + e^(-z))
```

Where:

- σ(z) = Predicted probability
- e = Euler's number
- z = Linear combination of features

The output will always be between:

```text
0 and 1
```

---

# How Logistic Regression Works

### Step 1: Calculate a Linear Equation

Similar to Linear Regression:

```text
z = β₀ + β₁x
```

Where:

- x = Input feature
- β₀ = Intercept
- β₁ = Coefficient

---

### Step 2: Apply the Sigmoid Function

The value of z is passed through the Sigmoid Function.

Example:

```text
z = 2
```

After applying sigmoid:

```text
Probability = 0.88
```

This means:

```text
88% chance of belonging to Class 1
```

---

# Making Predictions

Suppose the model predicts:

```text
0.92
```

This means:

```text
92% probability of Pass
```

Now we apply a threshold.

Most commonly:

```text
Threshold = 0.5
```

Decision Rule:

```text
Probability >= 0.5 → Class 1
Probability < 0.5 → Class 0
```

Example:

| Probability | Prediction |
|------------|------------|
| 0.90 | Pass |
| 0.75 | Pass |
| 0.40 | Fail |
| 0.10 | Fail |

---

# Real-Life Example: Spam Detection

Suppose an email arrives.

The Logistic Regression model analyzes features such as:

- Number of links
- Presence of suspicious words
- Sender information
- Email content

The model outputs:

```text
0.95
```

Meaning:

```text
95% probability that the email is spam.
```

Since:

```text
0.95 > 0.5
```

The email is classified as:

```text
Spam
```

---

# Logistic Regression Output

Unlike Linear Regression, which predicts numerical values such as:

```text
House Price = ₹25,00,000
```

Logistic Regression predicts probabilities:

```text
0.85
```

which can be interpreted as:

```text
85% chance of belonging to a class.
```

---

# Types of Logistic Regression

## 1. Binary Logistic Regression

Used when there are only two classes.

Examples:

- Pass / Fail
- Spam / Not Spam
- Fraud / Not Fraud

---

## 2. Multinomial Logistic Regression

Used when there are more than two classes.

Examples:

- Red
- Blue
- Green

or

- Cat
- Dog
- Horse

---

## 3. Ordinal Logistic Regression

Used when classes have a meaningful order.

Examples:

- Poor
- Average
- Good
- Excellent

---

# Advantages

- Easy to understand and implement
- Fast to train
- Produces probabilities
- Works well for binary classification problems
- Highly interpretable

---

# Limitations

- Assumes a linear relationship between features and log-odds
- May struggle with complex nonlinear patterns
- Sensitive to outliers
- Can underperform on highly complex datasets

---

# Common Applications

- Spam Detection
- Disease Prediction
- Customer Churn Prediction
- Fraud Detection
- Loan Approval Prediction
- Sentiment Analysis

---

# Linear Regression vs Logistic Regression

| Linear Regression | Logistic Regression |
|------------------|--------------------|
| Used for Regression Problems | Used for Classification Problems |
| Predicts Numerical Values | Predicts Probabilities |
| Output can be any value | Output is always between 0 and 1 |
| Uses a Straight Line | Uses a Sigmoid Function |
| Example: House Price Prediction | Example: Spam Detection |

---

# Summary

Logistic Regression is a supervised Machine Learning algorithm used for classification tasks.

It first calculates a linear equation and then passes the result through a Sigmoid Function to produce a probability between 0 and 1.

Using a threshold (commonly 0.5), the model converts that probability into a class label.

> Logistic Regression answers the question:
>
> "What is the probability that this data point belongs to a particular class?"

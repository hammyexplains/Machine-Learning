# Confusion Matrix

When building a classification model, it is not enough to know whether predictions are correct or incorrect.

We also need to understand **what kind of mistakes** the model is making.

For example, suppose we build a Machine Learning model that predicts whether a person has COVID-19 or not.

If the model makes mistakes, we need to know:

- Did it incorrectly mark a healthy person as infected?
- Did it miss an infected patient?

A **Confusion Matrix** helps answer these questions.

---

# What is a Confusion Matrix?

A Confusion Matrix is a table used to evaluate a classification model by comparing:

- Actual Values
- Predicted Values

It shows how many predictions fall into each category.

For a binary classification problem, a confusion matrix consists of four components:

1. True Positive (TP)
2. True Negative (TN)
3. False Positive (FP)
4. False Negative (FN)

---

# COVID-19 Prediction Example

Suppose we build a model that predicts whether a patient has COVID-19.

Possible actual outcomes:

```text
COVID Positive
COVID Negative
```

Possible predictions:

```text
COVID Positive
COVID Negative
```

Based on the combination of actual and predicted values, four situations can occur.

---

# 1. True Positive (TP)

The patient actually has COVID.

The model predicts that the patient has COVID.

```text
Actual      = COVID Positive
Predicted   = COVID Positive
```

Result:

```text
Correct Prediction
```

Example:

An infected patient is correctly identified as infected.

---

# 2. True Negative (TN)

The patient does not have COVID.

The model predicts that the patient does not have COVID.

```text
Actual      = COVID Negative
Predicted   = COVID Negative
```

Result:

```text
Correct Prediction
```

Example:

A healthy person is correctly identified as healthy.

---

# 3. False Positive (FP)

The patient does not have COVID.

The model predicts that the patient has COVID.

```text
Actual      = COVID Negative
Predicted   = COVID Positive
```

Result:

```text
Incorrect Prediction
```

Example:

A healthy person is incorrectly identified as infected.

This may lead to unnecessary testing, isolation, or treatment.

---

# 4. False Negative (FN)

The patient actually has COVID.

The model predicts that the patient does not have COVID.

```text
Actual      = COVID Positive
Predicted   = COVID Negative
```

Result:

```text
Incorrect Prediction
```

Example:

An infected patient is incorrectly identified as healthy.

This can be dangerous because the patient may continue spreading the disease without knowing they are infected.

---

# The Confusion Matrix Table

| Actual / Predicted | COVID Positive | COVID Negative |
|-------------------|----------------|----------------|
| COVID Positive | True Positive (TP) | False Negative (FN) |
| COVID Negative | False Positive (FP) | True Negative (TN) |

---

# Example

Suppose we test our model on 100 patients.

The results are:

```text
True Positive  = 35
True Negative  = 50
False Positive = 5
False Negative = 10
```

The confusion matrix would look like:

| Actual / Predicted | Positive | Negative |
|-------------------|----------|----------|
| Positive | 35 | 10 |
| Negative | 5 | 50 |

---

# Understanding the Results

### True Positives

```text
35
```

35 infected patients were correctly identified as infected.

---

### True Negatives

```text
50
```

50 healthy patients were correctly identified as healthy.

---

### False Positives

```text
5
```

5 healthy patients were incorrectly identified as infected.

---

### False Negatives

```text
10
```

10 infected patients were incorrectly identified as healthy.

---

# Why is a Confusion Matrix Important?

A confusion matrix gives more information than simply knowing how many predictions were correct.

It helps us understand:

- How many positive cases were identified correctly
- How many negative cases were identified correctly
- How many healthy people were incorrectly flagged
- How many actual cases were missed

In medical applications such as COVID detection, understanding these mistakes is extremely important because different mistakes can have different consequences.

---

# Visual Representation

```text
                    Predicted
                 Positive   Negative

Actual Positive     TP         FN

Actual Negative     FP         TN
```

---

# Quick Memory Trick

### Positive Prediction

Model predicts:

```text
Positive
```

If it is correct:

```text
True Positive
```

If it is wrong:

```text
False Positive
```

---

### Negative Prediction

Model predicts:

```text
Negative
```

If it is correct:

```text
True Negative
```

If it is wrong:

```text
False Negative
```

---

# Summary

A Confusion Matrix is a table used to evaluate classification models by comparing actual outcomes with predicted outcomes.

The four components are:

```text
TP → True Positive
TN → True Negative
FP → False Positive
FN → False Negative
```

Using these four values, we can understand exactly where a model is making correct predictions and where it is making mistakes.

> A Confusion Matrix is not just about knowing whether a prediction is right or wrong.
>
> It helps us understand the type of mistakes a classification model makes.

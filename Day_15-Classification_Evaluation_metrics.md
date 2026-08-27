# Classification Evaluation Metrics

After training a classification model, one important question arises:

> How do we know if the model is performing well?

Simply looking at predictions is not enough. We need quantitative measures that tell us how accurate and reliable the model is.

This is where **Classification Evaluation Metrics** come into the picture.

The most commonly used metrics are:

1. Accuracy
2. Precision
3. Recall
4. F1 Score

Before understanding these metrics, let's quickly revisit the Confusion Matrix.

---

# Confusion Matrix Recap

Suppose we build a model to predict whether a patient has COVID-19.

The model's predictions can be categorized into four groups:

| Actual / Predicted | Positive | Negative |
|-------------------|----------|----------|
| Positive | True Positive (TP) | False Negative (FN) |
| Negative | False Positive (FP) | True Negative (TN) |

Where:

- **True Positive (TP)** → Actual Positive, Predicted Positive
- **True Negative (TN)** → Actual Negative, Predicted Negative
- **False Positive (FP)** → Actual Negative, Predicted Positive
- **False Negative (FN)** → Actual Positive, Predicted Negative

Suppose our model produces the following results:

```text
TP = 35
TN = 50
FP = 5
FN = 10
```

Total records:

```text
35 + 50 + 5 + 10 = 100
```

We will use these values throughout this markdown.

---

# 1. Accuracy

## What is Accuracy?

Accuracy measures the percentage of predictions that were correct.

In simple terms:

> Out of all predictions made by the model, how many were correct?

---

## Formula

```text
Accuracy =
(TP + TN)
---------------------
(TP + TN + FP + FN)
```

---

## Example

Using our confusion matrix values:

```text
TP = 35
TN = 50
FP = 5
FN = 10
```

Substituting into the formula:

```text
Accuracy =
(35 + 50)
----------------
(35 + 50 + 5 + 10)

=
85 / 100

=
0.85
```

```text
Accuracy = 85%
```

---

## Interpretation

An accuracy of 85% means:

> The model correctly predicted 85 out of every 100 patients.

---

## When Accuracy Works Well

Accuracy is useful when:

- Classes are balanced
- Both classes are equally important

Example:

```text
Pass / Fail Prediction
```

where both outcomes occur in similar numbers.

---

## Limitation of Accuracy

Consider a dataset of 1000 patients:

```text
990 Healthy
10 COVID Positive
```

A model predicts:

```text
Everyone is Healthy
```

Accuracy:

```text
990 / 1000

=
99%
```

The model appears excellent.

However:

```text
It missed every COVID patient.
```

This shows why accuracy alone is often not enough.

---

# 2. Precision

## What is Precision?

Precision answers the question:

> Out of all the patients predicted as positive, how many were actually positive?

Precision focuses on the quality of positive predictions.

---

## Formula

```text
Precision =
TP
------------
TP + FP
```

---

## Example

Using our confusion matrix:

```text
TP = 35
FP = 5
```

Substituting:

```text
Precision =
35
----------
35 + 5

=
35 / 40

=
0.875
```

```text
Precision = 87.5%
```

---

## Interpretation

A precision of 87.5% means:

> Whenever the model predicts COVID, it is correct 87.5% of the time.

---

## Why Precision Matters

Imagine a hospital screening system.

If precision is low:

```text
Many healthy people are flagged as infected.
```

This may lead to:

- Unnecessary testing
- Anxiety
- Additional medical costs

A higher precision means fewer false alarms.

---

# 3. Recall

## What is Recall?

Recall answers the question:

> Out of all actual positive cases, how many did the model correctly identify?

Recall focuses on finding as many actual positives as possible.

---

## Formula

```text
Recall =
TP
------------
TP + FN
```

---

## Example

Using our confusion matrix:

```text
TP = 35
FN = 10
```

Substituting:

```text
Recall =
35
----------
35 + 10

=
35 / 45

=
0.778
```

```text
Recall = 77.8%
```

---

## Interpretation

A recall of 77.8% means:

> The model successfully identified about 78% of all infected patients.

---

## Why Recall Matters

In healthcare:

```text
Missing an infected patient
```

can be more dangerous than

```text
Incorrectly flagging a healthy person.
```

High recall helps ensure that most actual positive cases are detected.

---

# Precision vs Recall

These metrics often compete with each other.

Imagine reducing the threshold for COVID detection.

Result:

```text
More patients predicted positive.
```

Advantages:

```text
Higher Recall
```

Disadvantages:

```text
More False Positives
Lower Precision
```

---

# Example

### Model A

```text
Precision = 95%
Recall = 60%
```

The model is very careful before predicting positive.

---

### Model B

```text
Precision = 75%
Recall = 95%
```

The model catches almost every infected patient but generates more false alarms.

Neither model is universally better.

The choice depends on the business problem.

---

# When Precision is Important

Use cases where false positives are costly:

- Spam Detection
- Fraud Alerts
- Legal Investigations

Example:

```text
Important emails should not be marked as spam.
```

---

# When Recall is Important

Use cases where false negatives are costly:

- COVID Detection
- Cancer Detection
- Fraud Detection
- Security Threat Detection

Example:

```text
Missing a cancer patient can be extremely dangerous.
```

---

# 4. F1 Score

## What is F1 Score?

Sometimes we need a single metric that considers both Precision and Recall.

F1 Score provides a balance between them.

It is the harmonic mean of Precision and Recall.

---

## Formula

```text
F1 Score =
2 × Precision × Recall
--------------------------------
Precision + Recall
```

---

## Example

Using:

```text
Precision = 0.875
Recall = 0.778
```

Substituting:

```text
F1 =
2 × 0.875 × 0.778
---------------------
0.875 + 0.778

≈ 0.824
```

```text
F1 Score ≈ 82.4%
```

---

## Interpretation

An F1 Score of 82.4% means:

> The model maintains a good balance between Precision and Recall.

---

## Why Use F1 Score?

Suppose two models have:

### Model A

```text
Precision = 99%
Recall = 30%
```

### Model B

```text
Precision = 85%
Recall = 85%
```

Model A looks impressive based on precision.

However:

```text
It misses many actual positives.
```

F1 Score helps identify models that maintain a balance.

---

# Quick Summary of Metrics

## Accuracy

Answers:

```text
How many predictions were correct overall?
```

Formula:

```text
(TP + TN) / Total
```

---

## Precision

Answers:

```text
When the model predicts Positive,
how often is it correct?
```

Formula:

```text
TP / (TP + FP)
```

---

## Recall

Answers:

```text
Out of all actual Positive cases,
how many were found?
```

Formula:

```text
TP / (TP + FN)
```

---

## F1 Score

Answers:

```text
How well does the model balance
Precision and Recall?
```

Formula:

```text
2 × Precision × Recall
----------------------
Precision + Recall
```

---

# Metric Comparison

| Metric | Focus |
|----------|---------|
| Accuracy | Overall Correct Predictions |
| Precision | Quality of Positive Predictions |
| Recall | Ability to Find Positive Cases |
| F1 Score | Balance Between Precision and Recall |

---

# Which Metric Should You Use?

## Use Accuracy When

- Classes are balanced
- Overall correctness is important

---

## Use Precision When

- False positives are costly

Examples:

- Spam Detection
- Fraud Alerts

---

## Use Recall When

- False negatives are costly

Examples:

- COVID Detection
- Cancer Detection

---

## Use F1 Score When

- Both Precision and Recall matter
- Dataset is imbalanced
- You need a single balanced metric

---

# Summary

Classification models are evaluated using metrics derived from the Confusion Matrix.

The most common metrics are:

### Accuracy

Measures overall correctness.

```text
Higher is Better
```

---

### Precision

Measures how reliable positive predictions are.

```text
Higher is Better
```

---

### Recall

Measures how many actual positive cases were identified.

```text
Higher is Better
```

---

### F1 Score

Measures the balance between Precision and Recall.

```text
Higher is Better
```

A good classification model typically aims for:

```text
High Accuracy
High Precision
High Recall
High F1 Score
```

However, the most important metric depends on the problem you are trying to solve.

> Accuracy tells us how often the model is correct.
>
> Precision tells us how trustworthy positive predictions are.
>
> Recall tells us how many actual positives were found.
>
> F1 Score tells us how well Precision and Recall are balanced.

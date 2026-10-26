# Precision vs Recall in Machine Learning

When building a classification model, we need to evaluate how well it predicts the correct classes.

Two important evaluation metrics are **Precision** and **Recall**.

Both use True Positives (TP), False Positives (FP), and False Negatives (FN), but they answer different questions.

To understand them, let's use a COVID-19 detection model as an example.

---

## 1. Understanding the COVID-19 Example

Imagine we build a Machine Learning model that predicts whether a person has COVID-19.

The model can make two predictions:

- **Positive:** The person is predicted to have COVID-19.
- **Negative:** The person is predicted not to have COVID-19.

After testing the model on 100 people, suppose we get these results:

| Actual / Predicted | Predicted Positive | Predicted Negative |
|---|---:|---:|
| Actual Positive | 40 (TP) | 10 (FN) |
| Actual Negative | 10 (FP) | 40 (TN) |

Let's understand the important terms:

- **True Positive (TP):** The person has COVID-19, and the model correctly predicts Positive.
- **False Positive (FP):** The person does not have COVID-19, but the model predicts Positive.
- **False Negative (FN):** The person has COVID-19, but the model predicts Negative.
- **True Negative (TN):** The person does not have COVID-19, and the model correctly predicts Negative.

We will use these values to understand Precision and Recall.

---

# 2. What Is Precision?

Precision answers this question:

> Out of all the people the model predicted as COVID-positive, how many actually have COVID-19?

In simple terms, **Precision tells us how trustworthy the model's positive predictions are.**

## Formula

```text
Precision = TP / (TP + FP)
```

Here:

- TP = Correctly predicted positive cases
- FP = Incorrectly predicted positive cases

Notice that the denominator contains **TP + FP**, which represents everyone the model predicted as Positive.

## Example

From our confusion matrix:

```text
TP = 40
FP = 10
```

Therefore:

```text
Precision = TP / (TP + FP)

          = 40 / (40 + 10)

          = 40 / 50

          = 0.80

Precision = 80%
```

### What Does This Mean?

The model predicted 50 people as COVID-positive.

However, only 40 of them actually had COVID-19.

Therefore, 80% of the model's positive predictions were correct.

---

## 3. How Does False Positive Affect Precision?

Let's understand the relationship between False Positives and Precision.

Suppose the model predicts 50 people as COVID-positive.

### Case 1: More False Positives

```text
TP = 30
FP = 20
```

```text
Precision = 30 / (30 + 20)

          = 30 / 50

          = 60%
```

Only 60% of the positive predictions were correct.

### Case 2: Fewer False Positives

Now suppose the model correctly identifies 45 positive cases and incorrectly flags only 5 healthy people.

```text
TP = 45
FP = 5
```

```text
Precision = 45 / (45 + 5)

          = 45 / 50

          = 90%
```

Precision has increased from 60% to 90%.

### What Did We Learn?

When the number of True Positives remains fixed, reducing False Positives increases Precision.

Why?

Because fewer healthy people are incorrectly classified as infected.

**Remember:**

> To improve Precision, we want to reduce False Positives relative to the number of positive predictions.

However, reducing False Positives alone does not guarantee that Precision will increase if the number of True Positives also changes.

---

# 4. When Should We Use Precision?

Precision is especially important when **False Positives are costly**.

In other words, we want to avoid incorrectly predicting that something belongs to the positive class.

### Example 1: Spam Detection

Imagine Gmail predicts whether an email is Spam.

- TP: An actual spam email is correctly identified as spam.
- FP: An important email is incorrectly marked as spam.

If False Positives increase, more legitimate emails end up in the spam folder.

Therefore, we want high Precision so that emails classified as spam are actually spam.

### Example 2: Fraud Detection

Imagine a bank's model identifies fraudulent transactions.

If the model incorrectly flags legitimate transactions as fraudulent, customers may be unable to make payments.

High Precision helps reduce these false alarms.

### Example 3: COVID-19 Screening

High Precision means that people flagged as potentially infected are more likely to actually be infected, reducing unnecessary follow-up testing.

However, Precision alone does not tell us whether the model is missing many infected people.

That is where Recall becomes important.

---

# 5. What Is Recall?

Recall answers this question:

> Out of all the people who actually have COVID-19, how many did the model correctly identify?

In simple terms, **Recall tells us how many of the actual positive cases the model successfully finds.**

## Formula

```text
Recall = TP / (TP + FN)
```

Here:

- TP = Correctly predicted positive cases
- FN = Actual positive cases missed by the model

Notice that the denominator contains **TP + FN**, which represents everyone who actually belongs to the positive class.

## Example

From our original confusion matrix:

```text
TP = 40
FN = 10
```

Therefore:

```text
Recall = TP / (TP + FN)

       = 40 / (40 + 10)

       = 40 / 50

       = 0.80

Recall = 80%
```

### What Does This Mean?

There were 50 people who actually had COVID-19.

The model correctly identified 40 of them and missed 10.

Therefore, the model detected 80% of all actual COVID-positive cases.

---

# 6. How Does False Negative Affect Recall?

Let's understand the relationship between False Negatives and Recall.

Suppose 50 people actually have COVID-19.

### Case 1: More False Negatives

```text
TP = 30
FN = 20
```

```text
Recall = 30 / (30 + 20)

       = 30 / 50

       = 60%
```

The model identifies only 60% of the actual positive cases.

### Case 2: Fewer False Negatives

Now suppose the model identifies 45 infected people and misses only 5.

```text
TP = 45
FN = 5
```

```text
Recall = 45 / (45 + 5)

       = 45 / 50

       = 90%
```

Recall has increased from 60% to 90%.

### What Did We Learn?

When the number of actual positive cases remains fixed, reducing False Negatives increases Recall.

Why?

Because the model is missing fewer people who actually have COVID-19.

**Remember:**

> To improve Recall, we want to reduce False Negatives relative to the number of actual positive cases.

In practice, a change to the model can affect both True Positives and False Negatives, so we must evaluate the resulting Recall rather than assuming it will always improve.

---

# 7. When Should We Use Recall?

Recall is especially important when **False Negatives are costly**.

In other words, we want to avoid missing actual positive cases.

### Example 1: COVID-19 Detection

A False Negative means an infected person is incorrectly classified as healthy.

This person may not realize they are infected and could spread the disease to others.

Therefore, high Recall is important when the goal is to identify as many infected people as possible.

### Example 2: Cancer Screening

A False Negative means a patient who actually has cancer is incorrectly classified as not having cancer.

Missing such a case could delay further testing and diagnosis.

Therefore, Recall can be especially important in screening systems.

### Example 3: Security Threat Detection

A security system may identify malicious files or attacks.

A False Negative means a real threat goes undetected.

High Recall helps the system identify more of the actual threats.

---

# 8. Precision vs Recall: The Key Difference

Both metrics use True Positives, but their denominators are different.

| Precision | Recall |
|---|---|
| `TP / (TP + FP)` | `TP / (TP + FN)` |
| Looks at predicted positives | Looks at actual positives |
| Focuses on reducing False Positives | Focuses on reducing False Negatives |
| Asks, "How many positive predictions were correct?" | Asks, "How many actual positives did we find?" |
| Important when false alarms are costly | Important when missing positive cases is costly |

The easiest way to remember the difference is:

**Precision looks at what the model predicted.**

**Recall looks at what actually happened.**

---

# 9. Why Does the Denominator Matter?

Let's focus on the idea that a smaller error count in the denominator can improve the metric.

## Precision

```text
Precision = TP / (TP + FP)
```

The denominator is the total number of predicted positives.

If TP stays fixed and FP decreases:

```text
TP + FP decreases
```

Therefore, Precision increases.

Example:

```text
40 / (40 + 20) = 66.7%

40 / (40 + 10) = 80%

40 / (40 + 5)  = 88.9%
```

As FP decreases while TP remains fixed, Precision increases.

## Recall

```text
Recall = TP / (TP + FN)
```

The denominator is the total number of actual positives.

If TP stays fixed and FN decreases:

```text
TP + FN decreases
```

Therefore, Recall increases.

Example:

```text
40 / (40 + 20) = 66.7%

40 / (40 + 10) = 80%

40 / (40 + 5)  = 88.9%
```

As FN decreases while TP remains fixed, Recall increases.

### Important Clarification

We should not simply say that making the denominator smaller always increases Precision or Recall.

The numerator and denominator are related:

- Reducing FP while TP stays fixed increases Precision.
- Reducing FN while TP stays fixed increases Recall.
- Increasing TP while keeping FP fixed increases Precision.
- Increasing TP while keeping FN fixed increases Recall.

The real goal is to improve the ratio by making more correct positive predictions and fewer relevant errors.

---

# 10. Can We Have High Precision but Low Recall?

Yes!

Imagine a COVID-19 detection model that predicts Positive only when it is extremely confident.

It flags very few people as infected.

Most of the people it flags genuinely have COVID-19, but it misses many other infected people.

Example:

```text
TP = 20
FP = 2
FN = 30
```

Precision:

```text
20 / (20 + 2) = 90.9%
```

Recall:

```text
20 / (20 + 30) = 40%
```

The model has high Precision but low Recall.

**Interpretation:** Its positive predictions are usually correct, but it detects only 40% of all actual positive cases.

---

# 11. Can We Have High Recall but Low Precision?

Yes!

Imagine a COVID-19 model that predicts Positive whenever it detects even a small possibility of infection.

It identifies most infected people, but it also flags many healthy people.

Example:

```text
TP = 45
FP = 25
FN = 5
```

Precision:

```text
45 / (45 + 25) = 64.3%
```

Recall:

```text
45 / (45 + 5) = 90%
```

The model has high Recall but lower Precision.

**Interpretation:** It detects 90% of all actual positive cases, but many of its positive predictions are false alarms.

---

# 12. The Role of the Classification Threshold

In many classification models, the model produces a probability rather than an immediate class label.

For example:

```text
Predicted probability of COVID = 0.70
```

If the classification threshold is 0.50, the model predicts Positive.

If we raise the threshold to 0.90, the model may predict Negative for that same probability.

Changing the threshold affects which cases are classified as positive.

Generally:

- **Lower threshold:** More positive predictions, often higher Recall and lower Precision.
- **Higher threshold:** Fewer positive predictions, often higher Precision and lower Recall.

These are common tendencies, not guarantees. The actual effect depends on the data and the model's predictions.

This is why the threshold should be chosen based on the consequences of False Positives and False Negatives.

---

# 13. How to Choose Between Precision and Recall

| Situation | Metric to Prioritize | Reason |
|---|---|---|
| Spam detection | Precision | Avoid marking legitimate emails as spam |
| Fraud alerts | Depends on the costs | Balance missed fraud against false alarms |
| Cancer screening | Recall may be prioritized | Avoid missing actual cases |
| COVID-19 screening | Recall may be prioritized | Identify as many actual cases as possible |
| Security threat detection | Recall may be prioritized | Avoid missing genuine threats |

In real-world applications, we often monitor both metrics. The choice depends on the risks, costs, and requirements of the specific problem.

---

# 14. How to Explain Precision and Recall in an Interview

### Question: What is Precision?

**Interview Answer:**

"Precision tells us, out of all the positive predictions made by our model, how many were actually positive. Its formula is TP divided by TP plus FP. We focus on Precision when False Positives are costly, such as in spam detection, where we don't want legitimate emails to be marked as spam."

### Question: What is Recall?

**Interview Answer:**

"Recall tells us, out of all the actual positive cases, how many our model correctly identified. Its formula is TP divided by TP plus FN. We focus on Recall when False Negatives are costly, such as in cancer screening, where we don't want to miss actual cases."

### Question: What Is the Difference Between Precision and Recall?

**Interview Answer:**

"Precision focuses on the reliability of positive predictions, whereas Recall focuses on finding actual positive cases. Precision is affected by False Positives, while Recall is affected by False Negatives."

---

# Final Summary

## Precision

```text
Precision = TP / (TP + FP)
```

- Measures how reliable positive predictions are.
- Focuses on reducing False Positives.
- Useful when false alarms are costly.

## Recall

```text
Recall = TP / (TP + FN)
```

- Measures how many actual positive cases are identified.
- Focuses on reducing False Negatives.
- Useful when missing actual cases is costly.

## The Easiest Way to Remember

> **Precision:** Of the cases I predicted Positive, how many were actually Positive?

> **Recall:** Of the cases that were actually Positive, how many did I successfully find?

Remember that neither metric is universally more important. The right choice depends on the problem and the consequences of the model's mistakes.

# F-Score in Machine Learning: F1, F2, and F0.5 Score

When evaluating a classification model, we often use two important metrics:

- **Precision:** Out of all the positive predictions made by the model, how many were actually positive?
- **Recall:** Out of all the actual positive cases, how many did the model correctly identify?

But what if we want to consider both Precision and Recall using a single metric?

This is where the **F-Score** comes into the picture.

The F-Score combines Precision and Recall into a single value. By changing a parameter called **Beta (β)**, we can control how much emphasis the score places on Precision versus Recall.

The most commonly used versions are:

- F1 Score
- F2 Score
- F0.5 Score

---

## 1. What Is the F-Score?

The F-Score, also called the F-beta Score, is a classification evaluation metric that combines Precision and Recall using their harmonic mean.

It is useful when we want to evaluate a model based on both the reliability of its positive predictions and its ability to identify actual positive cases.

For example, consider a model that detects COVID-19.

- Precision tells us how many people predicted as infected actually have COVID-19.
- Recall tells us how many people who actually have COVID-19 were identified by the model.

Depending on the application, we might want to give equal importance to both metrics or prioritize one over the other.

The F-beta Score allows us to do this.

---

## 2. The F-beta Score Formula

The general formula is:

```text
Fβ Score = (1 + β²) × (Precision × Recall)
           ----------------------------------
           (β² × Precision) + Recall
```

Where:

- **Precision (P):** Reliability of positive predictions.
- **Recall (R):** Ability to identify actual positive cases.
- **Beta (β):** Controls the relative emphasis on Precision and Recall.
- **β²:** The square of the beta value.

The beta value determines which metric receives more emphasis in the F-score calculation.

| Beta Value | F-Score | Relative Emphasis |
|---|---|---|
| β = 0.5 | F0.5 Score | Precision |
| β = 1 | F1 Score | Equal emphasis on Precision and Recall |
| β = 2 | F2 Score | Recall |

Let's understand each one.

---

## 3. F1 Score: Balancing Precision and Recall

### What Is F1 Score?

F1 Score is used when we want to balance Precision and Recall equally.

When β = 1, the general F-beta formula becomes:

```text
F1 = (1 + 1²) × (P × R)
     --------------------
     (1² × P) + R
```

Simplifying:

```text
F1 = 2 × (P × R)
     ------------
        P + R
```

### Example

Suppose a classification model has:

```text
Precision = 80%
Recall    = 60%
```

Convert the percentages into decimals:

```text
P = 0.80
R = 0.60
```

Calculate F1 Score:

```text
F1 = 2 × (0.80 × 0.60)
     -------------------
          0.80 + 0.60

   = 0.96 / 1.40

   ≈ 0.686
```

Therefore:

```text
F1 Score ≈ 68.6%
```

### When Should We Use F1 Score?

Use F1 Score when both Precision and Recall are important and you want a balanced evaluation of the two.

Example: A classification system where both false alarms and missed positive cases matter.

**Remember:** F1 Score gives equal relative emphasis to Precision and Recall, but their actual values do not have to be equal.

---

## 4. F2 Score: Giving More Emphasis to Recall

### What Is F2 Score?

F2 Score is used when Recall is more important than Precision.

In the formula, we set:

```text
β = 2
β² = 4
```

Substituting these values:

```text
F2 = (1 + 4) × (P × R)
     ------------------
         (4 × P) + R
```

Simplifying:

```text
F2 = 5 × (P × R)
     ------------
       4P + R
```

Notice that the formula gives Recall more relative emphasis than Precision.

### Example

Suppose:

```text
Precision = 80%
Recall    = 60%
```

Therefore:

```text
P = 0.80
R = 0.60
```

Calculate F2 Score:

```text
F2 = 5 × (0.80 × 0.60)
     ------------------
       (4 × 0.80) + 0.60

   = 2.40 / 3.80

   ≈ 0.632
```

Therefore:

```text
F2 Score ≈ 63.2%
```

### When Should We Use F2 Score?

Use F2 Score when missing actual positive cases is more costly than generating false alarms.

Examples:

- Disease screening
- Detecting security threats
- Identifying potentially fraudulent activity when missed fraud is especially costly

In a disease-screening application, a False Negative means an actual patient goes undetected. If avoiding missed cases is the priority, Recall deserves greater emphasis.

**Remember:** F2 Score emphasizes Recall, but it does not guarantee high Recall. The model's actual Precision and Recall still determine the score.

---

## 5. F0.5 Score: Giving More Emphasis to Precision

### What Is F0.5 Score?

F0.5 Score is used when Precision is more important than Recall.

In the formula, we set:

```text
β = 0.5
β² = 0.25
```

Substituting these values:

```text
F0.5 = (1 + 0.25) × (P × R)
       ----------------------
           (0.25 × P) + R
```

Simplifying:

```text
F0.5 = 1.25 × (P × R)
       ----------------
          0.25P + R
```

This gives Precision more relative emphasis than Recall.

### Example

Using the same values:

```text
Precision = 80%
Recall    = 60%
```

Therefore:

```text
P = 0.80
R = 0.60
```

Calculate F0.5 Score:

```text
F0.5 = 1.25 × (0.80 × 0.60)
       ---------------------
         (0.25 × 0.80) + 0.60

     = 0.60 / 0.80

     = 0.75
```

Therefore:

```text
F0.5 Score = 75%
```

### When Should We Use F0.5 Score?

Use F0.5 Score when false positive predictions are particularly costly.

Examples:

- Spam detection, when incorrectly filtering legitimate emails is costly
- Fraud alerts, when false alarms trigger expensive investigations
- Automated content moderation, when incorrectly flagging legitimate content is a significant concern

**Remember:** F0.5 Score emphasizes Precision, but it does not guarantee high Precision. The model's actual Precision and Recall determine the final score.

---

## 6. Comparing F1, F2, and F0.5 Scores

Using the same model with Precision = 80% and Recall = 60%:

| Metric | Beta (β) | Score | Emphasis |
|---|---:|---:|---|
| F0.5 Score | 0.5 | 75.0% | Precision |
| F1 Score | 1 | 68.6% | Equal relative emphasis |
| F2 Score | 2 | 63.2% | Recall |

Notice that the scores differ even though Precision and Recall remain unchanged.

This happens because each F-score weights Precision and Recall differently.

In this example, Precision is higher than Recall. Therefore, the scores that emphasize Precision are higher than the scores that emphasize Recall.

**Important:** A higher F-score does not automatically mean a model is better than another model evaluated using a different beta value. When comparing models, use the same metric and beta value to ensure a meaningful comparison.

---

## 7. What Does Beta Actually Control?

Beta is not a percentage that directly specifies how much weight a metric receives.

Instead, the formula uses β² to control the relative emphasis.

- **β = 1:** Equal relative emphasis on Precision and Recall.
- **β > 1:** More emphasis on Recall.
- **β < 1:** More emphasis on Precision.

For example:

```text
β = 2
β² = 4
```

This gives Recall more relative emphasis.

Similarly:

```text
β = 0.5
β² = 0.25
```

This gives Precision more relative emphasis.

The beta value should be selected according to the consequences of false positive and false negative predictions in the application.

---

## 8. How to Remember the F-Scores

Think about the problem you are trying to solve.

### F1 Score

Do we care about both Precision and Recall equally?

Use **F1 Score**.

### F2 Score

Is missing an actual positive case especially costly?

Use **F2 Score** to emphasize Recall.

### F0.5 Score

Are false positive predictions especially costly?

Use **F0.5 Score** to emphasize Precision.

A simple memory trick:

```text
Beta > 1  → Recall gets more emphasis
Beta = 1  → Equal relative emphasis
Beta < 1  → Precision gets more emphasis
```

---

## 9. Important Things to Remember

- F1, F2, and F0.5 are all classification evaluation metrics.
- All three combine Precision and Recall into a single score.
- Their values generally range from 0 to 1, or 0% to 100%.
- Higher values indicate a better Precision-Recall balance according to the chosen beta value.
- F1 Score uses the harmonic mean, not the ordinary arithmetic mean.
- F2 Score prioritizes Recall, while F0.5 Score prioritizes Precision.
- The beta value does not directly change the trained model; it changes how we evaluate the model.
- Choosing an F-score does not automatically improve Precision or Recall. It helps us evaluate models according to our priorities.

## Final Summary

| Metric | Formula | When to Use |
|---|---|---|
| F1 Score | `2PR / (P + R)` | When Precision and Recall have equal relative importance |
| F2 Score | `5PR / (4P + R)` | When Recall deserves more emphasis |
| F0.5 Score | `1.25PR / (0.25P + R)` | When Precision deserves more emphasis |

The general F-beta formula is:

```text
Fβ = (1 + β²) × (P × R)
     --------------------
       (β² × P) + R
```

The most important takeaway is:

**F1 balances Precision and Recall, F2 emphasizes Recall, and F0.5 emphasizes Precision.**

Choose the metric based on the type of prediction errors that matter most in your application.

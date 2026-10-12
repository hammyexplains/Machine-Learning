# Can an 85% Accuracy Model Be Better Than a 95% Accuracy Model?

Imagine you're building a Machine Learning model to detect fraudulent UPI transactions.

You train two models:

- **Model A:** 95% accuracy
- **Model B:** 85% accuracy

Which model would you choose?

At first glance, Model A seems better because it has higher accuracy. But what if Model A misses most fraudulent transactions while Model B detects almost all of them?

Let's understand why **higher accuracy doesn't always mean a better model.**

## 1. Understanding Our Dataset

Suppose we have 10,000 UPI transactions in our dataset.

| Transaction type | Number of transactions |
|---|---:|
| Genuine transactions | 9,900 |
| Fraudulent transactions | 100 |
| **Total** | **10,000** |

Notice that genuine transactions make up 99% of the dataset, while fraudulent transactions make up only 1%.

This is called **class imbalance**: one category has far more examples than the other.

## 2. How Can a Model Achieve High Accuracy and Still Be Bad?

Imagine we build a model that predicts every transaction as genuine.

It correctly identifies all 9,900 genuine transactions, but it fails to detect all 100 fraudulent transactions.

Its accuracy is:

\[
\text{Accuracy}=\frac{\text{Correct Predictions}}{\text{Total Predictions}}\times100
\]

\[
=\frac{9900}{10000}\times100=99\%
\]

The model has 99% accuracy, but it detects **zero fraudulent transactions**!

Why? Because the dataset contains so many genuine transactions that the model can achieve high accuracy simply by predicting the majority category.

This shows why accuracy alone can be misleading.

## 3. Let's Compare Our Two Models

Suppose both models produce the following results:

| Metric | Model A | Model B |
|---|---:|---:|
| Accuracy | 95% | 85% |
| Fraud detected (out of 100) | 20 | 80 |
| Fraud missed | 80 | 20 |

These are hypothetical results used to explain the concept.

### Model A — 95% Accuracy

Model A correctly classifies 95% of all transactions. However, it detects only 20 of the 100 fraudulent transactions.

That means it misses 80 fraudulent transactions.

### Model B — 85% Accuracy

Model B correctly classifies 85% of all transactions. Its overall accuracy is lower, but it detects 80 of the 100 fraudulent transactions.

It misses only 20 fraudulent transactions.

If our primary goal is to prevent fraud, Model B may be the better choice, even though its accuracy is lower.

**Important:** Accuracy alone cannot tell us how many fraudulent transactions a model detects. We need to examine its actual predictions and other evaluation metrics.

## 4. Which Metrics Should We Look At?

Apart from accuracy, two important metrics help us evaluate fraud detection models.

### Recall — How Much Fraud Can We Catch?

Recall tells us what proportion of all actual fraudulent transactions the model successfully detects.

\[
\text{Recall}=\frac{TP}{TP+FN}
\]

Here:

- **TP (True Positive):** Fraudulent transactions correctly identified as fraud.
- **FN (False Negative):** Fraudulent transactions incorrectly identified as genuine.

For our example:

- Model A recall = 20/100 = 20%
- Model B recall = 80/100 = 80%

Model B detects a much larger proportion of fraudulent transactions.

### Precision — How Many Fraud Alerts Are Correct?

Precision tells us what proportion of the transactions flagged as fraudulent are actually fraudulent.

\[
\text{Precision}=\frac{TP}{TP+FP}
\]

Here, **FP (False Positive)** means a genuine transaction is incorrectly flagged as fraudulent.

If a model flags too many genuine transactions, customers may experience unnecessary payment blocks or verification requests.

Therefore, a fraud detection system must consider both catching fraud and avoiding too many false alarms.

## 5. So, Which Model Is Better?

The answer depends on the **problem statement and the objective of the project.**

| Problem | What matters most? |
|---|---|
| Fraud detection | Catching fraud while managing false alarms |
| Disease screening | Identifying as many actual cases as possible |
| Spam detection | Catching spam without incorrectly blocking genuine emails |
| House price prediction | How close predicted prices are to actual prices |

For fraud detection, we may prioritize recall because missing fraudulent transactions can be costly. However, precision, operational costs, and customer experience also matter.

For another problem, a different metric may be more important.

## 6. The Final Takeaway

When choosing a Machine Learning model, don't simply ask:

"Which model has the highest accuracy?"

Instead, ask:

- What problem am I trying to solve?
- What are the consequences of incorrect predictions?
- Which evaluation metrics best measure success for this problem?

**A model with 95% accuracy is not automatically better than a model with 85% accuracy. The better model is the one that meets the objective of the problem more effectively.**

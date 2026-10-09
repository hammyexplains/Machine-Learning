# Interview Question: Which Train-Validation-Test Split Ratio Do You Use — 70-15-15 or 80-10-10?

## 1. Introduction

There is no fixed rule that says we must always use a 70-15-15 or 80-10-10 split. The choice depends mainly on **the size of the dataset, the complexity of the problem, and how reliably we need to evaluate the model.**

Before choosing a ratio, we should understand the purpose of each dataset split.

## 2. Understanding the Three Splits

When building a machine learning model, we generally divide the available data into three parts:

- **Training set:** Used to train the model so it can learn patterns from the data.
- **Validation set:** Used to compare different models, tune hyperparameters, and select the best model.
- **Test set:** Used at the end to evaluate how well the selected model performs on unseen data.

Think of it like preparing for an exam. Training data is like studying your textbook, validation data is like taking practice tests, and test data is like taking the final exam.

The test set should remain untouched during model selection so that the final evaluation is fair.

## 3. When Should You Use a 70-15-15 Split?

In a 70-15-15 split:

- 70% of the data is used for training.
- 15% is used for validation.
- 15% is used for testing.

Suppose you have 10,000 rows:

| Dataset | Number of rows |
|---|---:|
| Training | 7,000 |
| Validation | 1,500 |
| Testing | 1,500 |

This split can be useful when you have enough data to train the model and want relatively larger validation and test sets.

**Advantages:**
- Provides more data for validation and testing.
- Can help produce more reliable evaluation estimates when the dataset is sufficiently large.
- Useful when comparing multiple models or tuning hyperparameters.

**Limitation:** The model receives fewer training examples than it would with an 80-10-10 split. This may matter when learning patterns requires more data.

## 4. When Should You Use an 80-10-10 Split?

In an 80-10-10 split:

- 80% of the data is used for training.
- 10% is used for validation.
- 10% is used for testing.

With 10,000 rows:

| Dataset | Number of rows |
|---|---:|
| Training | 8,000 |
| Validation | 1,000 |
| Testing | 1,000 |

This split gives the model more examples to learn from while maintaining separate validation and test sets.

**Advantages:**
- More training data may help the model learn better patterns.
- Provides separate datasets for model selection and final evaluation.
- A reasonable starting point for many sufficiently large datasets.

**Limitation:** The validation and test sets are smaller. If the dataset contains rare classes or unusual examples, these sets may not contain enough examples to evaluate performance reliably.

## 5. So, Which One Is Better?

Neither split is universally better. The right choice depends on the dataset and the evaluation requirements.

| Situation | Possible approach |
|---|---|
| Large dataset with plenty of examples | 70-15-15 or 80-10-10 |
| More data needed for training | Consider 80-10-10 |
| Larger validation and test sets desired | Consider 70-15-15 |
| Small dataset | Consider K-fold cross-validation |
| Time-series data | Split chronologically |
| Imbalanced classification data | Consider stratified splitting |

These are starting points, not strict rules. For example, even a large dataset may need a different strategy if the positive class is extremely rare.

## 6. What If You Have a Small Dataset?

Suppose you have only 100 rows.

With an 80-10-10 split, you would have:
- 80 training rows.
- 10 validation rows.
- 10 test rows.

Evaluating the model on only 10 test rows can be unreliable. Just one incorrect prediction changes the accuracy by 10 percentage points.

In this situation, K-fold cross-validation can help you evaluate the model using different portions of the available data.

### How does K-fold cross-validation work?

Suppose you choose five-fold cross-validation with 100 rows.

1. Divide the data into five folds, each containing 20 rows.
2. Train the model on four folds (80 rows) and validate it on the remaining fold (20 rows).
3. Repeat the process five times, changing the validation fold each time.
4. Calculate the average of the five validation scores.

Every row is used for validation once and for training in the other four rounds.

This provides a better view of how consistently the model performs across different subsets of the data.

**Important:** Cross-validation is generally used for model selection and performance estimation. If possible, keep a separate test set untouched until the final evaluation. For very small datasets, the final test estimate may still be uncertain because relatively few examples are available.

## 7. Other Factors That Affect the Split

Dataset size is important, but it is not the only consideration.

### Class imbalance

Imagine a fraud detection dataset in which 99% of transactions are legitimate and only 1% are fraudulent.

A random split might leave very few fraudulent transactions in the validation or test set. Stratified splitting can help preserve class proportions across the sets, provided there are enough examples.

### Time-series data

For stock prices or sales forecasting, randomly splitting rows can allow future information to influence training.

Instead, use earlier observations for training, later observations for validation, and the latest observations for testing.

### Data leakage

Data leakage happens when information from the validation or test data unintentionally influences model training.

For example, if you standardize features, calculate the scaling parameters using the training data only, then apply those same parameters to the validation and test data. During cross-validation, preprocessing should be fitted separately within each training fold.

## 8. Interview-Ready Answer

If an interviewer asks, "Which train-validation-test split ratio do you use: 70-15-15 or 80-10-10?", you can answer:

"I don't follow a fixed split ratio for every problem. I choose it based on the dataset size and evaluation requirements.

For a sufficiently large dataset, I might start with an 80-10-10 split because it provides more data for training while keeping separate validation and test sets. If I need larger validation and test sets, I may consider a 70-15-15 split.

For smaller datasets, a fixed split can leave too few examples for reliable evaluation, so I may use K-fold cross-validation for model selection and keep a separate test set for final evaluation whenever possible.

I also consider factors such as class imbalance, time-series ordering, and data leakage. Ultimately, my goal is to give the model enough data to learn while ensuring that its performance is evaluated fairly on unseen data."

## Key Takeaway

**Choose the split based on your data, not just a popular ratio.** Larger datasets often allow a simple train-validation-test split, while smaller datasets may benefit from cross-validation. Regardless of the approach, keep the final test data separate from model selection to obtain a fair evaluation.

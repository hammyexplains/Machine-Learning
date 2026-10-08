# You Have Only 100 Rows of Data. Would You Choose Train-Test Split or Cross Validation? Why?

## Short Answer

If I have only **100 rows of data**, I would generally prefer **Cross Validation** over a simple **Train-Test Split**.

The reason is simple:

> With such a small dataset, every row is valuable. Cross Validation allows us to use the data more effectively and gives a more reliable estimate of model performance.

---

# First, Why Do We Split Data at All?

Imagine you are preparing for an exam.

You have a workbook containing **100 questions**.

If you study all 100 questions and then test yourself using the same 100 questions, you might score very well.

But does that mean you truly understand the subject?

Not necessarily.

Maybe you just memorized the answers.

To know whether you have actually learned the concepts, you should test yourself using questions you haven't seen before.

Machine Learning works the same way.

We train a model on one set of data and evaluate it on unseen data.

This helps us understand whether the model has actually learned patterns or simply memorized the training data.

---

# What Is a Train-Test Split?

In a Train-Test Split, we divide the dataset into two parts.

For example:

- 80 rows → Training Data
- 20 rows → Testing Data

```text
100 Rows
│
├── 80 Rows → Train Model
│
└── 20 Rows → Test Model
```

The model learns from the 80 training rows.

After training, we evaluate it using the 20 testing rows.

---

# The Problem with Train-Test Split on Small Datasets

Suppose we have only 100 rows.

We decide to use an 80-20 split.

```text
Training Data = 80 Rows
Testing Data  = 20 Rows
```

Now imagine those 20 test rows happen to contain unusual examples.

The model's performance may look much worse than it actually is.

Similarly, if those 20 rows are very easy examples, the model may appear much better than it really is.

In other words:

> The result depends heavily on which rows happened to end up in the test set.

With a small dataset, this can create misleading conclusions.

---

# What Is Cross Validation?

Cross Validation solves this problem.

Instead of using only one train-test split, it performs multiple splits and evaluates the model several times.

The most common approach is **5-Fold Cross Validation**.

---

## 5-Fold Cross Validation Example

Suppose we have 100 rows.

We divide them into 5 equal groups.

```text
Fold 1 = 20 Rows
Fold 2 = 20 Rows
Fold 3 = 20 Rows
Fold 4 = 20 Rows
Fold 5 = 20 Rows
```

### Round 1

```text
Train: Fold 2 + Fold 3 + Fold 4 + Fold 5
Test : Fold 1
```

### Round 2

```text
Train: Fold 1 + Fold 3 + Fold 4 + Fold 5
Test : Fold 2
```

### Round 3

```text
Train: Fold 1 + Fold 2 + Fold 4 + Fold 5
Test : Fold 3
```

### Round 4

```text
Train: Fold 1 + Fold 2 + Fold 3 + Fold 5
Test : Fold 4
```

### Round 5

```text
Train: Fold 1 + Fold 2 + Fold 3 + Fold 4
Test : Fold 5
```

Finally, we average all the results.

This gives a more reliable estimate of performance.

---

# Real-Life Analogy

Imagine a teacher wants to evaluate a student.

### Train-Test Split

The teacher asks only one mock test.

```text
One Test → One Score
```

If the test is unusually easy or unusually difficult, the score may not accurately represent the student's ability.

---

### Cross Validation

The teacher conducts five different mock tests.

```text
Test 1
Test 2
Test 3
Test 4
Test 5
```

Then calculates the average score.

This provides a much better picture of the student's actual performance.

Cross Validation works in exactly the same way.

---

# Why Is Cross Validation Better for Small Datasets?

When you have only 100 rows:

### Train-Test Split

```text
80 rows used for learning
20 rows used for testing
```

Those 20 test rows are never used for training.

A significant portion of the data is effectively unavailable to the model during training.

---

### Cross Validation

Every row gets a chance to:

- Be used for training
- Be used for testing

This means we extract more information from the dataset.

As a result:

- Better utilization of data
- More stable performance estimates
- Less dependence on a single random split

---

# Does That Mean Cross Validation Is Always Better?

Not necessarily.

Cross Validation requires training the model multiple times.

For example:

### Train-Test Split

```text
Train Model → 1 Time
```

### 5-Fold Cross Validation

```text
Train Model → 5 Times
```

### 10-Fold Cross Validation

```text
Train Model → 10 Times
```

This increases computation time.

For very large datasets, a simple Train-Test Split is often sufficient because there is already plenty of data available.

---

# Rule of Thumb

### Small Dataset (Hundreds or Few Thousands of Rows)

Prefer:

```text
Cross Validation
```

Reason:

- Data is limited
- Need reliable evaluation
- Want to use data efficiently

---

### Large Dataset (Hundreds of Thousands or Millions of Rows)

Prefer:

```text
Train-Test Split
```

Reason:

- Plenty of training examples
- Faster computation
- Reliable results even with a single split

---

# Interview-Style Answer

**Question:** You have only 100 rows of data. Would you choose Train-Test Split or Cross Validation?

**Answer:**

I would generally choose Cross Validation because 100 rows is a very small dataset. A simple Train-Test Split may produce unreliable results depending on which samples end up in the test set. Cross Validation evaluates the model multiple times using different train-test combinations, allowing every row to contribute to both training and testing. This provides a more reliable estimate of model performance and makes better use of the limited data available.

---

# Key Takeaways

- Train-Test Split evaluates the model using one split of the data.
- Cross Validation evaluates the model using multiple splits.
- With only 100 rows, Cross Validation is usually preferred.
- Cross Validation makes better use of limited data.
- Cross Validation provides more stable and trustworthy performance estimates.
- The tradeoff is increased training time because the model is trained multiple times.

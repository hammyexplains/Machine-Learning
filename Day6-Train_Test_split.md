# Training Data and Testing Data in Machine Learning

Before a Machine Learning model can make predictions, it needs to learn patterns from data. However, simply training a model on all available data is not enough. We also need a way to evaluate how well the model performs on new, unseen data.

This is where **Training Data** and **Testing Data** come into the picture.

---

# What is Training Data?

Training Data is the portion of the dataset used to teach a Machine Learning model.

The model analyzes this data, identifies patterns, and learns relationships between input features and the target variable.

### Example

Suppose we want to predict whether a student will pass an exam.

| Hours Studied | Result |
|--------------|---------|
| 2 | Fail |
| 4 | Pass |
| 6 | Pass |
| 1 | Fail |

The model learns patterns such as:

> Students who study more hours are more likely to pass.

This learning process happens using the training data.

---

# What is Testing Data?

Testing Data is the portion of the dataset that is kept separate from the training process.

After the model has learned from the training data, it is evaluated using testing data to check how well it performs on data it has never seen before.

### Example

Testing Data:

| Hours Studied | Actual Result |
|--------------|---------------|
| 5 | Pass |
| 3 | Fail |

The model makes predictions on these records, and the predictions are compared with the actual results.

---

# Why Do We Split the Data?

Imagine a student preparing for an exam.

If the student practices using the same questions that appear in the final exam, scoring well doesn't necessarily mean they understand the subject. It may simply mean they memorized the answers.

Similarly, if we evaluate a Machine Learning model using the same data it was trained on, the results can be misleading.

To measure how well the model generalizes to new data, we test it on unseen data.

---

# Real-Life Analogy

Consider learning to drive a car.

### Training Phase

You practice driving on different roads and learn:

- Steering control
- Gear shifting
- Braking
- Traffic rules

### Testing Phase

You take a driving test on roads you haven't practiced on before.

If you perform well, it shows that you have genuinely learned how to drive rather than memorizing a specific route.

Machine Learning models are evaluated in the same way.

---

# Common Train-Test Split Ratios

A dataset is usually divided into two parts:

| Training Data | Testing Data |
|--------------|--------------|
| 80% | 20% |
| 70% | 30% |
| 75% | 25% |

The exact ratio depends on the size of the dataset.

A commonly used split is:

```text
80% Training Data
20% Testing Data
```

---

# Example

Suppose a dataset contains 1,000 records.

Using an 80-20 split:

```text
Training Data = 800 records
Testing Data = 200 records
```

The model learns from the 800 training records and is evaluated on the remaining 200 testing records.

---

# What Happens If We Don't Use Testing Data?

Without testing data:

- We cannot measure real-world performance.
- The model may simply memorize the training data.
- We won't know whether the model can handle unseen data.
- The model may suffer from overfitting.

As a result, the model may perform well during training but fail when deployed in production.

---

# Training Data vs Testing Data

| Training Data | Testing Data |
|--------------|--------------|
| Used to teach the model | Used to evaluate the model |
| Model learns patterns | Model makes predictions |
| Seen by the model during learning | Unseen during learning |
| Helps build the model | Helps measure performance |

---

# Summary

Training Data is used to teach a Machine Learning model by helping it learn patterns from historical data.

Testing Data is used to evaluate the model's ability to make accurate predictions on unseen data.

By splitting the dataset into training and testing sets, we can determine whether the model has truly learned meaningful patterns or has simply memorized the data.

> Training data helps the model learn, while testing data helps us verify how well it has learned.

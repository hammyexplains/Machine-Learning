# Overfitting and Underfitting in Machine Learning

When training a Machine Learning model, our goal is not just to perform well on the training data but also to make accurate predictions on new, unseen data.

However, models can sometimes learn too little or too much from the training data. These situations are known as **Underfitting** and **Overfitting**.

---

# What is Underfitting?

Underfitting occurs when a model is too simple to capture the patterns present in the data.

As a result, the model performs poorly on both the training data and the testing data.

## Example

Imagine trying to predict house prices using only the number of bedrooms.

In reality, house prices may depend on:

- Location
- Area
- Number of bathrooms
- Age of the house
- Nearby facilities

Using only one feature may not be enough to learn the true relationship.

The model misses important patterns and makes inaccurate predictions.

## Characteristics of Underfitting

- Low accuracy on training data
- Low accuracy on testing data
- Model fails to learn important patterns
- High bias

## Visual Representation

```text
Actual Pattern:     ~~~~~~~~
Model Prediction:   --------
```

The model is too simple and cannot follow the actual trend.

---

# What is Overfitting?

Overfitting occurs when a model learns the training data too well, including noise and unnecessary details.

Instead of learning general patterns, it memorizes the training data.

As a result, it performs very well on training data but poorly on testing data.

## Example

Imagine a student memorizing answers to previous exam questions without understanding the concepts.

If the same questions appear again, the student scores well.

But if new questions appear, the student struggles.

Machine Learning models can behave the same way.

## Characteristics of Overfitting

- Very high accuracy on training data
- Low accuracy on testing data
- Memorizes training data
- Poor generalization to unseen data
- High variance

## Visual Representation

```text
Actual Pattern:     ~~~~~~~~
Model Prediction:   /\/\/\/\/\/\/\
```

The model tries to fit every data point, including noise.

---

# Real-Life Analogy

## Underfitting

A student studies only one chapter for an exam covering ten chapters.

Result:

- Performs poorly in the exam
- Doesn't understand the complete syllabus

## Overfitting

A student memorizes every answer from previous papers.

Result:

- Scores well on familiar questions
- Struggles with new questions

## Good Fit

A student understands the concepts and practices enough questions.

Result:

- Performs well on both familiar and new questions

---

# Comparing Underfitting and Overfitting

| Underfitting | Overfitting |
|-------------|-------------|
| Model is too simple | Model is too complex |
| Learns too little | Learns too much |
| Poor training performance | Excellent training performance |
| Poor testing performance | Poor testing performance |
| High Bias | High Variance |
| Misses important patterns | Memorizes noise and details |

---

# Ideal Situation: Good Fit

A well-trained model should:

- Learn meaningful patterns
- Ignore unnecessary noise
- Perform well on training data
- Perform well on testing data
- Generalize to unseen data

This state is often called a **Good Fit** or **Balanced Model**.

```text
Training Accuracy  → High
Testing Accuracy   → High
```

---

# How to Reduce Underfitting

- Use more relevant features
- Train for more iterations
- Use a more powerful model
- Reduce excessive regularization
- Improve feature engineering

---

# How to Reduce Overfitting

- Collect more data
- Remove irrelevant features
- Use cross-validation
- Apply regularization
- Reduce model complexity
- Use pruning (for decision trees)
- Apply dropout (for neural networks)

---

# Summary

**Underfitting** occurs when a model is too simple and fails to learn important patterns from the data.

**Overfitting** occurs when a model learns the training data too well and memorizes noise instead of learning general patterns.

The goal of Machine Learning is to find a balance where the model learns meaningful patterns and performs well on unseen data.

> Underfitting means the model learns too little.
>
> Overfitting means the model learns too much.
>
> A good model learns just enough to generalize well on new data.

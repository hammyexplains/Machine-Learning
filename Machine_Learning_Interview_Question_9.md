# Regularization in Machine Learning

## 1. What Is Overfitting?

Overfitting happens when a machine learning model learns the training data too closely, including noise and unnecessary patterns. As a result, it performs well on training data but poorly on unseen data.

**Example:** A model memorizes the answers to practice questions instead of understanding the concepts. It performs well on familiar questions but struggles with new ones.

## 2. What Is Regularization?

Regularization is a technique used to reduce overfitting by discouraging a model from becoming unnecessarily complex.

It adds a penalty during training to control the model's weights, helping it learn general patterns rather than relying too heavily on specific details in the training data.

## 3. Types of Regularization

### L1 Regularization (Lasso)

L1 regularization penalizes the absolute values of model weights. It can reduce some weights to exactly zero, effectively removing those features from the model.

**When do we use it?**
- When a dataset contains many features, and some may be irrelevant.
- When we want automatic feature selection.
- When we want a simpler model using fewer features.

**Example:** When predicting house prices using 100 features, L1 may reduce the weights of less useful features to zero.

### L2 Regularization (Ridge)

L2 regularization penalizes the squared values of model weights. It reduces large weights toward zero but generally does not make them exactly zero.

**When do we use it?**
- When most features may contribute useful information.
- When we want to control large weights without eliminating features.
- When we want to reduce overfitting while retaining most or all features.

**Example:** When predicting student performance using study hours, attendance, and sleep duration, L2 can reduce excessively large weights while retaining the features.

## 4. L1 vs L2 Regularization

| Feature | L1 Regularization | L2 Regularization |
|---|---|---|
| Common name | Lasso | Ridge |
| Effect on weights | Can make weights exactly zero | Shrinks weights toward zero |
| Feature selection | Yes, can eliminate features | Generally does not eliminate features |
| Best used when | Many features may be irrelevant | Most features may be useful |

## 5. How Does Regularization Prevent Overfitting?

Without regularization, a model may assign excessively large weights to fit the training data closely.

Regularization penalizes such weights, encouraging the model to learn simpler relationships that may generalize better to unseen data.

However, too much regularization can make the model too simple, leading to underfitting. The strength of regularization should be chosen carefully.

## Key Takeaway

- **Overfitting:** The model learns the training data too closely.
- **Regularization:** Helps control model complexity.
- **L1:** Useful when we want to eliminate less useful features.
- **L2:** Useful when we want to reduce large weights while retaining features.

The goal is to build a model that performs well not only on training data but also on new, unseen data.

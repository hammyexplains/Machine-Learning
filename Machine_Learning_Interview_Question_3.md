### What Is a Validation Set in Machine Learning?

When building a Machine Learning model, we usually divide our dataset into three parts: Training Set, Validation Set, and Test Set. Each has a different purpose.

### 1\. Training Set — Learning

The training set is used to teach the model patterns from the data.

For example, if we're predicting house prices, the model learns from features such as house size, number of bedrooms, and location, along with the actual house prices.

### 2\. Validation Set — Improving the Model

The validation set is used to check the model's performance during development and decide how to improve it.

For example, suppose we're building a house price prediction model. We train the model and then evaluate it on the validation set.

Based on the validation results, we can:

* Compare different algorithms, such as Linear Regression and Random Forest.

* Tune hyperparameters, such as the depth of a decision tree.

* Identify overfitting and use techniques such as early stopping when appropriate.

We repeat this process until we select a model that performs well on the validation data.

Important: The validation set does not directly train the model through its loss calculation. Instead, its results guide our decisions about the model.

### 3\. Test Set — Final Evaluation

Once we've selected and finalized the model using the training and validation sets, we evaluate it on the test set.

The test set helps us estimate how well the model might perform on genuinely unseen data.

### Why Can't We Use the Test Set Instead of the Validation Set?

Imagine you're preparing for an exam.

* Training set: Your textbook and study materials.

* Validation set: Practice tests that help you identify mistakes and improve.

* Test set: Your final exam.

Suppose you repeatedly check your performance on the final exam and change your preparation based on its questions and results. Eventually, your preparation becomes tailored to that exam, so the result may no longer reflect how well you perform on a completely new exam.

The same principle applies to Machine Learning.

If we repeatedly evaluate our model on the test set and use those results to select algorithms, tune hyperparameters, or decide when to stop training, we indirectly adapt the model development process to the test data. This is called test-set leakage or overfitting to the test set.

As a result, the final test score may become overly optimistic and no longer provide an independent evaluation.

### Example: How They Work Together

Suppose you have 10,000 rows of data and choose an 80-10-10 split.

| Dataset    | Rows  | Purpose                          |
| ---------- | ----- | -------------------------------- |
| Training   | 8,000 | Learn patterns                   |
| Validation | 1,000 | Compare models and tune settings |
| Testing    | 1,000 | Evaluate the finalized model     |

The workflow is:

* Train the model using 8,000 rows.

* Evaluate it on 1,000 validation rows.

* Adjust the model or hyperparameters based on validation results.

* Repeat until you select a suitable model.

* Evaluate the finalized model on the 1,000 test rows, ideally only after all model-selection decisions are complete.

### Key Takeaway

Training data teaches the model, validation data helps us choose and improve the model, and test data evaluates the final model.

We keep the test set separate because we want an honest estimate of how well our model generalizes to data it has never encountered during development.

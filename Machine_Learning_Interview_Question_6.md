# True Positive, True Negative, False Positive, and False Negative

When working with Machine Learning classification models, we need to understand whether the model's predictions are correct or incorrect.

However, simply knowing that a prediction is wrong is not enough. We also need to understand **what the model predicted and what actually happened**.

To understand this, let's use a real-world example of a COVID-19 detection model.

## 1. Understanding the COVID-19 Example

Imagine we build a Machine Learning model that predicts whether a person has COVID-19 based on their medical test data.

The model can make two possible predictions:

- **Positive:** The model predicts that the person has COVID-19.
- **Negative:** The model predicts that the person does not have COVID-19.

The actual condition of the person can also be positive or negative.

By comparing the model's prediction with the person's actual condition, we get four possible outcomes:

1. True Positive (TP)
2. True Negative (TN)
3. False Positive (FP)
4. False Negative (FN)

---

## 2. True Positive (TP)

**Definition:** The model predicts Positive, and the actual result is also Positive.

In simple terms, the model correctly identifies a person who has COVID-19.

### Example

A person actually has COVID-19.

The model predicts that the person has COVID-19.

- Actual Result: Positive
- Predicted Result: Positive
- Outcome: True Positive

**Why is it called True Positive?**

- **True** means the prediction is correct.
- **Positive** means the model predicted the positive class.

Therefore, True Positive means the model correctly predicted a positive case.

---

## 3. True Negative (TN)

**Definition:** The model predicts Negative, and the actual result is also Negative.

In simple terms, the model correctly identifies a person who does not have COVID-19.

### Example

A person does not have COVID-19.

The model predicts that the person does not have COVID-19.

- Actual Result: Negative
- Predicted Result: Negative
- Outcome: True Negative

**Why is it called True Negative?**

- **True** means the prediction is correct.
- **Negative** means the model predicted the negative class.

Therefore, True Negative means the model correctly predicted a negative case.

---

## 4. False Positive (FP)

**Definition:** The model predicts Positive, but the actual result is Negative.

In simple terms, the model incorrectly identifies a healthy person as someone who has COVID-19.

### Example

A person does not have COVID-19.

However, the model predicts that the person has COVID-19.

- Actual Result: Negative
- Predicted Result: Positive
- Outcome: False Positive

**Why is it called False Positive?**

- **False** means the prediction is incorrect.
- **Positive** means the model predicted the positive class.

Therefore, False Positive means the model incorrectly predicted a positive case.

This type of error is also known as a **Type I Error** in the usual statistical hypothesis-testing terminology.

---

## 5. False Negative (FN)

**Definition:** The model predicts Negative, but the actual result is Positive.

In simple terms, the model incorrectly identifies a person who has COVID-19 as someone who does not have it.

### Example

A person actually has COVID-19.

However, the model predicts that the person does not have COVID-19.

- Actual Result: Positive
- Predicted Result: Negative
- Outcome: False Negative

**Why is it called False Negative?**

- **False** means the prediction is incorrect.
- **Negative** means the model predicted the negative class.

Therefore, False Negative means the model incorrectly predicted a negative case.

This type of error is also known as a **Type II Error** in the usual statistical hypothesis-testing terminology.

---

## 6. Confusion Matrix

A confusion matrix summarizes the four outcomes by comparing actual values with predicted values.

| Actual / Predicted | Predicted Positive | Predicted Negative |
|---|---|---|
| Actual Positive | True Positive (TP) | False Negative (FN) |
| Actual Negative | False Positive (FP) | True Negative (TN) |

Notice that the rows represent the **actual results**, while the columns represent the **predicted results**.

### Example with 100 Patients

Suppose we evaluate our COVID-19 detection model on 100 patients.

| Actual / Predicted | COVID Positive | COVID Negative |
|---|---:|---:|
| Actual Positive | 35 | 10 |
| Actual Negative | 5 | 50 |

Let's interpret the results:

- **TP = 35:** 35 infected patients were correctly identified.
- **TN = 50:** 50 healthy patients were correctly identified.
- **FP = 5:** 5 healthy patients were incorrectly identified as infected.
- **FN = 10:** 10 infected patients were incorrectly identified as healthy.

Total patients:

`35 + 50 + 5 + 10 = 100`

---

## 7. How Are These Four Outcomes Different?

The easiest way to distinguish them is to check two things:

1. Was the model's prediction correct?
2. Did the model predict Positive or Negative?

| Outcome | Model Prediction | Actual Result | Correct or Incorrect? |
|---|---|---|---|
| True Positive | Positive | Positive | Correct |
| True Negative | Negative | Negative | Correct |
| False Positive | Positive | Negative | Incorrect |
| False Negative | Negative | Positive | Incorrect |

The important point is that **True and False describe whether the prediction is correct, while Positive and Negative describe the class the model predicted.**

This distinction makes the four terms much easier to understand.

---

## 8. The Easiest Way to Remember

Instead of memorizing all four definitions separately, remember this rule:

**First, look at the prediction. Then, check whether it is correct.**

### If the model predicts Positive

- Actual Positive → True Positive
- Actual Negative → False Positive

### If the model predicts Negative

- Actual Negative → True Negative
- Actual Positive → False Negative

You can also remember it using this simple table:

|  | Actual Positive | Actual Negative |
|---|---|---|
| Predicted Positive | TP | FP |
| Predicted Negative | FN | TN |

Remember:

- **TP:** Correctly predicted Positive.
- **TN:** Correctly predicted Negative.
- **FP:** Incorrectly predicted Positive.
- **FN:** Incorrectly predicted Negative.

---

## 9. Which Mistake Is More Dangerous?

The importance of False Positives and False Negatives depends on the problem.

In a COVID-19 screening system:

- A False Positive may cause an uninfected person to undergo unnecessary testing or isolation.
- A False Negative may cause an infected person to go undetected, potentially increasing the risk of spreading the disease.

In this situation, missing an infected patient can be particularly dangerous.

However, in other applications, False Positives can be more costly. For example, incorrectly flagging a legitimate transaction as fraudulent may prevent a customer from making an important payment.

Therefore, when evaluating a Machine Learning model, we must consider the consequences of each type of error rather than treating all mistakes as equally important.

---

## 10. How to Explain This in a Machine Learning Interview

An interviewer may ask:

**"Can you explain True Positive, True Negative, False Positive, and False Negative with an example?"**

A clear interview answer would be:

"Let's consider a Machine Learning model that predicts whether a person has COVID-19.

A True Positive occurs when the person actually has COVID-19 and the model correctly predicts Positive.

A True Negative occurs when the person does not have COVID-19 and the model correctly predicts Negative.

A False Positive occurs when the person does not have COVID-19, but the model incorrectly predicts Positive.

A False Negative occurs when the person actually has COVID-19, but the model incorrectly predicts Negative.

In simple terms, True means the prediction is correct, False means the prediction is incorrect, and Positive or Negative tells us which class the model predicted."

### Interview Tip

Do not just memorize the full forms of TP, TN, FP, and FN.

Explain each term using the **actual condition and the model's prediction**. This demonstrates that you understand the concept rather than simply remembering definitions.

---

## Summary

True Positive, True Negative, False Positive, and False Negative are the four possible outcomes used to evaluate a binary classification model.

- **True Positive (TP):** Predicted Positive, and actually Positive.
- **True Negative (TN):** Predicted Negative, and actually Negative.
- **False Positive (FP):** Predicted Positive, but actually Negative.
- **False Negative (FN):** Predicted Negative, but actually Positive.

These four values form the foundation of the confusion matrix and are used to calculate several classification evaluation metrics.

**The key takeaway:**

> True or False tells you whether the prediction is correct. Positive or Negative tells you which class the model predicted.

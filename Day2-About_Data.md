# Data, Dataset, Labels, and Features

## 1. What is Data?

Data is a collection of raw facts, values, or information.

### Examples:

* Name: Mahesh BOB
* Age: 45
* Salary: 5500000
* City: Hyderabad

Each piece of information is called **data**.

---

## 2. What is a Dataset?

A dataset is a collection of related data organized in rows and columns.

### Example Dataset

| Name | Age | Experience | Salary |
| ---- | --- | ---------- | ------ |
| Ram  | 22  | 1 Year     | 400000 |
| Ravi | 25  | 3 Years    | 600000 |
| Sita | 28  | 5 Years    | 900000 |

Here, the entire table is called a **dataset**.

---

## 3. What are Features?

Features are the input variables used to make predictions.

In the above dataset:

* Age
* Experience

are features because they help predict another value.

### Example

If we want to predict **Salary**, then:

**Features (Inputs):**

* Age
* Experience

**Output:**

* Salary

---

## 4. What is a Label?

A label is the value that we want the machine learning model to predict.

### Example

| Age | Experience | Salary |
| --- | ---------- | ------ |
| 22  | 1 Year     | 400000 |
| 25  | 3 Years    | 600000 |
| 28  | 5 Years    | 900000 |

If our goal is to predict **Salary**:

* Features → Age, Experience
* Label → Salary

The label is also called:

* Target
* Output Variable
* Dependent Variable

---

## Real-Life Example

### House Price Prediction

| Area (sq.ft) | Bedrooms | House Price |
| ------------ | -------- | ----------- |
| 1000         | 2        | 50 Lakhs    |
| 1500         | 3        | 75 Lakhs    |
| 2000         | 4        | 1 Crore     |

### Features

* Area
* Bedrooms

### Label

* House Price

The model learns the relationship between the features and the label to predict the price of a new house.

---

## Quick Summary

| Term     | Meaning                               |
| -------- | ------------------------------------- |
| Data     | Individual pieces of information      |
| Dataset  | Collection of data organized together |
| Features | Input variables used for prediction   |
| Label    | Output value that the model predicts  |

**Simple Formula:**

`Features (Inputs) → Machine Learning Model → Label (Prediction)`

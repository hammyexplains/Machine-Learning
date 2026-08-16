# Data Cleaning and Preprocessing in Machine Learning

Machine Learning models learn from data. If the data is incomplete, inconsistent, or contains errors, the model's predictions can be inaccurate.

This is why **Data Cleaning** and **Data Preprocessing** are important steps before training any Machine Learning model.

---

# What is Data Cleaning?

Data Cleaning is the process of identifying and fixing issues in a dataset to improve its quality.

The goal is to ensure that the data is:

- Accurate
- Consistent
- Complete
- Ready for analysis and modeling

### Example

| Name | Age | Salary |
|--------|-----|---------|
| Ram | 25 | 30000 |
| Ravi | NULL | 45000 |
| Ram | 25 | 30000 |
| Sita | 200 | 50000 |

Issues in this dataset:

- Missing value (Age = NULL)
- Duplicate record
- Invalid value (Age = 200)

These issues should be handled before training a model.

---

# What is Data Preprocessing?

Data Preprocessing is the process of transforming raw data into a format that Machine Learning algorithms can understand and learn from effectively.

Even after cleaning the data, additional processing may be required.

Examples:

- Converting categorical data into numbers
- Scaling numerical values
- Selecting useful features

---

# Topics Covered in Data Cleaning

## 1. Handling Missing Values

Sometimes data may contain empty or NULL values.

Example:

| Age |
|------|
| 25 |
| NULL |
| 30 |

Common techniques:

- Remove rows
- Remove columns
- Fill with mean
- Fill with median
- Fill with mode

---

## 2. Handling Duplicate Records

Duplicate records can bias the model.

Example:

| Name | Age |
|--------|-----|
| Ram | 25 |
| Ram | 25 |

Duplicates are usually removed.

---

## 3. Handling Incorrect Data

Some values may be unrealistic.

Example:

| Age |
|------|
| 23 |
| 28 |
| 200 |

Age = 200 is likely incorrect and should be investigated.

---

## 4. Handling Outliers

Outliers are values that are significantly different from the rest of the data.

Example:

```text
20, 22, 25, 24, 23, 500
```

Here, 500 is an outlier.

Common methods:

- IQR Method
- Z-Score Method
- Capping

---

## 5. Fixing Inconsistent Data

Example:

```text
Hyderabad
hyderabad
HYDERABAD
```

All represent the same city but appear differently.

They should be standardized.

---

# Topics Covered in Data Preprocessing

## 1. Encoding Categorical Data

Machine Learning algorithms work with numbers.

Categorical values must be converted into numerical values.

Example:

| Gender |
|----------|
| Male |
| Female |

After Encoding:

| Gender |
|----------|
| 1 |
| 0 |

Common techniques:

- Label Encoding
- One-Hot Encoding

---

## 2. Feature Scaling

Features may have different ranges.

Example:

| Age | Salary |
|------|---------|
| 25 | 50000 |
| 30 | 100000 |

Salary values are much larger than Age values.

Scaling helps bring them to a similar range.

Common techniques:

- Standardization
- Normalization

---

## 3. Feature Selection

Not every column is useful for prediction.

Example:

| Name | Age | Salary |
|--------|-----|---------|

The "Name" column may not help predict salary.

Removing irrelevant features can improve model performance.

---

## 4. Feature Engineering

Creating new useful features from existing data.

Example:

From:

```text
Date of Birth
```

Create:

```text
Age
```

This often improves model performance.

---

## 5. Train-Test Split

The dataset is divided into:

- Training Data
- Testing Data

Purpose:

- Train the model on one portion
- Evaluate performance on unseen data

A common split is:

```text
80% Training Data
20% Testing Data
```

---

# Typical Data Preparation Workflow

```text
Raw Data
    ↓
Data Cleaning
    ↓
Handle Missing Values
    ↓
Remove Duplicates
    ↓
Handle Outliers
    ↓
Encode Categorical Data
    ↓
Scale Numerical Features
    ↓
Feature Selection / Engineering
    ↓
Train-Test Split
    ↓
Machine Learning Model
```

---

# Summary

Before training a Machine Learning model, data usually goes through two major stages:

### Data Cleaning

- Handling missing values
- Removing duplicates
- Fixing incorrect data
- Handling outliers
- Standardizing inconsistent values

### Data Preprocessing

- Encoding categorical data
- Feature scaling
- Feature selection
- Feature engineering
- Train-test splitting

> Good data leads to good models. In most real-world projects, data cleaning and preprocessing consume more time than model building itself.
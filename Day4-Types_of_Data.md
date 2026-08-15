# Types of Data Used in Machine Learning

Before building any Machine Learning model, it is important to understand the types of data that we work with.

Most data used in Machine Learning can be broadly classified into two categories:

1. Numerical Data
2. Categorical Data

---

# 1. Numerical Data

Numerical data consists of values that represent quantities or measurements. These values can be used directly in mathematical operations such as addition, subtraction, averaging, etc.

## Examples

| Age | Salary | Temperature |
|------|---------|------------|
| 21 | 30000 | 28.5 |
| 35 | 50000 | 32.1 |
| 42 | 75000 | 25.8 |

### Real-World Examples

- Age of a person
- Height of a student
- Salary of an employee
- Number of products sold
- Temperature of a city

Since these values are numbers with actual meaning, Machine Learning algorithms can easily process them.

---

# 2. Categorical Data

Categorical data represents labels, groups, or categories instead of quantities.

These values describe **what something is** rather than **how much it is**.

## Examples

### Gender

| Gender |
|----------|
| Male |
| Female |
| Male |

### Color

| Color |
|---------|
| Red |
| Blue |
| Green |

### Department

| Department |
|-------------|
| HR |
| Finance |
| IT |

### Real-World Examples

- Gender
- Blood Group
- City
- Country
- Product Category
- Department Name

Unlike numerical data, categorical values cannot be directly used in mathematical calculations.

Example:

```text
Male + Female = ?
```

This operation has no meaningful result.

---

# Quick Comparison

| Numerical Data | Categorical Data |
|---------------|------------------|
| Represents quantities | Represents labels or groups |
| Can be used in mathematical operations | Cannot be used in mathematical operations directly |
| Examples: Age, Salary, Height | Examples: Gender, Color, Country |
| Easy for ML algorithms to process | Requires additional processing |

---

# Summary

Machine Learning models commonly work with two types of data:

- **Numerical Data** → Numbers that represent quantities or measurements.
- **Categorical Data** → Labels or categories that represent groups.

Numerical data can be directly understood by most Machine Learning algorithms.

However, categorical data contains text labels rather than numbers.

## What's Next?

**How does Machine Learning understand categorical data?**

We'll answer that in the next markdown by exploring **Encoding Techniques**, which convert categorical values into a numerical format that Machine Learning models can understand.

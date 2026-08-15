# Types of Machine Learning

Machine Learning can be broadly divided into three main types:

## 1. Supervised Learning

In Supervised Learning, the model is trained using both **inputs (features)** and **outputs (labels)**.

The goal is to learn the relationship between inputs and outputs so that the model can predict outputs for new data.

### Example

| Age | Salary | Bought Product? |
|------|--------|----------------|
| 25 | 30,000 | Yes |
| 35 | 60,000 | No |
| 28 | 40,000 | Yes |

- Inputs: Age, Salary
- Output: Bought Product?

**Simple Rule:**

> Input + Output = Supervised Learning

**Real-world Examples:**
- Email Spam Detection
- House Price Prediction
- Customer Churn Prediction

---

## 2. Unsupervised Learning

In Unsupervised Learning, the model is trained using only **inputs (features)**. No output labels are provided.

The model tries to discover hidden patterns, relationships, or groups in the data.

### Example

| Age | Salary |
|------|--------|
| 25 | 30,000 |
| 35 | 60,000 |
| 26 | 32,000 |
| 55 | 90,000 |

The model may group customers with similar characteristics into different segments.

**Simple Rule:**

> Only Inputs = Unsupervised Learning

**Real-world Examples:**
- Customer Segmentation
- Market Basket Analysis
- Anomaly Detection

---

## 3. Reinforcement Learning

In Reinforcement Learning, an agent learns by interacting with an environment.

The agent performs actions and receives:
- Rewards for good actions
- Penalties for bad actions

The goal is to maximize the total reward over time.

### Example

Think of teaching a dog a trick:

- Correct action → Treat (Reward)
- Wrong action → No Treat (Penalty)

Over time, the dog learns the best behavior.

**Simple Rule:**

> Actions + Rewards/Penalties = Reinforcement Learning

**Real-world Examples:**
- Self-Driving Cars
- Game Playing AI (Chess, Go)
- Robot Navigation

---

## Quick Comparison

| Type | Input Data | Output Labels | Learning Method |
|--------|-----------|---------------|----------------|
| Supervised Learning | Yes | Yes | Learn from labeled examples |
| Unsupervised Learning | Yes | No | Find hidden patterns |
| Reinforcement Learning | Environment State | Rewards/Penalties | Learn through trial and error |

## Easy Way to Remember

- **Supervised Learning** → Learning with a teacher.
- **Unsupervised Learning** → Learning without a teacher.
- **Reinforcement Learning** → Learning through rewards and mistakes.

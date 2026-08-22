# Unsupervised Learning and K-Means Clustering

Machine Learning algorithms are broadly categorized into:

- Supervised Learning
- Unsupervised Learning

In Supervised Learning, the model learns from labeled data.

In Unsupervised Learning, the model works with data that has no labels and tries to discover hidden patterns on its own.

---

# What is Unsupervised Learning?

Unsupervised Learning is a type of Machine Learning where the model is given data without any target variable or correct answers.

The goal is to find patterns, relationships, or groups within the data.

### Example

Suppose we have customer data:

| Customer ID | Monthly Spend | Visits Per Month |
|------------|--------------|------------------|
| C1 | 5000 | 15 |
| C2 | 4500 | 12 |
| C3 | 500 | 2 |
| C4 | 700 | 1 |

Notice that there is no column such as:

```text
Customer Type
```

The model must analyze the data and discover groups on its own.

---

# Real-Life Analogy

Imagine entering a classroom full of students you've never met.

Without knowing anything about them, you might naturally group them based on observations such as:

- Students sitting together
- Similar interests
- Similar age groups

Nobody tells you the groups beforehand.

You identify the groups by observing patterns.

This is similar to how Unsupervised Learning works.

---

# Common Tasks in Unsupervised Learning

## 1. Clustering

Grouping similar data points together.

Example:

- Customer Segmentation
- Product Categorization
- Social Network Analysis

---

## 2. Association

Finding relationships between items.

Example:

```text
Customers who buy Bread
often buy Butter
```

---

## 3. Dimensionality Reduction

Reducing the number of features while preserving important information.

Example:

- Data Compression
- Data Visualization

---

# What is Clustering?

Clustering is the process of grouping similar data points together.

Data points within the same group should be similar, while data points in different groups should be different.

Example:

A supermarket may want to group customers into:

- Frequent Buyers
- Occasional Buyers
- Rare Buyers

These groups are called **Clusters**.

---

# What is K-Means Clustering?

K-Means is one of the most popular clustering algorithms.

It groups similar data points into **K clusters**.

The value of **K** represents the number of clusters we want to create.

Example:

```text
K = 3
```

Means:

```text
Create 3 clusters
```

---

# Real-Life Example

Suppose we have customer data:

| Customer | Visits Per Month |
|----------|-----------------|
| A | 15 |
| B | 14 |
| C | 12 |
| D | 3 |
| E | 2 |
| F | 1 |

We may want to divide customers into:

```text
Cluster 1 → Frequent Buyers
Cluster 2 → Occasional Buyers
Cluster 3 → Rare Buyers
```

K-Means automatically discovers these groups.

---

# How K-Means Works

## Step 1: Choose K

Decide how many clusters you want.

Example:

```text
K = 3
```

---

## Step 2: Initialize Centroids

A centroid represents the center of a cluster.

The algorithm randomly selects K centroids.

Example:

```text
Centroid 1
Centroid 2
Centroid 3
```

---

## Step 3: Assign Data Points

Each data point is assigned to the nearest centroid.

Example:

```text
Customer A → Cluster 1
Customer B → Cluster 1
Customer D → Cluster 2
```

---

## Step 4: Recalculate Centroids

After assigning points, the algorithm calculates new cluster centers.

The centroid moves to the average position of all points in that cluster.

---

## Step 5: Repeat

The algorithm repeatedly:

1. Assigns points to the nearest centroid
2. Updates centroids

until the centroids stop changing significantly.

This means the clusters have stabilized.

---

# Visual Representation

Suppose we have customer data plotted on a graph.

```text
      ● ● ●

          C1


● ●

     C2


                    ● ● ●

                        C3
```

After several iterations, similar points are grouped together into clusters.

---

# Choosing the Value of K

One common question is:

```text
How many clusters should we create?
```

The value of K is usually chosen based on:

- Business requirements
- Domain knowledge
- Evaluation techniques such as the Elbow Method

Example:

```text
K = 2
```

May create:

- High-Value Customers
- Low-Value Customers

While:

```text
K = 4
```

May create more detailed customer segments.

---

# Applications of K-Means Clustering

## Customer Segmentation

Grouping customers based on purchasing behavior.

---

## Recommendation Systems

Finding users with similar interests.

---

## Image Segmentation

Grouping similar pixels together.

---

## Market Analysis

Identifying customer groups for targeted marketing.

---

## Anomaly Detection

Detecting unusual patterns in data.

---

# Advantages of K-Means

- Simple to understand
- Easy to implement
- Fast on large datasets
- Works well for well-separated clusters
- Widely used in industry

---

# Limitations of K-Means

- Must choose K beforehand
- Sensitive to outliers
- Results depend on initial centroid placement
- Works best when clusters are roughly spherical
- May struggle with complex cluster shapes

---

# Unsupervised Learning vs Supervised Learning

| Supervised Learning | Unsupervised Learning |
|--------------------|----------------------|
| Uses labeled data | Uses unlabeled data |
| Has a target variable | No target variable |
| Learns input-output relationships | Discovers hidden patterns |
| Example: Predicting House Price | Example: Customer Segmentation |

---

# Summary

Unsupervised Learning is a type of Machine Learning where the model learns from unlabeled data and discovers hidden patterns without being given correct answers.

One of the most common Unsupervised Learning techniques is **K-Means Clustering**, which groups similar data points into K clusters.

K-Means works by:

1. Choosing the number of clusters (K)
2. Creating centroids
3. Assigning points to the nearest centroid
4. Updating centroids
5. Repeating the process until stable clusters are formed

> K-Means does not predict outcomes.
>
> Instead, it helps us discover natural groups that already exist within the data.

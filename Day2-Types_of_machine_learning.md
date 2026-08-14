#Supervised vs Unsupervised Learning

##Supervised Learning

In Supervised Learning, we provide the model with:

- Inputs (Features)
- Outputs (Labels/Targets)

The model learns the relationship between the inputs and outputs and uses that knowledge to make predictions on new data.

Example

Age| Salary| Bought Product?
25| 30,000| Yes
35| 60,000| No
28| 40,000| Yes

Here:

- Inputs: Age, Salary
- Output (Label): Bought Product?

Simple Rule:

«Input + Output = Supervised Learning»

---

##Unsupervised Learning

In Unsupervised Learning, we provide the model with:

- Inputs (Features) only
- No Outputs (Labels)

The model tries to find hidden patterns, similarities, or groups within the data.

Example

Age| Salary
25| 30,000
35| 60,000
26| 32,000
55| 90,000

The model may automatically group similar customers together based on their age and salary.

Simple Rule:

«Only Inputs = Unsupervised Learning»

---

Quick Comparison

Feature| Supervised Learning| Unsupervised Learning
Inputs Available| ✅ Yes| ✅ Yes
Outputs Available| ✅ Yes| ❌ No
Goal| Predict Outputs| Find Patterns
Example| Spam Detection| Customer Segmentation

Easy Way to Remember

- Supervised Learning → Learning with a teacher (answers are provided).
- Unsupervised Learning → Learning without a teacher (find patterns yourself)..
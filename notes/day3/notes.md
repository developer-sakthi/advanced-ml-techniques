# Decision Trees

first read this article
[Decision Trees](https://www.geeksforgeeks.org/machine-learning/decision-tree-introduction-example/)

## 1️⃣ Classification vs Regression Trees

Both are decision trees.

The difference is what they predict.

🌳 Classification Tree

👉 Used when the output is a category (label).

Examples:

Spam / Not Spam

Male / Female

Pass / Fail

Disease / No Disease

So the final leaf gives a class label.

Example:

Age > 30?
Yes → Has Disease
No → No Disease

Behind the scenes:

The tree tries to make each leaf contain mostly one class.

It uses metrics like:

Gini Index

Entropy

Information Gain

Goal:
👉 Make each final group as “pure” as possible.

If a leaf has 95% spam emails, it predicts “Spam”.

🌳 Regression Tree

👉 Used when the output is a number (continuous value).

Examples:

House price = ₹45,00,000

Salary = ₹6,50,000

Temperature = 32.5°C

So the final leaf gives a number.

Example:

House Size > 1500 sq ft?
Yes → 75 Lakhs
No → 45 Lakhs

Behind the scenes:

It splits data to reduce variance

It uses:

Mean Squared Error (MSE)

Variance reduction

Goal:
👉 Make numbers inside each leaf very close to each other.

Instead of predicting a class, it predicts the average value of that group.

Quick Comparison
Feature Classification Tree Regression Tree
Output Category Number
Example Spam / Not Spam House Price
Goal Make groups pure Reduce variance
Metric Gini, Entropy MSE, Variance

## 2️⃣ Feature-Based Splitting

This is how the tree decides what question to ask next.

A decision tree does NOT randomly ask questions.

It examines all features like:

Age

Height

Weight

Income

Email length

Word frequency

Then it asks:

👉 “Which feature, if I split on it, gives the cleanest separation?”

Example dataset:

Age Income Buy
22 20k No
25 25k No
40 80k Yes
45 90k Yes

The tree checks:

Split on Age?
Split on Income?

It calculates which split reduces uncertainty the most.

If splitting on Income gives perfect separation:

Income > 50k?

Yes → Buy

No → Don’t Buy

Then Income becomes the root.

So “feature-based splitting” means:

👉 The tree chooses features one by one
👉 Each split is based on one feature
👉 It selects the feature that improves prediction the most

Big Picture

Decision Tree =

Choose best feature

Split data

Repeat on each branch

Stop when pure or small

That’s it.

Now let me push you slightly:

If a regression tree predicts ₹5,00,000 at a leaf, what number is it actually using from training data?

Think carefully before answe

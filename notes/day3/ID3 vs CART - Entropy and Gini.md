# 🌪 What Is Impurity?

Impurity means:

👉 “How mixed is this group?”

If a node contains:

- 100 Spam → Pure
- 50 Spam + 50 Not Spam → Very impure

So the tree’s goal is:

> Keep splitting until groups become as pure as possible.

To measure impurity, we use:

- **Entropy**
- **Gini Index**

---

# 🔵 Entropy (Used in ID3)

Entropy measures randomness.

Formula:

[
Entropy = - \sum p_i \log_2(p_i)
]

Don’t panic. Let’s simplify.

If a node has:

- 100% Spam → Entropy = 0 (Perfectly pure)
- 50% Spam, 50% Not Spam → Entropy = 1 (Maximum impurity)

So:

| Distribution   | Entropy |
| -------------- | ------- |
| 100% one class | 0       |
| 50–50 split    | 1 (max) |
| 80–20 split    | ~0.72   |

Higher entropy = more mixed
Lower entropy = more pure

The tree chooses the split with **highest Information Gain**.

Information Gain =
Old Entropy − New Entropy

So ID3 asks:

👉 “Which feature reduces entropy the most?”

---

# 🟢 Gini Index (Used in CART)

Formula:

[
Gini = 1 - \sum p_i^2
]

Again, simplify.

If a node has:

- 100% Spam → Gini = 0 (Pure)
- 50% Spam + 50% Not Spam → Gini = 0.5 (Maximum impurity)

So:

| Distribution   | Gini |
| -------------- | ---- |
| 100% one class | 0    |
| 50–50 split    | 0.5  |
| 80–20 split    | 0.32 |

Lower Gini = more pure

CART chooses split with **lowest Gini**.

---

# 🔥 ID3 vs CART

Now let’s compare properly.

## 🌳 ID3 (Iterative Dichotomiser 3)

- Uses **Entropy**
- Uses **Information Gain**
- Used only for classification
- Can create **multi-branch splits**
- Doesn’t handle continuous features well (original version)

Invented by: Ross Quinlan

---

## 🌳 CART (Classification And Regression Tree)

- Uses **Gini Index** (for classification)
- Uses **MSE** (for regression)
- Can handle both classification & regression
- Always makes **binary splits** (only 2 branches)
- Handles continuous features naturally

Developed by: Leo Breiman and team

---

# 🆚 Entropy vs Gini (Which Is Better?)

Truth?

They usually give very similar results.

But here’s the difference:

| Feature     | Entropy                         | Gini                      |
| ----------- | ------------------------------- | ------------------------- |
| Complexity  | Slightly slower (log involved)  | Faster (simple math)      |
| Range       | 0 to 1                          | 0 to 0.5 (binary case)    |
| Sensitivity | More sensitive to small changes | Slightly less sensitive   |
| Used in     | ID3                             | CART (and most libraries) |

Most modern libraries (like scikit-learn) use Gini by default because it’s faster.

---

# 🎯 Intuition Difference

Entropy:

> “How much information do we gain?”

Gini:

> “What is the probability of misclassifying a random point?”

Different thinking. Same goal:
👉 Make nodes pure.

---

# Important Insight

Both measures try to answer:

> If I randomly pick a sample from this node, how likely am I to be wrong?

If the node is pure → 0 error → impurity = 0.

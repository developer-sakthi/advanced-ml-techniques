# AdaBoost (Adaptive Boosting)

- One of the earliest boosting algorithms is AdaBoost.

- AdaBoost stands for Adaptive Boosting.

- It is called adaptive because the algorithm adjusts the importance of training data based on how well the model performs.

### The key idea:

- Samples that are correctly classified become less important

- Samples that are misclassified become more important

- This forces the next model to focus more on the difficult cases.

### Steps

1. Start with all training data having equal importance.

2. Train a weak learner on the data.

3. Identify which samples were predicted incorrectly.

4. Increase the importance of those misclassified samples.

5. Train another weak learner focusing more on those difficult samples.

6. Repeat the process several times.

7. Combine all the weak learners to make the final prediction.

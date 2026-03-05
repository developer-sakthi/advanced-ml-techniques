# PCA

- Principal Component Analysis (PCA) is a technique used in dimensionality reduction to transform a dataset with many correlated variables into a smaller set of uncorrelated variables called principal components, while preserving as much variance (information) as possible.

## Steps in PCA ( refer notes for formula )

1. Standardize the data (mean=0, std=1)
2. Calculate the covariance matrix
3. Calculate the eigenvalues and eigenvectors of the covariance matrix
4. Sort the eigenvectors by its eigenvalues in descending order
5. Select the top k eigenvectors
6. Transform the data

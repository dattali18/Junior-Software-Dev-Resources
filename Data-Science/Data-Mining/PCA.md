# PCA

Principal Component Analysis (PCA) is a dimensionality reduction technique commonly used in data mining and machine learning. It aims to reduce the number of variables in a dataset while preserving the most important information. PCA works by finding the principal components, which are new variables that are linear combinations of the original variables. These components are ordered by the amount of variance they explain in the data, with the first component explaining the most variance.

### Explanation

Let's say we have a dataset with two variables, `X` and `Y`. PCA would find the principal components of this dataset, which are new variables `PC1` and `PC2` that are linear combinations of `X` and `Y`. These new variables are orthogonal to each other, and `PC1` explains the most variance in the data, followed by `PC2`.

### Code Example (Python)

```python
import numpy as np
from sklearn.decomposition import PCA

# Example data
X = np.array([[1, 2], [3, 4], [5, 6], [7, 8]])

# Create PCA object
pca = PCA(n_components=2)

# Fit the data
pca.fit(X)

# Get the principal components
print("Principal Components:")
print(pca.components_)

# Transform the data
X_transformed = pca.transform(X)
print("\nTransformed Data:")
print(X_transformed)
```

### Real-World Examples

1. **Image Compression:** PCA can be used to reduce the dimensionality of images while preserving the most important information. This is useful for image compression techniques.

2. **Finance:** In finance, PCA is used for tasks like stock market forecasting, where it can reduce the dimensionality of stock data to identify patterns and trends.

3. **Biology:** PCA is used in genetics to analyze gene expression data, where it can help identify patterns in gene expression levels across different samples.

4. **Text Mining:** In text mining, PCA can be used to reduce the dimensionality of text data, making it easier to analyze and extract meaningful information.

PCA is a powerful technique with many applications in data mining and machine learning. It helps to reduce the complexity of high-dimensional datasets while preserving important information, making it easier to analyze and interpret the data.
## Math 

The main idea behind PCA is to find a new set of orthogonal axes (principal components) onto which we can project our data in such a way that the variance of the projected data is maximized. This is done by finding the eigenvectors of the covariance matrix of the data.

Given a dataset $X$ with $n$ observations and $p$ variables, the steps for PCA are as follows:

1. **Standardize the Data:** Subtract the mean and divide by the standard deviation for each variable to ensure that all variables have zero mean and unit variance.

2. **Compute the Covariance Matrix:** Compute the covariance matrix $\Sigma$ of the standardized data.

3. **Compute Eigenvectors and Eigenvalues:** Find the eigenvectors $\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_p$ and corresponding eigenvalues $\lambda_1, \lambda_2, \ldots, \lambda_p$ of $\Sigma$. The eigenvectors are the principal components, and the eigenvalues represent the amount of variance explained by each principal component.

4. **Select Principal Components:** Sort the eigenvectors in descending order of their corresponding eigenvalues and select the first $k$ eigenvectors to form a matrix $\mathbf{V}_k$.

5. **Project the Data:** Project the standardized data onto the new space spanned by the selected eigenvectors to obtain the transformed data $\mathbf{Y} = \mathbf{X} \mathbf{V}_k$.

The mathematical representation of the covariance matrix is:

$$
\Sigma = \frac{1}{n-1} \sum_{i=1}^{n} (\mathbf{x}_i - \bar{\mathbf{x}})(\mathbf{x}_i - \bar{\mathbf{x}})^T
$$

where $\mathbf{x}_i$ is the $i$-th observation, $\bar{\mathbf{x}}$ is the mean vector, and $n$ is the number of observations.

The eigenvectors $\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_p$ and eigenvalues $\lambda_1, \lambda_2, \ldots, \lambda_p$ satisfy the equation:

$$
\Sigma \mathbf{v}_i = \lambda_i \mathbf{v}_i
$$

The projected data $\mathbf{Y}$ is obtained by multiplying the standardized data $\mathbf{X}$ by the matrix of selected eigenvectors $\mathbf{V}_k$:

$$
\mathbf{Y} = \mathbf{X} \mathbf{V}_k
$$

This transformation reduces the dimensionality of the data while preserving the most important information, as the principal components are ordered by the amount of variance they explain.
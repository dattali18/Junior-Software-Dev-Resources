# t-SNE

t-distributed Stochastic Neighbor Embedding (t-SNE) is a technique used for dimensionality reduction and visualization of high-dimensional data. It aims to map high-dimensional data points into a lower-dimensional space (usually 2D or 3D) while preserving the local structure of the data. t-SNE is particularly useful for visualizing complex datasets in a way that can reveal clusters or groups of data points.

### Mathematical Explanation

Given a high-dimensional dataset $X$ with $n$ data points and $d$ dimensions, t-SNE works by first constructing a probability distribution over pairs of high-dimensional data points. This is done using a Gaussian kernel to measure similarity:

$$
p_{ij} = \frac{\exp(-\lVert \mathbf{x}_i - \mathbf{x}_j \rVert^2 / 2\sigma_i^2)}{\sum_{k \neq i} \exp(-\lVert \mathbf{x}_i - \mathbf{x}_k \rVert^2 / 2\sigma_i^2)}
$$

where $p_{ij}$ is the conditional probability that point $i$ would pick point $j$ as its neighbor, and $\sigma_i$ is the variance of the Gaussian centered at point $i$.

t-SNE then constructs a similar probability distribution in the lower-dimensional space (usually 2D) using a Student's t-distribution with one degree of freedom:

$$
q_{ij} = \frac{(1 + \lVert \mathbf{y}_i - \mathbf{y}_j \rVert^2)^{-1}}{\sum_{k \neq i} (1 + \lVert \mathbf{y}_i - \mathbf{y}_k \rVert^2)^{-1}}
$$

where $q_{ij}$ is the conditional probability that point $i$ would pick point $j$ as its neighbor in the lower-dimensional space, and $\mathbf{y}_i$ and $\mathbf{y}_j$ are the corresponding points in the lower-dimensional space.

The objective of t-SNE is to minimize the Kullback-Leibler divergence between the two distributions $P$ and $Q$:

$$
KL(P||Q) = \sum_i \sum_j p_{ij} \log \frac{p_{ij}}{q_{ij}}
$$

### Practical Example

Let's say we have a dataset with 1000 high-dimensional data points and we want to visualize them in 2D using t-SNE.

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.manifold import TSNE

# Generate example data
np.random.seed(0)
X = np.random.rand(1000, 50)  # 1000 data points in 50 dimensions

# Perform t-SNE
tsne = TSNE(n_components=2, random_state=0)
X_embedded = tsne.fit_transform(X)

# Plot the embedded data
plt.figure(figsize=(8, 6))
plt.scatter(X_embedded[:, 0], X_embedded[:, 1], marker='.')
plt.title('t-SNE Visualization')
plt.xlabel('Dimension 1')
plt.ylabel('Dimension 2')
plt.show()
```

In this example, we generate a synthetic dataset with 1000 data points in 50 dimensions. We then use t-SNE to reduce the dimensionality to 2D and visualize the data points in a scatter plot. The resulting plot shows the data points in a lower-dimensional space, where clusters or patterns in the data may be more easily discernible.
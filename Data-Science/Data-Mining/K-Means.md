# K-Means
### K-Means Clustering

#### Concept
K-Means is a popular clustering algorithm that aims to partition $n$ observations into $k$ clusters, where each observation belongs to the cluster with the nearest mean (centroid). The algorithm iteratively assigns observations to the nearest centroid and then recalculates the centroids based on the new assignments. This process continues until the centroids no longer change significantly, or a specified number of iterations is reached.

#### Algorithm Steps
1. **Initialize Centroids:** Randomly select $k$ observations as the initial centroids.
2. **Assign Observations to Clusters:** For each observation, assign it to the cluster with the nearest centroid.
3. **Update Centroids:** Recalculate the centroids for each cluster based on the mean of the observations assigned to that cluster.
4. **Repeat Steps 2 and 3:** Repeat the assignment and update steps until convergence (centroids do not change significantly) or a maximum number of iterations is reached.

#### Python Implementation

```python
import numpy as np

class KMeans:
    def __init__(self, n_clusters, max_iter=300):
        self.n_clusters = n_clusters
        self.max_iter = max_iter

    def fit(self, X):
        n_samples, n_features = X.shape
        
        # Initialize centroids
        self.centroids = X[np.random.choice(
	        n_samples, self.n_clusters, replace=False
	        )]
        
        # Main loop
        for _ in range(self.max_iter):
            # Assign samples to closest centroid
            labels = self._assign_clusters(X)
            
            # Update centroids
            new_centroids = np.array(
            [X[labels == i].mean(axis=0) for i in range(self.n_clusters)]
            )
            
            # Check for convergence
            if np.allclose(self.centroids, new_centroids):
                break
                
            self.centroids = new_centroids

        # Assign the final clusters
        self.labels_ = self._assign_clusters(X)
        return self

    def _assign_clusters(self, X):
        return np.argmin(
        ((X - self.centroids[:, np.newaxis])**2).sum(axis=2), axis=0)

# Example usage
X = np.array([[1, 2], [5, 8], [1.5, 1.8], [8, 8], [1, 0.6], [9, 11]])
kmeans = KMeans(n_clusters=2)
kmeans.fit(X)
print("Final centroids:", kmeans.centroids)
print("Cluster labels:", kmeans.labels_)
```

In this example, we define a `KMeans` class with methods for fitting the model (`fit`) and assigning clusters to data points (`_assign_clusters`). The `fit` method initializes centroids, assigns points to clusters, and updates centroids iteratively until convergence or the maximum number of iterations is reached.

## Example

Let's run a simple example of K-Means clustering with $k=2$ on a small dataset. We'll initialize centroids randomly and update them iteratively until convergence.

### Example Dataset
Consider the following dataset with two-dimensional points:

$$
\begin{array}{|c|c|}
\hline
X & Y \\
\hline
1 & 2 \\
5 & 8 \\
1.5 & 1.8 \\
8 & 8 \\
1 & 0.6 \\
9 & 11 \\
\hline
\end{array}
$$

### Step 1: Initialize Centroids
Let's randomly select two points as the initial centroids:

$$
\begin{array}{|c|c|}
\hline
\text{Centroid} & \text{Coordinates} \\
\hline
C_1 & (1, 2) \\
C_2 & (5, 8) \\
\hline
\end{array}
$$

### Step 2: Assign Points to Clusters
Calculate the Euclidean distance from each point to each centroid and assign each point to the closest centroid.

$$
\begin{array}{|c|c|c|c|}
\hline
\text{Point} & \text{Distance to } C_1 & \text{Distance to } C_2 & \text{Assigned Cluster} \\
\hline
(1, 2) & 0 & 7.21 & C_1 \\
(5, 8) & 7.81 & 0 & C_2 \\
(1.5, 1.8) & 0.36 & 6.61 & C_1 \\
(8, 8) & 8.25 & 0.82 & C_2 \\
(1, 0.6) & 1.4 & 7.86 & C_1 \\
(9, 11) & 11.18 & 3.61 & C_2 \\
\hline
\end{array}
$$

### Step 3: Update Centroids
Calculate the mean of points in each cluster and update the centroids:

$$
\begin{array}{|c|c|c|}
\hline
\text{Cluster} & \text{Points} & \text{New Centroid} \\
\hline
C_1 & (1, 2), (1.5, 1.8), (1, 0.6) & (1.17, 1.47) \\
C_2 & (5, 8), (8, 8), (9, 11) & (7.33, 9) \\
\hline
\end{array}
$$

### Repeat Steps 2 and 3
Repeat steps 2 and 3 until the centroids no longer change significantly or a maximum number of iterations is reached. In this case, the centroids converge after a few iterations.

### Final Result
The final centroids are:

$$
\begin{array}{|c|c|}
\hline
\text{Centroid} & \text{Coordinates} \\
\hline
C_1 & (1.17, 1.47) \\
C_2 & (7.33, 9) \\
\hline
\end{array}
$$

And the cluster labels for the points are:

$$
\begin{array}{|c|c|}
\hline
\text{Point} & \text{Cluster} \\
\hline
(1, 2) & C_1 \\
(5, 8) & C_2 \\
(1.5, 1.8) & C_1 \\
(8, 8) & C_2 \\
(1, 0.6) & C_1 \\
(9, 11) & C_2 \\
\hline
\end{array}
$$

This demonstrates a basic example of K-Means clustering on a small dataset.

## Time & Space Complexity 

The time and space complexity of the K-Means clustering algorithm can be analyzed as follows:

### Time Complexity
1. **Initialization:** Selecting the initial centroids has a time complexity of $O(k \cdot d \cdot n)$, where $k$ is the number of clusters, $d$ is the number of features, and $n$ is the number of data points. This is because for each of the $k$ centroids, we need to consider each of the $d$ dimensions for each of the $n$ data points.
   
2. **Assignment Step:** Assigning each data point to its nearest centroid has a time complexity of $O(k \cdot n \cdot d)$, where $k$ is the number of clusters, $d$ is the number of features, and $n$ is the number of data points. This is because for each of the $n$ data points, we need to calculate the distance to each of the $k$ centroids, each requiring $O(d)$ operations.

3. **Update Step:** Updating the centroids has a time complexity of $O(k \cdot n \cdot d)$, similar to the assignment step. For each of the $k$ centroids, we need to calculate the mean of the points assigned to that centroid, which requires $O(d)$ operations for each of the $n$ data points.

4. **Convergence:** The algorithm typically converges in a fixed number of iterations, which is determined by the convergence criteria. The number of iterations is often small compared to the size of the dataset, so it is often considered constant.

Overall, the dominant term in the time complexity is $O(k \cdot n \cdot d)$, which is the complexity of the assignment and update steps.

### Space Complexity
1. **Centroids:** The space complexity for storing the centroids is $O(k \cdot d)$, where $k$ is the number of clusters and $d$ is the number of features.
   
2. **Assignments:** The space complexity for storing the cluster assignments for each data point is $O(n)$, where $n$ is the number of data points.

3. **Distance Matrix:** If a distance matrix is used to store pairwise distances between data points and centroids, the space complexity would be $O(k \cdot n)$ or $O(n^2)$, depending on whether all pairwise distances are precomputed or computed on the fly.

4. **Other Data Structures:** Additional space may be required for temporary data structures used during the algorithm, such as arrays to store sums of points in each cluster.

Overall, the dominant term in the space complexity is usually $O(k \cdot d)$ or $O(n)$, depending on how distances are stored and how many centroids are used.
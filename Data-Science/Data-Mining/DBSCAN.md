# DBSCAN

### DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

DBSCAN is a density-based clustering algorithm that groups together closely packed points and identifies outliers as noise. It stands for Density-Based Spatial Clustering of Applications with Noise. DBSCAN is based on two parameters: $\varepsilon$ (epsilon) and `min_samples`.

#### Algorithm Steps:
1. **Core Points:** A point is considered a core point if at least `min_samples` points are within distance $\varepsilon$ of it (including the point itself).
2. **Border Points:** A point that is not a core point but is within distance $\varepsilon$ of a core point.
3. **Noise Points:** Points that are neither core nor border points.
4. **Cluster Formation:** DBSCAN forms clusters by connecting core points that are within distance $\varepsilon$ of each other. A single cluster contains all core points, as well as border points that are reachable from the core points.
5. **Noise Identification:** Points that are not within distance $\varepsilon$ of any core points are considered noise points and do not belong to any cluster.

#### Parameters:
- $\varepsilon$: The maximum distance between two samples for them to be considered as in the same neighborhood.
- `min_samples`: The number of samples in a neighborhood for a point to be considered as a core point.

#### Python Example:

```python
from sklearn.cluster import DBSCAN
import numpy as np

# Sample data
X = np.array([[1, 2], [2, 2], [2, 3],
              [8, 7], [8, 8], [25, 80]])

# Applying DBSCAN
dbscan = DBSCAN(eps=3, min_samples=2)
y_dbscan = dbscan.fit_predict(X)

# Output cluster labels (-1 for noise)
print("Cluster labels:", y_dbscan)
```

### Key Concepts:
- **Core Point:** A point with at least `min_samples` points within distance $\varepsilon$.
- **Border Point:** A point within distance $\varepsilon$ of a core point but does not have enough points within $\varepsilon$ to be a core point itself.
- **Noise Point:** A point that is neither a core point nor a border point.

### Advantages:
- Can find arbitrarily shaped clusters.
- Robust to outliers.

### Limitations:
- Requires setting $\varepsilon$ and `min_samples` parameters.
- Struggles with clusters of varying densities.

DBSCAN is widely used in various fields, such as spatial data analysis, anomaly detection, and image segmentation, due to its ability to handle noise and find clusters of arbitrary shapes.

## Example

To run the DBSCAN algorithm on the given example data, we'll follow these steps:

1. **Initialize the Algorithm:** Set `min_samples=3` and `epsilon=2`.
2. **Assign Point Labels:** Initially, all points are labeled as "unvisited".
3. **Process Core Points:** For each point, check if it's a core point or a border point. Core points are points with at least `min_samples` points within distance `epsilon`.
4. **Expand Clusters:** For each core point (and its reachable points), assign it to a cluster.
5. **Identify Noise:** Points that are not core points or reachable from core points are noise points.

Let's proceed step by step:

### Step 1: Initialize

| Point | X | Y | Label |
|-------|---|---|-------|
| P1    | 1 | 2 | Unvisited |
| P2    | 1 | 4.5 | Unvisited |
| P3    | 1 | 3 | Unvisited |
| P4    | 3 | 1.5 | Unvisited |
| P5    | 3 | 3.5 | Unvisited |
| P6    | 4 | 2.5 | Unvisited |
| P7    | 5 | 6 | Unvisited |

### Step 2: Process Core Points

- **P1:** Core point (3 points within epsilon=2)
- **P2:** Core point (3 points within epsilon=2)
- **P3:** Core point (3 points within epsilon=2)
- **P4:** Border point (2 points within epsilon=2)
- **P5:** Core point (3 points within epsilon=2)
- **P6:** Border point (2 points within epsilon=2)
- **P7:** Noise point (No points within epsilon=2)

### Step 3: Expand Clusters

- Cluster 1: {P1, P2, P3, P5} (Core points and reachable border points)
- Cluster 2: {P4} (Border point)
- Noise: {P7}

### Step 4: Final Result

| Point | X | Y | Label |
|-------|---|---|-------|
| P1    | 1 | 2 | Cluster 1 |
| P2    | 1 | 4.5 | Cluster 1 |
| P3    | 1 | 3 | Cluster 1 |
| P4    | 3 | 1.5 | Cluster 2 |
| P5    | 3 | 3.5 | Cluster 1 |
| P6    | 4 | 2.5 | Cluster 2 |
| P7    | 5 | 6 | Noise |

In conclusion:
- Points P1, P2, P3, and P5 belong to Cluster 1.
- Points P4 and P6 belong to Cluster 2.
- Point P7 is a noise point.
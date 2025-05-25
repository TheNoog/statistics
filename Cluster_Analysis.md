# Cluster Analysis

Cluster analysis is a collection of techniques used to group objects or individuals into clusters based on their similarity. The goal is to partition a set of data points such that data points within the same cluster are more similar to each other than to those in other clusters. There are various clustering algorithms, including:

*   **Hierarchical Clustering:** Builds a hierarchy of clusters, either by merging small clusters into larger ones (agglomerative) or by splitting large clusters into smaller ones (divisive).
*   **Partitioning Methods:** Divide data into a predefined number of clusters, such as K-Means clustering.

The choice of clustering algorithm and the definition of "similarity" (e.g., distance metrics like Euclidean distance) depend on the nature of the data and the research question.

## Worked Example: K-Means Clustering

Let's illustrate K-Means clustering with a simple example. Suppose we have data points representing the height and weight of five individuals:

| Individual | Height (cm) | Weight (kg) |
| :--------- | :---------- | :---------- |
| A          | 160         | 55          |
| B          | 175         | 70          |
| C          | 165         | 60          |
| D          | 180         | 75          |
| E          | 170         | 65          |

We want to group these individuals into two clusters using K-Means.

**Step 1: Choose the number of clusters (K) and initialize centroids.**

We choose K=2. Let's randomly initialize two centroids:

*   Centroid 1: (160, 55)
*   Centroid 2: (180, 75)

**Step 2: Assign each data point to the nearest centroid.**

We calculate the Euclidean distance from each data point to each centroid:

*   Distance(A, C1) = $\sqrt{(160-160)^2 + (55-55)^2} = 0$
*   Distance(A, C2) = $\sqrt{(160-180)^2 + (55-75)^2} = \sqrt{400 + 400} = \sqrt{800} \approx 28.28$. Individual A is assigned to Cluster 1.

*   Distance(B, C1) = $\sqrt{(175-160)^2 + (70-55)^2} = \sqrt{225 + 225} = \sqrt{450} \approx 21.21$
*   Distance(B, C2) = $\sqrt{(175-180)^2 + (70-75)^2} = \sqrt{25 + 25} = \sqrt{50} \approx 7.07$. Individual B is assigned to Cluster 2.

*   Distance(C, C1) = $\sqrt{(165-160)^2 + (60-55)^2} = \sqrt{25 + 25} = \sqrt{50} \approx 7.07$
*   Distance(C, C2) = $\sqrt{(165-180)^2 + (60-75)^2} = \sqrt{225 + 225} = \sqrt{450} \approx 21.21$. Individual C is assigned to Cluster 1.

*   Distance(D, C1) = $\sqrt{(180-160)^2 + (75-55)^2} = \sqrt{400 + 400} = \sqrt{800} \approx 28.28$
*   Distance(D, C2) = $\sqrt{(180-180)^2 + (75-75)^2} = 0$. Individual D is assigned to Cluster 2.

*   Distance(E, C1) = $\sqrt{(170-160)^2 + (65-55)^2} = \sqrt{100 + 100} = \sqrt{200} \approx 14.14$
*   Distance(E, C2) = $\sqrt{(170-180)^2 + (65-75)^2} = \sqrt{100 + 100} = \sqrt{200} \approx 14.14$. Individual E is assigned to Cluster 1 (in case of a tie, assign to the first cluster or handle according to a rule).

**Initial Clusters:**

*   Cluster 1: A, C, E
*   Cluster 2: B, D

**Step 3: Recalculate centroids.**

Calculate the mean of the data points in each cluster:

*   New Centroid 1 (mean of A, C, E): $(\frac{160+165+170}{3}, \frac{55+60+65}{3}) = (\frac{495}{3}, \frac{180}{3}) = (165, 60)$
*   New Centroid 2 (mean of B, D): $(\frac{175+180}{2}, \frac{70+75}{2}) = (\frac{355}{2}, \frac{145}{2}) = (177.5, 72.5)$

**Step 4: Reassign data points to the nearest new centroid.**

Now we repeat Step 2 with the new centroids:

*   Distance(A, New C1) = $\sqrt{(160-165)^2 + (55-60)^2} = \sqrt{25 + 25} = \sqrt{50} \approx 7.07$
*   Distance(A, New C2) = $\sqrt{(160-177.5)^2 + (55-72.5)^2} = \sqrt{(-17.5)^2 + (-17.5)^2} = \sqrt{306.25 + 306.25} = \sqrt{612.5} \approx 24.75$. Individual A is assigned to Cluster 1.

*   Distance(B, New C1) = $\sqrt{(175-165)^2 + (70-60)^2} = \sqrt{100 + 100} = \sqrt{200} \approx 14.14$
*   Distance(B, New C2) = $\sqrt{(175-177.5)^2 + (70-72.5)^2} = \sqrt{(-2.5)^2 + (-2.5)^2} = \sqrt{6.25 + 6.25} = \sqrt{12.5} \approx 3.54$. Individual B is assigned to Cluster 2.

*   Distance(C, New C1) = $\sqrt{(165-165)^2 + (60-60)^2} = 0$
*   Distance(C, New C2) = $\sqrt{(165-177.5)^2 + (60-72.5)^2} = \sqrt{(-12.5)^2 + (-12.5)^2} = \sqrt{156.25 + 156.25} = \sqrt{312.5} \approx 17.68$. Individual C is assigned to Cluster 1.

*   Distance(D, New C1) = $\sqrt{(180-165)^2 + (75-60)^2} = \sqrt{225 + 225} = \sqrt{450} \approx 21.21$
*   Distance(D, New C2) = $\sqrt{(180-177.5)^2 + (75-72.5)^2} = \sqrt{(2.5)^2 + (2.5)^2} = \sqrt{6.25 + 6.25} = \sqrt{12.5} \approx 3.54$. Individual D is assigned to Cluster 2.

*   Distance(E, New C1) = $\sqrt{(170-165)^2 + (65-60)^2} = \sqrt{25 + 25} = \sqrt{50} \approx 7.07$
*   Distance(E, New C2) = $\sqrt{(170-177.5)^2 + (65-72.5)^2} = \sqrt{(-7.5)^2 + (-7.5)^2} = \sqrt{56.25 + 56.25} = \sqrt{112.5} \approx 10.61$. Individual E is assigned to Cluster 1.

**New Clusters:**

*   Cluster 1: A, C, E
*   Cluster 2: B, D

**Step 5: Repeat steps 3 and 4 until the cluster assignments no longer change.**

In this case, the cluster assignments are the same as in the previous iteration. Therefore, the algorithm has converged.

**Final Clusters:**

*   Cluster 1: Individuals A, C, and E
*   Cluster 2: Individuals B and D

This simple example demonstrates how K-Means groups data points based on their proximity to cluster centroids, iteratively refining the cluster assignments and centroid positions.
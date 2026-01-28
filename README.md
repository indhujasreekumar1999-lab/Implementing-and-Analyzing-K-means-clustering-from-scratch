Implementing and Analyzing K-Means Clustering from Scratch
Overview

This project presents a complete implementation of the K-Means clustering algorithm developed from first principles using NumPy. The goal of the project is to understand how unsupervised learning works internally, rather than relying on pre-built machine learning libraries.

A synthetic dataset with overlapping clusters is used to evaluate the robustness of the implementation. The project also applies the Elbow Method and Silhouette Analysis to determine the optimal number of clusters and to interpret the clustering quality.

Project Objectives

Implement K-Means clustering without using scikit-learn

Understand centroid initialization, distance computation, and convergence

Evaluate clustering performance using standard metrics

Visualize and interpret clustering results

Project Structure
kmeans-from-scratch/
├── kmeans.py
├── analysis.py
├── outputs/
│   ├── kmeans_clustering_output.jpg
│   └── metrics.txt
└── README.md

Dataset Description

The dataset consists of 500 two-dimensional data points generated using Gaussian distributions. Three overlapping clusters are intentionally created to simulate a realistic and challenging clustering scenario. The overlapping nature of the data helps evaluate how well the algorithm handles ambiguity in cluster boundaries.

K-Means Implementation

The K-Means algorithm is implemented step by step using NumPy:

Random initialization of centroids from the dataset

Calculation of Euclidean distance between data points and centroids

Assignment of each data point to the nearest centroid

Updating centroids based on the mean of assigned points

Iterative repetition until convergence or maximum iterations

This implementation avoids the use of any external clustering libraries to ensure conceptual clarity.

Evaluation Methods
Elbow Method (Sum of Squared Errors)

The Elbow Method is used to measure how the compactness of clusters improves as the number of clusters increases. A sharp reduction in SSE followed by a gradual decrease indicates the optimal cluster count.

Silhouette Analysis

Silhouette Analysis evaluates how well each data point fits within its assigned cluster compared to other clusters. Higher silhouette values indicate better cluster separation and cohesion.

Both methods are applied for K values ranging from 2 to 10.

Analysis and Interpretation

The Elbow Method shows a noticeable bend at K = 3, suggesting that adding more clusters beyond this point provides diminishing improvement in clustering quality. Silhouette Analysis also reaches its highest value at K = 3, indicating strong separation between clusters and good intra-cluster cohesion.

For values of K lower than 3, distinct clusters are merged, leading to higher intra-cluster variance. For values greater than 3, clusters are unnecessarily divided, reducing interpretability. Therefore, K = 3 is identified as the optimal number of clusters for this dataset.

Visualization

The final clustering result is visualized using a scatter plot where data points are colored by their assigned cluster, and centroids are highlighted for clarity. The visualization is saved as a JPG file:

outputs/kmeans_clustering_output.jpg

Notes on Initialization

Random centroid initialization is used in this implementation for simplicity. Future improvements could include the use of K-Means++ initialization to improve convergence stability and clustering consistency.

Key Learnings

Practical understanding of distance-based clustering algorithms

Importance of evaluation metrics in unsupervised learning

Impact of data overlap on clustering performance

Relationship between cluster count and model interpretability

Conclusion

This project demonstrates a clear understanding of the K-Means clustering algorithm by implementing it entirely from scratch and evaluating its performance using established metrics. The results align with the known structure of the synthetic dataset, confirming the effectiveness of the approach.

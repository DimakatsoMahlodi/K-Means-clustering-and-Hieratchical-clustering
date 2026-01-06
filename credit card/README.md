# Clustering Analysis of Credit Card Dataset

## 1. Overview

This study applies unsupervised learning techniques—Hierarchical Clustering and K-Means Clustering—to the Credit Card dataset to identify natural groupings of clients. The primary objective is to uncover patterns in customer financial and demographic behavior, which can inform marketing strategies, risk assessment, and customer behavior analysis.

By comparing both clustering methods, we aim to gain complementary insights into the structure and characteristics of the client segments.

## 2. Dataset Description

Dataset Name: default of credit card clients.xls

Contents: Anonymized credit card client data including:

Credit limits (LIMIT_BAL)

Demographic attributes (SEX, AGE)

Default payment status and other financial indicators

Preprocessing: The first row (original headers) was removed to ensure correct data interpretation. Missing values and anomalies were addressed to ensure data consistency.

## 3. Hierarchical Clustering

Hierarchical clustering was employed to explore nested relationships among clients and segment them based on key attributes.

### 3.1 Methodology

#### Feature Selection:

LIMIT_BAL (credit limit)

SEX (gender)

#### Distance Metric and Linkage:

Euclidean distance was used to measure similarity.

Ward’s linkage was applied to minimize variance within clusters.

#### Dendrogram Construction:

A dendrogram was generated to visualize the merging process.

Only the last 30 merges were displayed for clarity.

Vertical gaps in the dendrogram were analyzed to determine the optimal number of clusters. Five clusters were selected based on significant separation in the dendrogram.

#### Model Training:

Agglomerative clustering was performed with the following parameters:

n_clusters = 5

metric = 'euclidean'

linkage = 'ward'

#### Visualization:

Scatter plots were generated to visualize cluster assignments, with each cluster represented by a distinct color.

Hierarchical clustering highlighted the hierarchical relationships and proximities between client groups.

## 4. K-Means Clustering

K-Means clustering was applied to segment clients based on numerical features and to calculate cluster centroids for interpretable summaries.

### 4.1 Methodology

#### Feature Selection:

Two numerical features (e.g., LIMIT_BAL and AGE) were selected for clustering.

Optimal Cluster Determination:

The Elbow Method was used to determine the optimal number of clusters.

Within-Cluster Sum of Squares (WCSS) was plotted for k = 1–10.

The plot indicated an elbow point at k = 5, suggesting five clusters as optimal.

#### Model Training:

K-Means clustering was implemented with the following parameters:

n_clusters = 5

init = 'k-means++' (to optimize initial centroid selection)

random_state = 42

Each client was assigned to a cluster, and cluster centroids were calculated to represent the average feature values.

#### Visualization:

Scatter plots displayed clusters in distinct colors, with centroids highlighted.

Cluster separation and centroid positions were visually evaluated to confirm coherence.

## 5. Results

Both Hierarchical Clustering and K-Means Clustering identified five distinct clusters, confirming meaningful segmentation.

Hierarchical Clustering: Revealed nested relationships and the relative proximity of clusters.

K-Means Clustering: Provided centroid-based summaries, allowing interpretation of average feature values within each cluster.

Scatter plots confirmed clear and consistent cluster separation for both methods.

## 6. Discussion

#### Method Comparison:

Hierarchical clustering is effective for visualizing cluster structure and understanding nested relationships.

K-Means clustering is ideal for centroid-based analysis and summarizing cluster characteristics numerically.

Complementarity: Using both methods provides a more comprehensive understanding of customer segmentation—structural insight from hierarchical clustering and numerical summary from K-Means.

#### Limitations:

Only two features were used for visualization and clustering; including additional features (e.g., payment history, bill amounts) could reveal more complex patterns.

Scaling and normalization were assumed for numerical features, but differences in scale could influence clustering results.

## 7. Conclusion

The clustering analysis successfully segmented the Credit Card dataset into five coherent groups using Hierarchical and K-Means clustering methods.

Segmentation enables the identification of distinct customer profiles based on financial and demographic attributes.

These insights can support marketing strategies, risk assessment, and behavioral analysis.

Overall, the study demonstrates the effectiveness of unsupervised learning techniques in uncovering meaningful patterns in complex datasets, providing a foundation for data-driven decision-making.



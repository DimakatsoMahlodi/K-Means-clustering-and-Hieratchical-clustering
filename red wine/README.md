# Clustering Analysis on Wine Quality Dataset and EDA
## Overview

This project applies unsupervised learning techniques—Hierarchical Clustering and K-Means Clustering—to the Wine Quality dataset. The goal is to identify natural groupings of wines based on their chemical properties and to gain insights into patterns and similarities that may support quality assessment and future predictive analysis. 


### Dataset

### winequality.csv
Contains chemical measurements of red and white wines along with quality scores.

#### Project Files

This repository includes the following Jupyter Notebook files:

### DATA_CLEANING_.ipynb
Handles data preprocessing tasks such as checking for missing values, removing duplicates, handling outliers, and preparing the dataset for analysis.

### EDA.ipynb
Performs Exploratory Data Analysis (EDA), including summary statistics and visualizations to better understand the distribution and relationships of wine chemical features.

### Clustering_.ipynb
Contains the implementation of Hierarchical Clustering and K-Means Clustering, including model training, visualization, and interpretation of results.

### Hierarchical Clustering
## Methodology

### Dendrogram Analysis

A dendrogram was generated using Ward linkage with Euclidean distance.

The last 30 merges were displayed for clarity.

Significant gaps in the dendrogram suggested five clusters.

Model Training

Agglomerative hierarchical clustering was applied.

Parameters used:

n_clusters = 5

metric = 'euclidean'

linkage = 'ward'

Cluster Visualization

A 2D scatter plot was used to visualize clusters with different colors.

The results showed well-separated groups based on the selected features.

### K-Means Clustering
### Methodology

Optimal Cluster Selection (Elbow Method)

The elbow method was applied to determine the optimal number of clusters.

The elbow point indicated five clusters.

Model Training

K-Means clustering was applied with:

n_clusters = 5

init = 'k-means++'

Cluster labels and centroids were computed.

Cluster Visualization

Clusters were visualized using a scatter plot with distinct colors.

Cluster centroids were highlighted in yellow, making central tendencies easy to interpret.

Results

Both clustering techniques identified five distinct clusters, indicating natural groupings within the dataset.

Hierarchical Clustering revealed nested relationships and how clusters merge at different levels.

K-Means Clustering provided clear centroids, simplifying interpretation of average feature values per cluster.

Scatter plots confirmed good separation between clusters for the selected features.

## Discussion

Hierarchical clustering is effective for understanding hierarchical relationships among observations.

K-Means is well-suited for identifying centroid-based clusters and summarizing numerical data.

Using both methods provides complementary insights:

Hierarchical clustering for structural understanding.

K-Means for centroid-based interpretation.

Limitation: Clustering was performed on only two features for visualization, which may not capture all complex relationships among chemical properties.

## Conclusion

This project successfully identified five meaningful clusters in the Wine Quality dataset using both Hierarchical and K-Means clustering methods. The analysis highlights how unsupervised learning techniques can uncover hidden structure and patterns in complex datasets. These findings provide a strong foundation for future work, such as predicting wine quality or exploring deeper relationships between chemical features.







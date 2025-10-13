# Clustering Analysis on Wine Quality Dataset

## Overview

This project applies unsupervised learning techniques—Hierarchical Clustering and K-Means Clustering—to the Wine Quality dataset. The aim is to identify natural groupings of wines based on their chemical properties, providing insights into patterns and similarities that could inform quality assessment and further predictive analysis.

---

## Datasets

- **winequality.csv** – Includes chemical measurements of wines (red and white) along with quality scores.

---

## Hierarchical Clustering

Hierarchical clustering was performed on the first two numerical features of the dataset to identify natural groupings.

### Methodology

1. **Dendrogram Analysis**  
   - A dendrogram using Ward linkage with Euclidean distance was generated.  
   - The last 30 merges were displayed for clarity.  
   - Based on significant gaps in the dendrogram, five clusters were selected.

2. **Model Training**  
   - Agglomerative hierarchical clustering assigned wines to five clusters.  
   - Parameters used: `n_clusters = 5`, `metric = 'euclidean'`, `linkage = 'ward'`.

3. **Cluster Visualization**  
   - A 2D scatter plot visualized the clusters with distinct colors.  
   - Hierarchical clustering revealed well-separated groups based on the selected features.

---

## K-Means Clustering

K-Means clustering was applied to a different pair of numerical features from the Wine Quality dataset to identify and visualize cluster centers.

### Methodology

1. **Optimal Cluster Selection (Elbow Method)**  
   - The elbow method was used to determine the optimal number of clusters, which was identified as five.

2. **Model Training**  
   - K-Means clustering was applied with `n_clusters = 5`, using the `k-means++` initialization method.  
   - Cluster assignments and centroids were computed for visualization.

3. **Cluster Visualization**  
   - Each cluster was plotted with a distinct color, and centroids were highlighted in yellow.  
   - This plot provided a clear representation of cluster structure and central tendencies.

---

## Results

- Both clustering methods produced **five distinct clusters**, demonstrating natural groupings within the Wine Quality dataset.  
- **Hierarchical Clustering** revealed nested relationships and proximity between clusters.  
- **K-Means Clustering** provided clear centroids, making it easier to interpret average feature values for each cluster.  
- Scatter plots confirmed coherent cluster separation for the selected features.

---

## Discussion

- Hierarchical clustering is effective for understanding hierarchical relationships between observations, showing how clusters merge at different levels.  
- K-Means is suitable for identifying cluster centroids and provides easily interpretable clusters for numerical analysis.  
- Using both methods offers complementary insights: hierarchical clustering for structure and K-Means for centroid-based summaries.  
- Limitations: Clustering was performed on only two features for visualization purposes, which may not capture complex relationships present in all chemical properties.

---

## Conclusion

The clustering analysis successfully identified five distinct clusters in the Wine Quality dataset using both Hierarchical and K-Means approaches.  
These methods revealed meaningful groupings based on chemical composition, offering a foundation for further analysis, such as predicting wine quality or exploring relationships between chemical features.  
Overall, this study demonstrates how unsupervised learning techniques can uncover patterns and structure within complex datasets.

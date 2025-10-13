# Clustering Analysis on Credit Card Dataset

## Overview

This project applies unsupervised learning techniques—**Hierarchical Clustering** and **K-Means Clustering**—to the Credit Card dataset. The aim is to identify natural groupings of clients based on financial and demographic features, providing insights into customer segmentation for marketing strategies, risk assessment, and behavioral analysis.

---

## Dataset

- **default of credit card clients.xls** – Contains anonymized credit card client data, including credit limits, demographic attributes (such as sex and age), and default payment information.

---

## Hierarchical Clustering

Hierarchical clustering was applied to explore the relationships and segment clients based on key features.

### Methodology

1. **Feature Selection**  
   - Two features were used: `LIMIT_BAL` (credit limit) and `SEX`.  
   - The first row (original headers) was excluded to avoid incorrect data interpretation.

2. **Dendrogram Analysis**  
   - A dendrogram was generated using the Ward linkage method with Euclidean distance.  
   - Only the last 30 merges were displayed for clarity.  
   - Five clusters were chosen based on significant vertical gaps, indicating optimal cluster separation.

3. **Model Training**  
   - Agglomerative hierarchical clustering assigned clients to five clusters with the following parameters:  
     - `n_clusters = 5`  
     - `metric = 'euclidean'`  
     - `linkage = 'ward'`  

4. **Cluster Visualization**  
   - A scatter plot showed each cluster in a distinct color.  
   - Hierarchical clustering revealed nested relationships, demonstrating how clusters merge at different levels.

---

## K-Means Clustering

K-Means clustering was applied to segment clients based on a different set of numerical features for centroid-based analysis.

### Methodology

1. **Feature Selection**  
   - Two numerical features were selected for clustering (e.g., credit limit and age).  

2. **Optimal Cluster Selection (Elbow Method)**  
   - The elbow method was used to plot WCSS (Within-Cluster Sum of Squares) for 1–10 clusters.  
   - The elbow point suggested **five clusters** as optimal.

3. **Model Training**  
   - K-Means clustering was applied with:  
     - `n_clusters = 5`  
     - `init = 'k-means++'`  
     - `random_state = 42`  
   - Clients were assigned to clusters, and centroids were calculated.

4. **Cluster Visualization**  
   - Each cluster was displayed in a distinct color, with centroids highlighted in yellow.  
   - Scatter plots showed clear separation and average positions of each cluster.

---

## Results

- Both methods produced **five distinct clusters**, indicating meaningful segmentation of clients.  
- **Hierarchical Clustering** highlighted nested relationships and cluster proximities.  
- **K-Means Clustering** provided centroids for interpreting average feature values in each group.  
- Scatter plots confirmed coherent cluster separation across both methods.

---

## Discussion

- **Hierarchical Clustering** is effective for understanding cluster structure and merging relationships.  
- **K-Means Clustering** offers easily interpretable centroids, suitable for numerical summaries.  
- Using both techniques provides complementary insights: hierarchical clustering for structure, K-Means for centroid-based interpretations.  
- Limitation: Clustering was performed on only two features for visualization; additional features could reveal more complex patterns.

---

## Conclusion

The clustering analysis successfully segmented the Credit Card dataset into five coherent groups using both Hierarchical and K-Means approaches.  
This segmentation provides insights into customer profiles based on financial and demographic attributes, supporting strategic decision-making in marketing, risk management, and customer behavior analysis.  
Overall, the study demonstrates how unsupervised learning techniques can uncover meaningful patterns in complex datasets and guide data-driven decisions.

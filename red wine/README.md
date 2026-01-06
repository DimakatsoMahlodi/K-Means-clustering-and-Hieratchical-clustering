# Clustering Analysis and Exploratory Data Analysis of the Wine Quality Dataset

## 1. Overview

This project applies unsupervised machine learning techniques—Hierarchical Clustering and K-Means Clustering—to the Wine Quality dataset. The primary objective is to identify natural groupings of wines based on their physicochemical properties. By uncovering patterns and similarities within the data, the study aims to enhance understanding of wine characteristics and provide a foundation for future quality assessment and predictive modeling.


## 2. Dataset Description
winequality.csv

The dataset contains physicochemical measurements of red and white wines, along with a quality score assigned through sensory evaluation. The chemical attributes include acidity levels, alcohol content, sulfur dioxide concentration, and other factors known to influence wine quality.

## 3. Project Structure and Files

The analysis is organized into the following Jupyter Notebook files:

### 3.1 DATA_CLEANING_.ipynb

This notebook focuses on data preprocessing, including:

Detection and handling of missing values

Removal of duplicate records

Identification and treatment of outliers

Data formatting and preparation for analysis

These steps ensure data consistency, reliability, and suitability for exploratory analysis and clustering.

## 3.2 EDA.ipynb

This notebook performs Exploratory Data Analysis (EDA) to understand the underlying structure of the dataset. Key activities include:

Descriptive statistics (mean, median, standard deviation)

Distribution analysis using histograms and box plots

Exploration of relationships between variables using scatter plots and correlation analysis

EDA provides insights into feature behavior and guides the selection of variables for clustering.

## 3.3 Clustering_.ipynb

This notebook implements Hierarchical Clustering and K-Means Clustering, including model construction, visualization, and interpretation of clustering results.

# 4. Hierarchical Clustering

## 4.1 Methodology

Dendrogram Analysis

A dendrogram was constructed using Ward’s linkage method with Euclidean distance. To improve readability, the last 30 merges were displayed. Clear vertical gaps in the dendrogram indicated the presence of five distinct clusters.

Model Training

Agglomerative hierarchical clustering was applied with the following parameters:

n_clusters = 5

metric = 'euclidean'

linkage = 'ward'

Cluster Visualization

Clusters were visualized using a two-dimensional scatter plot, with each cluster represented by a different color. The visualization demonstrated clear separation between groups based on the selected features.

# 5. K-Means Clustering

## 5.1 Methodology

Optimal Cluster Selection (Elbow Method)

The Elbow Method was used to determine the optimal number of clusters by analyzing the within-cluster sum of squares (WCSS). The elbow point was observed at k = 5, supporting the choice identified through hierarchical clustering.

Model Training

K-Means clustering was performed with the following parameters:

n_clusters = 5

init = 'k-means++'

Cluster labels and centroid coordinates were calculated to summarize the central tendency of each cluster.

Cluster Visualization

Clusters were displayed in a two-dimensional scatter plot. Cluster centroids were highlighted in yellow, allowing for clear interpretation of the average feature values within each group.

# 6. Results

Both Hierarchical Clustering and K-Means Clustering consistently identified five distinct clusters, suggesting stable and meaningful groupings within the dataset.

Hierarchical clustering revealed nested relationships and illustrated how observations merge across different similarity levels.

K-Means clustering provided clearly defined centroids, facilitating quantitative interpretation of cluster characteristics.

Visual inspection of scatter plots confirmed good separation among clusters for the selected features.

# 7. Discussion

Hierarchical clustering is particularly useful for understanding the hierarchical structure and relationships among observations, while K-Means clustering is effective for summarizing data through centroid-based groupings. The combined use of both methods offers complementary insights:

Hierarchical clustering supports structural and relational analysis.

K-Means clustering enables efficient interpretation of numerical patterns.

Limitation: For visualization purposes, clustering was performed using only two features. While effective for illustration, this approach may not fully capture the complexity of relationships among all chemical attributes.

# 8. Conclusion

This study successfully identified five meaningful clusters within the Wine Quality dataset using both Hierarchical and K-Means clustering techniques. The findings demonstrate the value of unsupervised learning in revealing hidden structures and patterns in complex chemical datasets. The results provide a strong foundation for future research, including wine quality prediction, feature importance analysis, and the application of supervised learning models.








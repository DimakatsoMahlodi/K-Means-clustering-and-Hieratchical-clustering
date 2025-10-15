# K-Means-clustering and Hierarchical clustering

## Data Cleaning Report

### Abstract

This report presents the data cleaning process conducted on two datasets: Credit Card Transactions and Wine Quality. The aim was to improve the reliability, consistency, and overall quality of the data to make it suitable for analysis and machine learning. Both datasets exhibited issues such as missing values, duplicate entries, outliers, and inconsistent formatting. Systematic cleaning procedures were applied, resulting in datasets that are now ready for exploratory data analysis and modeling. The k means and hierarchical clustering they are unsupervised learning algorothms maening there are no labels to compare predictions to.

---

### Repository Layout

The repository is organized as follows:

- CreditCard/
  - creditcard.csv
  - creditcard.ipynb
  - hierarchical-clustering.ipynb
  - README.md
- WineQuality/
  - winequality.csv
  - winequality.ipynb
  - k-means-clustering.ipynb
  - README.md

---

### Datasets

- creditcard.csv – Contains transaction records including time, amount, and anonymized numerical features, with a target variable indicating fraud.  
- winequality.csv – Includes chemical measurements of wines (red and white) and quality scores.

---

## Methodology

1. **Data Inspection**  
   The datasets were explored to understand their structure, including dimensions, column types, missing values, and value distributions. Histograms and boxplots were used to detect skewness and outliers.

2. **Handling Missing Values**  
   - Credit Card: Less than 0.1% missing in the Amount column was imputed using the median.  
   - Wine Quality: Missing values (~1.5%) in variables such as residual sugar and pH were imputed using the median.

3. **Duplicate Removal**  
   - Credit Card: 35 duplicate transactions were removed.  
   - Wine Quality: 20 duplicate records were eliminated.

4. **Outlier Detection and Treatment**  
   - Credit Card: Extreme transaction amounts were capped at the 99th percentile to reduce the impact of anomalies.  
   - Wine Quality: Outliers in volatile acidity, density, and alcohol were capped using the IQR method. Skewness in residual sugar was reduced using a log transformation.

5. **Data Type and Formatting Corrections**  
   All numeric columns were ensured to have consistent formats. Categorical and target variables were standardized, and column names were cleaned for uniformity.

6. **Normalization and Standardization**  
   - Credit Card: Continuous features were scaled using StandardScaler.  
   - Wine Quality: All features were normalized to a [0,1] range using Min–Max scaling.
     
 # Methodology on both algorithm

This study applied K-Means and Hierarchical Clustering techniques to two datasets — the Credit Card Clients dataset and the Wine Quality dataset — with the objective of grouping similar observations and identifying hidden patterns within the data.

1. Data Import and Preparation

Both datasets were imported using Pandas. For the Credit Card dataset, relevant columns such as EDUCATION and MARRIAGE were selected as features. For the Wine Quality dataset, chemical properties like fixed acidity and volatile acidity were used. Data was checked for completeness and consistency before clustering.

2. K-Means Clustering

The K-Means algorithm was implemented using the sklearn.cluster.KMeans library. The process began with the Elbow Method to determine the optimal number of clusters. The Within-Cluster Sum of Squares (WCSS) was calculated for cluster values ranging from 1 to 10. The point at which the WCSS curve started to flatten was selected as the optimal number of clusters, which was determined to be 5 for both datasets.

After identifying the optimal cluster count, K-Means was applied to group the data. Each observation was assigned to the nearest cluster centroid based on Euclidean distance. Cluster visualizations were created using Matplotlib, where each cluster was color-coded, and the centroids were highlighted in yellow to show cluster separation.

3. Hierarchical Clustering

For the Credit Card dataset, Hierarchical Agglomerative Clustering (HAC) was performed using the scipy and sklearn libraries. A dendrogram was constructed to visualize the hierarchical structure of the data and help determine the number of clusters. The Ward linkage method was chosen to minimize variance within clusters. Based on the dendrogram’s structure, five distinct clusters were identified.

The AgglomerativeClustering model was then applied with the Euclidean metric and Ward linkage to form final clusters. Cluster visualization followed the same approach as in K-Means, highlighting each group in distinct colors for comparison.

4. Visualization and Interpretation

Visualizations for both algorithms were generated using Matplotlib. The x- and y-axes represented selected numerical attributes from each dataset, allowing for clear identification of how data points were grouped. The distribution of clusters revealed meaningful groupings — such as clients with similar financial behaviors in the Credit Card dataset and wines sharing similar chemical compositions in the Wine Quality dataset.
     

## Results

- **Credit Card**  
  - Missing Amount values: 0.1% → 0% (Median imputation)  
  - Duplicate transactions: 35 → 0 (Removed)  
  - Outliers in transaction amount: >99th percentile → Within range (IQR capping)

- **Wine Quality**  
  - Missing chemical features: 1.5% → 0% (Median imputation)  
  - Duplicate records: 20 → 0 (Dropped)  
  - Skewness in residual sugar: 3.2 → 0.8 (Log transform)

---

### Suggested Visualizations

- Credit Card: Boxplots of Amount before and after outlier treatment.  
- Wine Quality: Histograms of residual sugar before and after log transformation.  
- Both: Missing value heatmaps using missingno.

---

## Discussion

The data cleaning process followed a systematic, scientific approach:

- **Observation:** Initial analysis revealed missing values, duplicate entries, and extreme outliers.  
- **Hypothesis:** Applying cleaning and standardization techniques would improve dataset reliability and prepare the data for modeling.  
- **Experimentation:** Missing values were imputed, duplicates removed, outliers capped, and numerical features normalized.  
- **Analysis:** After cleaning, all missing and duplicate records were resolved, and skewness was reduced, resulting in more balanced datasets.
- The k-means-clustering perform better than Hierarchical-clustering , kmeans has higher silhoutte and lower DBI so it performs better.
  
- Both clustering methods successfully identified underlying patterns within the datasets, but they differed in their approach and interpretability.

The K-Means algorithm provided clear, spherical clusters and was computationally efficient, making it suitable for large datasets like Credit Card Clients. Its centroids allowed easy interpretation of cluster centers, revealing groups of clients with similar education, marital status, or spending tendencies. However, K-Means required a predefined number of clusters and was sensitive to outliers and data scaling.

In contrast, Hierarchical Clustering offered deeper insight into the data structure through its dendrogram visualization, which depicted the merging of data points into clusters step by step. This made it particularly useful for understanding relationships between groups, even though it was more computationally intensive. The hierarchical approach proved beneficial for visualizing how customers or wine samples could be merged into broader categories.

When applied to the Wine Quality dataset, both algorithms produced interpretable groupings of wine samples based on their chemical characteristics. K-Means captured compact clusters efficiently, while Hierarchical Clustering revealed nuanced subgroup structures that K-Means could overlook.

**Trade-offs:**  
Median imputation may slightly reduce natural variability, and outlier capping can remove rare but legitimate extreme cases. However, these steps improved overall model performance and analytical reliability.

---
## Conclusion

The data cleaning process successfully enhanced the quality of both datasets:

- The Credit Card dataset is now free from duplicates, normalized, and ready for fraud detection modeling.  
- The Wine Quality dataset is standardized, scaled, and prepared for regression or classification tasks.
- Transforming raw, inconsistent data into structured, reliable, and analysis-ready resources. The Credit Card dataset, now free from duplicates and extreme anomalies, provides a robust foundation for accurate fraud detection modeling. Meanwhile, the Wine Quality dataset, with normalized and standardized features, is ready for meaningful regression and classification analyses. 

These cleaning steps not only improved data integrity but also revealed deeper insights into the datasets, such as patterns in transaction amounts and chemical compositions. By systematically addressing missing values, duplicates, and outliers, the project ensured that subsequent analyses and machine learning models can operate on trustworthy, high-quality data.  

Ultimately, this process demonstrates that thorough data cleaning is not just a preliminary task—it is a critical step that can dramatically influence the accuracy, interpretability, and reliability of any analytical or predictive workflow. The cleaned datasets now serve as a reliable launchpad for uncovering patterns, generating insights, and building models that can make a real-world impact.

Overall, both K-Means and Hierarchical Clustering complemented each other in analyzing the datasets. K-Means excelled in speed and simplicity, providing quick insights into natural groupings, while Hierarchical Clustering added interpretative depth through its visual hierarchy. Together, they provided a comprehensive understanding of the data, effectively segmenting customers and categorizing wines based on shared characteristics.


# K-Means and Hierarchical Clustering: Data Cleaning Report
## Abstract

This report explains the data cleaning and preprocessing steps applied to two datasets: a Credit Card dataset and a Wine Quality dataset. The aim of data cleaning was to improve data quality and prepare the datasets for analysis and machine learning. Common problems such as missing values, duplicate records, outliers, and inconsistent scaling were identified and corrected.

After cleaning, K-Means Clustering and Hierarchical Clustering were applied to both datasets to find patterns and group similar data points. These methods are unsupervised learning algorithms, meaning that no labels are used to check predictions. Instead, clustering quality is evaluated using internal measures.

## 1. Repository Structure

The project files are organised as follows:

CreditCard/
- creditcard.csv
- creditcard.ipynb
- hierarchical-clustering.ipynb
- README.md
- exploratory_data_analysis.ipynb

WineQuality/
- winequality.csv
- winequality.ipynb
- k-means-clustering.ipynb
- README.md
- exploratory_data_analysis.ipynb

## 2. Datasets
Credit Card Dataset

This dataset contains credit card transaction records. It includes transaction amounts, time information, and anonymised numerical features that describe customer behaviour.

Wine Quality Dataset

The Wine Quality dataset contains chemical measurements of wines, such as acidity, alcohol, and sulphates, along with expert quality scores.

## 3. Data Cleaning Process
3.1 Data Inspection

Both datasets were explored to understand their size, structure, and variable types. Histograms and boxplots were used to check distributions and identify outliers.

## 3.2 Handling Missing Values

Credit Card Dataset:
Less than 0.1% of values in the Amount column were missing. These values were replaced using the median.

Wine Quality Dataset:
About 1.5% of values were missing in some chemical features. These were also filled using the median.

## 3.3 Removing Duplicate Records

Credit Card Dataset:
35 duplicate transactions were found and removed.

Wine Quality Dataset:
20 duplicate records were removed to avoid repeated information.

## 3.4 Handling Outliers

Credit Card Dataset:
Very large transaction amounts were capped at the 99th percentile to reduce their effect on analysis.

### Wine Quality Dataset:
Outliers in variables such as volatile acidity, density, and alcohol were capped using the IQR method.
A log transformation was applied to residual sugar to reduce skewness.

## 3.5 Data Formatting

All numerical variables were converted to the correct data type. Column names were cleaned and made consistent.

## 3.6 Scaling the Data

Credit Card Dataset:
Numerical features were standardised using StandardScaler.

Wine Quality Dataset:
Features were scaled to a range between 0 and 1 using Min–Max scaling.

Scaling was important because both clustering algorithms use distance calculations.

## 4. Unsupervised Learning Methods

This study used K-Means Clustering and Hierarchical Clustering to group similar observations in each dataset.

Because clustering is unsupervised learning, there are no true labels to compare results with. Cluster quality was therefore evaluated using measures such as the Silhouette Score and Davies–Bouldin Index.

## 5. K-Means Clustering

K-Means clustering was applied using the Scikit-learn library.

Choosing the Number of Clusters

The Elbow Method was used to find a suitable number of clusters. The results showed that five clusters was an appropriate choice for both datasets.

Clustering Results

After selecting the number of clusters, K-Means grouped data points based on how close they were to cluster centres. The results were visualised using scatter plots, with different colours representing different clusters.

## 6. Hierarchical Clustering

Hierarchical clustering was also applied to both datasets.

A dendrogram was created to show how data points were merged step by step. The Ward linkage method was used, as it reduces variation within clusters. Based on the dendrogram, five clusters were selected.

## 7. Visualisation and Interpretation

Cluster plots helped show how the data was grouped:

In the Credit Card dataset, clusters represented customers with similar spending behaviour.

In the Wine Quality dataset, clusters grouped wines with similar chemical properties.

Hierarchical clustering provided more detail about how clusters were formed, while K-Means produced clearer and more compact groups.

## 8. Results Summary
Credit Card Dataset

Missing values: 0.1% → 0%

Duplicate records: 35 → 0

Extreme transaction amounts: capped at 99th percentile

Wine Quality Dataset

Missing values: 1.5% → 0%

Duplicate records: 20 → 0

Residual sugar skewness reduced after log transformation

## 9. Discussion

The data cleaning process improved the quality of both datasets. Missing values and duplicates were removed, outliers were handled, and features were scaled correctly. These steps made the data more suitable for clustering.

K-Means clustering performed better than hierarchical clustering based on Silhouette Score and Davies–Bouldin Index. This shows that K-Means formed more compact and well-separated clusters. However, hierarchical clustering was useful for understanding relationships between clusters through the dendrogram.

Both methods were useful and provided different insights into the data.

## 10. Conclusion

This project showed that proper data cleaning is an important step before applying machine learning techniques. By fixing missing values, removing duplicates, handling outliers, and scaling features, the datasets were prepared for clustering analysis.

K-Means clustering was fast and effective at finding clear groups, while hierarchical clustering provided useful visual insight into how clusters were formed. Together, these methods helped identify meaningful patterns in both the Credit Card and Wine Quality datasets.


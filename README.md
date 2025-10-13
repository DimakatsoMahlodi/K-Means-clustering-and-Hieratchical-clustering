# K-Means-clustering and Hieratchical clustering

## Data Cleaning Report

### Abstract

This report presents the data cleaning process conducted on two datasets: Credit Card Transactions and Wine Quality. The aim was to improve the reliability, consistency, and overall quality of the data to make it suitable for analysis and machine learning. Both datasets exhibited issues such as missing values, duplicate entries, outliers, and inconsistent formatting. Systematic cleaning procedures were applied, resulting in datasets that are now ready for exploratory data analysis and modeling. The k means and hierarchical clustering they are unsupervised learning algorothms maening there are no labels to compare predictions to.

---

### Repository Layout

The repository is organized as follows:

- CreditCard/
  - creditcard.csv
  - creditcard_cleaning.ipynb
  - README.md
- WineQuality/
  - winequality.csv
  - winequality_cleaning.ipynb
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


# K-Means-clustering and Hieratchical clustering

## Data Cleaning Report

### Abstract

This report presents the data cleaning process conducted on two datasets: **Credit Card Transactions** and **Wine Quality**. The objective was to enhance the reliability, consistency, and analytical quality of the data for further statistical analysis and machine learning applications. Both datasets exhibited unique challenges such as missing values, duplicate records, outliers, and inconsistent formatting. A systematic cleaning process was applied, including detection and imputation of missing data, removal of duplicates, handling of outliers, standardization of data types, and normalization of numerical features. The resulting datasets are now well-prepared for exploratory data analysis (EDA) and predictive modeling.

### Repository Layout

This repository contains two main directories — each including its own Jupyter Notebook, `README`, and raw dataset.

`` CreditCard/
│   ├── creditcard.csv
│   ├── creditcard_cleaning.ipynb
│   └── README.md
│
├── WineQuality/
│   ├── winequality.csv
│   ├── winequality_cleaning.ipynb
│   └── README.md
```

### Datasets

- **creditcard.csv** – Contains transaction records including time, amount, and 28 anonymized numerical features, with a binary class variable indicating fraud (1) or non-fraud (0).  
- **winequality.csv** – Chemical composition and sensory data of red and white wines, with physicochemical inputs (e.g., acidity, pH, alcohol) and an overall quality score.

## ⚙️ Methodology

### 1. Data Inspection
- Verified dataset dimensions, data types, and column integrity.  
- Checked for missing values, data type mismatches, and inconsistencies in categorical labels.  
- Explored value distributions using histograms and boxplots to detect skewness and outliers.

### 2. Handling Missing Values
- **Credit Card:** Less than 0.1% missing data (in the “Amount” column) was imputed using the median to maintain robustness against skewed distributions.  
- **Wine Quality:** Missing entries (~1.5%) in variables such as `residual sugar` and `pH` were filled with the median. Outliers were checked to ensure imputation did not distort the underlying distribution.

### 3. Duplicate Removal
- **Credit Card:** 35 duplicate transactions (exact matches across all columns) were removed to prevent bias in fraud detection analysis.  
- **Wine Quality:** 20 identical records were detected and dropped based on complete row duplication.

### 4. Outlier Detection and Treatment
- **Credit Card:** Extreme transaction amounts were identified using the Interquartile Range (IQR) method and capped at the 99th percentile to reduce the influence of high-value anomalies.  
- **Wine Quality:** Outliers in `volatile acidity`, `density`, and `alcohol` were treated via IQR-based capping. Distribution skewness for `residual sugar` was reduced using a log transformation.

### 5. Data Type & Formatting Corrections
- Ensured all numeric columns were in consistent formats (`float64` where applicable).  
- Standardized categorical and target variable formats (e.g., fraud labels as 0/1, wine quality as integer categories).  
- Removed redundant spaces and ensured all column names were lowercase for uniformity.

### 6. Normalization & Standardization
- **Credit Card:** Applied `StandardScaler` normalization to continuous variables (e.g., `Amount`, `Time`) to prepare for model training.  
- **Wine Quality:** All chemical attributes were scaled using Min–Max normalization to [0,1] range for balanced model input representation.

---

## Results

| Dataset          | Issue                      | Before         | After          | Method Applied           |
|------------------|----------------------------|----------------|----------------|--------------------------|
| Credit Card      | Missing Amount values      | 0.1% missing   | 0% missing     | Median imputation        |
|                  | Duplicate transactions     | 35 records     | 0              | Removed                  |
|                  | Outliers in transaction amt| >99th pct.     | Within range   | IQR capping              |
| Wine Quality     | Missing chemical features  | 1.5% missing   | 0% missing     | Median imputation        |
|                  | Duplicate records          | 20             | 0              | Dropped                  |
|                  | Skewness in residual sugar | 3.2            | 0.8            | Log transform            |

---

### Suggested Visualizations

To illustrate data improvements, the following plots can be included:
- **Credit Card:** Boxplot of `Amount` before and after outlier capping.  
- **Wine Quality:** Histogram of `residual sugar` before vs. after log transformation.  
- **Both:** Missing value heatmap using `missingno` to visualize completeness before cleaning.

---

## Discussion

The data cleaning process followed the **scientific method**, beginning with **observation** of data inconsistencies and progressing through **hypothesis-driven corrections** aimed at improving reliability and model readiness.

- **Observation:** Initial exploration revealed minor missingness, duplicate entries, and extreme outliers in both datasets.  
- **Hypothesis:** Cleaning and normalization would enhance dataset integrity, reduce noise, and improve the predictive accuracy of subsequent models.  
- **Experimentation:** Missing values were imputed, duplicates removed, and outliers capped. Numerical columns were normalized to standardize feature scales.  
- **Analysis:** Post-cleaning diagnostics showed that all datasets achieved complete integrity (no missing or duplicate records) and reduced skewness, resulting in more balanced data distributions.  

**Trade-offs:**  
While imputation improved dataset completeness, it may slightly reduce natural variance. Similarly, outlier capping and transformations enhanced normality but could obscure genuine extreme cases (e.g., legitimate high-value transactions).

---

## Conclusion

The data cleaning process effectively improved the analytical quality of both datasets.  

- The **Credit Card** dataset is now free from duplication and scale imbalances, providing a strong foundation for fraud detection modeling.  
- The **Wine Quality** dataset has been standardized, imputed, and normalized, making it suitable for regression and classification tasks.  

By following systematic cleaning procedures based on the scientific method, data reliability, interpretability, and readiness for modeling have been significantly enhanced. Future improvements may include advanced outlier detection using machine learning (e.g., Isolation Forest) and domain-specific thresholding for chemical measurements or transaction values. 

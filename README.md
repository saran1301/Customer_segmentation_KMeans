# Customer_segmentation_KMeans
This project demonstrates the power of KMeans clustering in identifying distinct customer segments within an online retail environment. The insights derived from the clustering analysis can help businesses tailor their marketing strategies, improve customer retention, and enhance overall customer experience.

File Structure :
src/
│
├── Notebooks/
│   └── YourNotebook.ipynb
|
├── Visualisations/
   ├── image1.png            
   ├── image2.png
   └── image3.png          

---

# Customer Segmentation Using KMeans Clustering

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset Overview](#dataset-overview)
3. [Data Exploration](#data-exploration)
4. [Data Cleaning](#data-cleaning)
5. [Feature Engineering](#feature-engineering)
6. [KMeans Clustering](#kmeans-clustering)
7. [Clustering Insights](#clustering-insights)
8. [Visualizations](#visualizations)
9. [Conclusion](#conclusion)

## Introduction
In today's competitive business environment, understanding customer behavior is crucial for crafting effective marketing strategies. This project leverages KMeans clustering to segment customers based on their purchasing behavior, providing actionable insights that can enhance customer relationship management.

## Dataset Overview
The dataset used in this analysis is the **Online Retail II** dataset, which contains transactional data from a UK-based online retailer. The data includes attributes such as `Customer ID`, `Invoice`, `StockCode`, `Quantity`, `Price`, and `InvoiceDate`. 

## Data Exploration
We start by examining the dataset to understand its structure and identify potential issues:

```python
df = pd.read_excel("./data/online_retail_II.xlsx", sheet_name=0)
df.head(10)
df.info()
```

### Key Findings:
- The dataset contains several anomalies, including missing `Customer ID`s and negative quantities.
- Stock codes have inconsistent formats, necessitating a cleaning step.

## Data Cleaning
The data cleaning process involves:
1. Removing records with missing `Customer ID`.
2. Filtering out transactions with negative quantities or zero prices.
3. Ensuring that `Invoice` and `StockCode` follow consistent formats.

After cleaning, we retained approximately **77%** of the original records, setting the stage for further analysis.


## Feature Engineering
We engineered three key features for clustering:
- **Monetary Value**: Total spending per customer.
- **Frequency**: Number of unique invoices per customer.
- **Recency**: Days since the last purchase.

The aggregated data structure allows for a meaningful analysis of customer segments.

![image](https://github.com/saran1301/Customer_segmentation_KMeans/blob/c39d0d4a720bd6841fddee10cc5140b1b2038d8b/src/Visualizations/Histograms.png)

## KMeans Clustering
We utilized the KMeans clustering algorithm to categorize customers based on the engineered features. Key steps included:
- Standardizing the feature set to ensure each feature contributes equally.
- Determining the optimal number of clusters through the elbow method and silhouette scores.

![image](https://github.com/saran1301/Customer_segmentation_KMeans/blob/c39d0d4a720bd6841fddee10cc5140b1b2038d8b/src/Visualizations/KMeans_Clustering.png)

After testing various values of \( k \), we settled on **4 clusters** for analysis.

## Clustering Insights
The final clusters are characterized as follows:

1. **Cluster 0 (Retain)**: High-value customers with regular purchases. 
   - **Action**: Focus on retention strategies.
  
2. **Cluster 1 (Re-Engage)**: Infrequent, lower-value customers. 
   - **Action**: Targeted marketing to encourage repeat purchases.

3. **Cluster 2 (Nurture)**: Recent but low-value customers. 
   - **Action**: Enhance engagement to increase frequency.

4. **Cluster 3 (Reward)**: Very frequent and high-value customers. 
   - **Action**: Implement loyalty programs and rewards.

![image](https://github.com/saran1301/Customer_segmentation_KMeans/blob/c39d0d4a720bd6841fddee10cc5140b1b2038d8b/src/Visualizations/3D_ScatterPlot_3_Final.png)

## Visualizations
We created various visualizations to summarize and present the findings effectively:

1. **Violin Plots**: These plots illustrate the distribution of key features across clusters, highlighting differences in customer behavior.
   
   ![image](https://github.com/saran1301/Customer_segmentation_KMeans/blob/c39d0d4a720bd6841fddee10cc5140b1b2038d8b/src/Visualizations/Violin%20Plots.png)

2. **Cluster Distribution Bar Chart**: This chart depicts the number of customers in each cluster, accompanied by the average feature values.

   ![image](https://github.com/saran1301/Customer_segmentation_KMeans/blob/c39d0d4a720bd6841fddee10cc5140b1b2038d8b/src/Visualizations/Cluster%20Distribution.png)

## Conclusion
This project demonstrates the power of KMeans clustering in identifying distinct customer segments within an online retail environment. The insights derived from the clustering analysis can help businesses tailor their marketing strategies, improve customer retention, and enhance overall customer experience.

---

### Additional Notes:
- **Future Work**: Consider further segmentation analysis using additional features or alternative clustering methods.
- **Implementation**: This methodology can be applied to various datasets to gain insights into customer behavior across different domains.

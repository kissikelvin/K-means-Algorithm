# KMeans-Algorithm

*by KELVIN KISSI*

## Spending Beyond our K-Means

This project applies unsupervised learning to define customer segments or clusters using the K-means algorithm. The goal is to segment customers based on their purchasing behavior and develop targeted marketing strategies to increase revenue.

---

## Definitions

The [K-means](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) algorithm requires all columns in a DataFrame to have numeric values with the same scale. A centroid is a key part of how the K-means algorithm clusters its observations. For example, if four groups exist (K=4), we’ll have four centroids. These centroids mathematically describe the boundaries that characterize the differences between one group and the next.

Before running the K-means algorithm, verify that the data meets the following requirements:

All data columns have numeric values.
The same scale applies to the numeric values.
Every column in the DataFrame has relevance for clustering because it represents a relevant characteristic.

## Installation

Before running the application, install the following dependencies:

````
pip install pandas
pip install -U scikit-learn
conda install -c pyviz hvplot
````

---

## Using the K-Means Algorithm for Customer Segmentation

This project uses historical data from purchases made by 200 customers at an online store. The process includes importing the K-means algorithm, creating and initializing an instance, training the model, predicting the clusters, adding a new column with the predicted clusters, and creating a scatter plot.

Clustering for characterizing customer types is an important analytics problem in fintech and elsewhere. We can apply clustering techniques to any general financial problem where grouping or knowledge discovery is important. Identifying the optimal number of clusters for an unlabeled dataset can involve uncertainty.

---

![](./01-Spending_Beyond_Our_KMeans/Resources/customer_segments_k4.png)

---

![](./01-Spending_Beyond_Our_KMeans/Resources/customer_segments_k5.png)

There is a big difference in the cluster assignment for transactions involving individuals with an income of less that 40,000 and a spending score of less than 40. With 5 clusters, these individuals are assinged their own segment. With only 4 clusters, they are assigned to a segment that includes individuals with incomes between 40,000 and 75.000 and a spending score between 40 and 60. 5 clusters seems to fit this dataset much better.

---

## The Elbow Method - Points of Diminishing Return

The [Elbow Method](https://en.wikipedia.org/wiki/Elbow_method_(clustering)) is a commonly used heuristic for determining the number of clusters in a dataset. The algorithm uses inertia to measure how distributed or spread out the data points are within a cluster. The smaller the inertia, the closer all the data points are within a cluster. The optimal value for K is found at the elbow of the curve, or when the measure of inertia shows minimal change for each additional cluster added to the dataset.

![](./01-Spending_Beyond_Our_KMeans/Resources/inertia.png)

The best number for k is its value where the curve flattens out like an elbow. In the preceding image, this seems to happen at about k=3, but selecting the exact best value involves some degree of subjectivity.

---

## Standard Scaling and PCA

Applying [Principal Component Analysis](https://en.wikipedia.org/wiki/Principal_component_analysishttps://en.wikipedia.org/wiki/Principal_component_analysis) (PCA) enhances machine learning algorithms. Prior to applying PCA, transform the features of data by applying standard scaling. The StandardScaler transforms data by calculating the mean value of the column and scaling the data in the column to a standard deviation of 1. This helps give the same foundation to all variables that a model uses. Otherwise, results in machine learning models might become distorted because columns of data with larger values or values that range more widely than others could have a larger influence on the analysis. Combining PCA with the K-means algorithm provides a strategy for better dealing with huge financial datasets.

---
<div align="center">
   
   [Source Code](https://github.com/kelvinkissi/K-means-Algorithm/blob/main/spending_beyond_our_kmeans-checkpoint.ipynb)
   
</div>


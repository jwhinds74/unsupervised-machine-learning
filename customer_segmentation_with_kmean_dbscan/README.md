# __UNSUPERVISED LEARNING APPROACHES FOR SEGMENTATION WITH K-MEANS & DBSCAN__     

A retail store aims to enhance customer engagement and optimize inventory management. Analysis of purchasing behavior through loyalty program data indicated a need for more granular customer segmentation. This insight led to the initiation of a segmentation project using unsupervised learning approaches to uncover detailed customer patterns.

<p align="center">
  <img src="https://github.com/user-attachments/assets/7e43e953-6e89-4d61-8ccd-fc8d19893f4e">
</p>

## __Why is this analysis important?__
__This segmentation project paly a vital role for retail stores in general as it leverages advanced unsupervised learning techniques, such as K-Means and DBSCAN, to uncover detailed patterns in customer purchasing behavior. By identifying distinct customer segments through the analysis of loyalty program data, the store can tailor its marketing strategies to better engage customers, enhance their shopping experience, and optimize inventory management. This targeted approach will not only improve customer satisfaction but also drive sales and operational efficiency, ultimately contributing to the store's long-term success and competitive advantage.__

## __PROJECT GOAL__

The goal of this segmentation project is to analyze and categorize the purchasing behavior of approximately 2,000 individuals from a retail store using unsupervised learning approaches: hierarchical and flat approaches specifically K-Means and DBSCAN with variants of each models optimized with Principal Component Analysis PCA that will lead to find insightful segments of customers.

The dataset provided with fictitious records through loyalty program information at checkout, provides valuable insights into customer behavior. By leveraging these clustering techniques, we aim to identify distinct customer segments, enabling the retail store to tailor marketing strategies, improve customer engagement, and optimize inventory management.

## __Uncovering Meaningful Realtionships__
This project is essential as it uncovers meaningful relationships in customer purchasing behavior from scratch, especially when analysts initially see no clear insights. By applying K-Means and DBSCAN clustering techniques, we can reveal hidden patterns and segments within the loyalty program data, enabling data-driven decisions.
![image](https://github.com/user-attachments/assets/2a536fc5-0cf4-4823-ba87-874943f16074)


## __HIERARCHICAL CLUSTERING__
In this project, employing hierarchical clustering offers several distinct advantages that can enhance the depth and breadth of this analysis. Unlike K-Means and DBSCAN methods to be employeed next, hierarchical clustering does not require the pre-specification of the number of clusters, allowing for a more natural exploration of the data's structure. This method builds a hierarchy of clusters that can be visualized as a dendrogram. 

![image](https://github.com/user-attachments/assets/85856c12-37a4-418d-ab7c-f21704e4b62b)

Using next techniques like K-Means and DBSCAN for customer segmentation provides a more reliable and efficient approach compared to hierarchical clustering, such as dendrograms. K-Means and DBSCAN excel in handling large datasets and identifying clusters based on proximity and density, respectively. They offer clearer insights into customer behavior patterns, enabling the retail store to adapt marketing strategies and inventory management more effectively. These methods are robust in uncovering hidden relationships and segments, ensuring a more precise understanding of customer preferences and enhancing overall business decision-making.

## __FLAT CLUSTERING APPROACHES (K MEANS)__
## __K Means Clustering Approach #1__
the sum of the variance between the observations in each cluster and it measures the distance between each observation and the centroid and calculates the squared difference between the two. Hence the name within cluster sum squares.
I will use within cluster sum of squares values to determine the best clustering solution.
Then, I'm going to set the number of clusters to i and initialize the K-means++ algorithm that runs before the actual K-means and finds the best starting points for the centroids.

![image](https://github.com/user-attachments/assets/dd4abd47-341a-4a28-9fe9-3eb788276088)

## Results for K Means Approach #1
![image](https://github.com/user-attachments/assets/c423fd93-87c6-4c53-b36c-6618c63db088)
### According to the visual above, it seem difficult to differentiate clusters for Averages and Disadvantages, because of this, this approach must be tune in order to get a better result.



## __K Means Clustering Approach #2__
## Principal Components Analysis for K Means Clustering
### PCA will creates as many components as there are features in our data, in our case will create 7
![image](https://github.com/user-attachments/assets/8a8b6bf4-9c78-4d2c-870d-2447f080e0e4)
The rule of thumb: Keep 80% of the variance, so keep 3 component make sense
![image](https://github.com/user-attachments/assets/165b1282-9540-4fac-8ef9-88ac8036ae8a)


## Insights for K Means Clustering Tuned with PCA
### We'll add the values of the separate components to our segmentation dataset

#### 1st line This line concatenates the `df_segmentation` DataFrame (with the index reset) and a DataFrame pd.DataFrame(Scores_pca) horizontally along the columns axis. The result is assigned to a new DataFrame df_segm_pca_kmeans
####  2nd line assigns new column names to the last three columns of the df_segm_pca_kmeans DataFrame. The new column names are 'Component 1', 'Component 2', and 'Component 3'
####  3rd line adds a new column named 'Segment K-means PCA' to the df_segm_pca_kmeans DataFrame and assigns the values from the kmeans_pca.labels_ attribute to this column. The kmeans_pca.labels_ attribute contains the cluster labels assigned by the K-means clustering algorithm.

## Visualizing Clusters from K Means Model Aproach #2
![image](https://github.com/user-attachments/assets/fa142243-3f22-45a2-962d-337330ce8147)
### K Means Clustering with PCA has provided a clearer and more concise clusters, with easily interpretable segments.



## __FLAT CLUSTERING APPROACHES (DBSCAN)__

## __DBSCAN Approach #1__
## Parameters Scenarios for DBSCAN approach #1
### Find the optimal parameters with heuristic method based in K nearest neighbors
![image](https://github.com/user-attachments/assets/b8a0830d-6ee1-4df2-a793-59f727ca5bfb)

## Visualizing Clusters from DBSCAN Model Aproach #1
![image](https://github.com/user-attachments/assets/bfb3345e-433f-4fe9-a94e-10ca142088c4)
### Alike the first approach for K Means Clustering, it seems difficult to differentiate clusters for Averages and Disadvantages segments in DBSCAN Clustering as well, this approach must be tuned in order to get a better result.



## __DBSCAN Approach #2__
## Fitting DBSCAN Model Approach #2
## Evaluating Performance for DBSCAN Model Approach #2
Since DBSCAN does not have an attribute inertia_ because it does not minimize a within-cluster sum of squares as KMeans does. Instead, DBSCAN identifies clusters based on density.
To evaluate the quality of DBSCAN clustering, we can look at metrics like silhouette score, number of clusters, or number of noise points. 
![image](https://github.com/user-attachments/assets/31e2155a-483a-42d1-9bb4-7b3baea56277)

## DBSCAN Model Approach #2 Tuned with PCA
## Visualizing Clusters from DBSCAN Model Aproach #2
![image](https://github.com/user-attachments/assets/ce31c49c-b80e-43b5-b634-3ebde3cb402e)

### DBSCAN Clustering with PCA has provided a clearer but more granular clusters segmentation, even though easily interpretable segments it seems to capturing more subtle patterns.



## DBSCAN Approaches Comparison

### Cluster Characteristics:

Approach #1: Not clear clusters, then hard interpretable segments in particular for Disadvantaged and Standard segments.

Approach #2: More clusters with potentially overlapping or mixed characteristics, making interpretation more complex.

### Data Reduction with PCA:

PCA may have introduced more variance that led to the creation of additional clusters. This is useful for capturing more subtle patterns but can also introduce noise.

### Interpretability:

**Approach #1** offers less straightforward and interpretable clusters.

**Approach #2** provides a more granular segmentation, which might be beneficial if those additional segments are meaningful and actionable.

### Actionability:

The blurred segmentation in Approach #1 is likely difficult to act upon for marketing or customer relationship strategies.

The additional segments in Approach #2 might provide deeper insights but could complicate the decision-making process.

![image](https://github.com/user-attachments/assets/baa79ced-e199-4c0c-b3ae-fbaf88360ce0)



## MAIN INSIGHTS

### Data Reduction with PCA:
K-Means: PCA helped in identifying clear clusters, with slight differences in demographic and income characteristics.
DBSCAN: PCA introduced additional clusters, capturing more subtle patterns and adding complexity.

### Interpretability:
K-Means: Both approaches (with PCA) provided clear and concise clusters with easily interpretable segments.
DBSCAN: The approach on the PCA-reduced data added more complexity with additional clusters.

### Conclusion:
K-Means: Preferred for its clear and actionable clusters, both with PCA treatment.
DBSCAN: Useful for identifying outliers and more granular segmentation, especially when PCA is applied, though it may introduce complexity.

### Actionable Insights and Further Use
These results look suitable for Customer Segmentation, then should be helpful to create targeted marketing strategies and
design personalized offers and promotions for different customer segments.













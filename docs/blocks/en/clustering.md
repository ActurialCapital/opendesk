---
icon: fontawesome/solid/battery-full
---

# Clustering

## Definition

Clustering methods are becoming increasingly common in portfolio management, aiming to address the inefficiencies of sectoral clustering analysis (particularly GICS). This study focuses on the most popular clustering methods, such as Partitioning Around Medoids (PAM), Hierarchical Clustering, and Gaussian Mixture Model, and provides examples of their use in portfolio management. We have developed modeling techniques based on graph theory and community detection to enhance the clustering analysis.

## Clustering Techniques

!!! Preprocessing
    To enhance the accuracy of clustering operations, it is preferable to transform the data prior to any analysis. Some clustering techniques are more reliable when the parameters are normalized and reduced to a few dimensions, for instance, Principal Component Analysis (PCA) and Multi-Dimensional Scaling (MDS). Nonetheless, it is crucial to consider the data characteristics and the selected sample. Research indicates that normalizing the data can boost the efficiency of clustering techniques, particularly when dealing with heterogeneous data.
    
    **References**: 
    
    * Wang, F. et al. (2011). Improved K-Means Clustering Algorithm Based on Data Normalization. Journal of Software Engineering and Applications, 4(4), 265-270. doi:10.4236/jsea.2011.44030
    * Juszczak, P. (2015). The influence of normalization on clustering of data with high dimensionality. Journal of Medical Informatics & Technologies, 24(2), 79-84. doi:10.2478/jmit-2014-0010)

### Partitioning Around Medoids

Partitioning Around Medoids (PAM) is a non-hierarchical clustering method developed by Kaufman and Rousseeuw in 1987. PAM utilizes the concept of a centroid, which is the central point of a cluster. Unlike mean-based clustering methods (such as k-means), PAM uses medoids as centroids, which are actual objects within the cluster rather than mean points (Jankowski, 2020).

PAM has been extensively studied and applied in various fields, including biology, finance, engineering, and psychology, as evidenced by the research papers by Davari (2015), Mu (2017), and Kwong (2008). It is regarded as one of the simplest and most effective clustering methods, particularly for non-Gaussian, high-dimensional, or outlier-prone data, as presented by De Soete (1986), Kuo, Liang, and Liang (2013).

The PAM clustering is an iterative process, which involves several steps. 

* First, a predetermined number of clusters is chosen, and random objects are assigned to each cluster
* Then, a medoid is selected for each cluster, which is the object in the cluster with the minimum average dissimilarity to all other objects in the cluster
* Next, objects are assigned to clusters based on their dissimilarity to the medoid of each cluster
* A new iteration begins with a new choice of medoids for each cluster, and so on until the clusters no longer change.

PAM is often compared to k-means in terms of performance and results. According to several comparative studies, PAM is often considered superior to k-means in terms of cluster stability, robustness to outliers, and accuracy.

In conclusion, PAM is a popular and effective clustering method that relies on medoids to create clusters. This method is widely used in various research fields and offers an interesting alternative to the k-means method.

### Hierarchical Clustering

Hierarchical Clustering is a hierarchical clustering method that groups similar objects into successive clusters, forming a tree-like structure called a dendrogram (Jain, Murty, & Flynn 1999). Unlike non-hierarchical clustering methods such as k-means, Hierarchical Clustering does not require specifying a number of clusters in advance, but determines the number of clusters from the dendrogram structure.

There are two types of Hierarchical Clustering: 

* **Agglomerative**: The agglomerative algorithm starts by considering each object as a cluster and gradually merges the most similar clusters to form larger clusters.
* **Divisive**.  The divisive algorithm starts with all objects in a single cluster and gradually divides the cluster into smaller clusters by separating the least similar objects. 

One advantage of Hierarchical Clustering is that it provides a visualization of the cluster structure in the form of a dendrogram, which allows identifying the different levels of clusters and understanding the similarity between them. However, the algorithm can be costly in terms of computation, especially for large amounts of data.

Hierarchical Clustering is commonly used in various applications such as bioinformatics, customer segmentation, and document classification (Berkhin 2006). Hybrid approaches that combine the advantages of hierarchical and non-hierarchical clustering methods are also widely studied in the literature (Zhang, Ramakrishnan, Livny 1996).

In summary, Hierarchical Clustering is a useful clustering method for identifying the structure of clusters and determining the number of clusters from the dendrogram structure. It is widely used in various fields, but its computational cost should be considered for large datasets. Hybrid approaches that combine the advantages of hierarchical and non-hierarchical clustering methods are also worth exploring.

### Gaussian Mixture

The Gaussian Mixture is a clustering method that models each cluster as a multidimensional Gaussian probability distribution (McLachlan, Peel 2000). Unlike centroid-based clustering methods, the Gaussian Mixture allows for more flexible modeling of the data distribution by considering that each cluster can have a different distribution shape.

The Gaussian Mixture algorithm seeks to estimate the parameters of each cluster's Gaussian distribution, such as mean and covariance matrix, as well as the relative weights of each cluster in the model. The model parameters are estimated using an optimization method such as the EM (Expectation-Maximization) algorithm.

One of the advantages of Gaussian Mixture is its ability to model clusters with complex and non-spherical distribution shapes, which is often the case in real data. It is also possible to determine the optimal number of clusters using information criteria such as the Akaike criterion or the Bayes criterion.

The Gaussian Mixture is widely used in various applications such as pattern recognition, image segmentation, and data modeling for machine learning (Bishop 2006). However, as with any clustering method, the quality of the results heavily depends on the choice of algorithm, optimization method, and parameter selection.

## Supervised Methods: Optimal Number of Clusters Selection

!!! abstract "Methodes"
    The optimal number of clusters selection is a crucial step in clustering techniques. The methods presented here, the Elbow Method, the Silhouette Method, and the Gap Statistic, are scientific methods commonly used to determine the appropriate number of clusters and thus ensure an adequate representation of the data.

The selection of the appropriate number of clusters is crucial to achieve meaningful results, as too few or too many clusters can lead to oversimplification or overcomplication of the data structure. Different approaches can be used to determine the optimal number of clusters, such as visualization techniques, statistical methods, and performance evaluation metrics.

### Elbow Method

The Elbow Method is a scientific technique commonly used to determine the appropriate number of clusters. It involves plotting the explained variation of data points against the number of clusters. The decision rule for determining the appropriate number of clusters is based on selecting the angle of the elbow in the curve, which means finding a "break" in the elbow diagram. Although simple and quick, this method can be subjective and may not always work with complex or unstructured data (Jambu 2016).

### Silhouette Method

The Silhouette Method is another commonly used method for determining the optimal number of clusters. It is based on measuring the similarity of an object to its own cluster compared to the other clusters. This measure is based on the average distance of an object to the other clusters. The silhouette ranges from -1 to 1, where a high value indicates that the object is well-matched to its own cluster and poorly matched to the other clusters. If most objects have a high silhouette value, the clustering is considered well-done. On the other hand, if many objects have a low silhouette value, the clustering may have too few or too many clusters. The Silhouette Method provides a representation of how each object has been classified. This method is more objective than the Elbow Method, but it can be more computationally expensive.

### Gap Statistic

In the Gap Statistic method, the dispersion within the cluster, represented by $W$, is standardized by taking the logarithm of it and comparing it to its expected value under a null reference distribution of the data. The optimal number of clusters is then determined as the one that maximizes the Gap Statistic. This method allows for determining whether the clustering structure significantly deviates from a random uniform distribution. Although the Gap Statistic method is objective and robust for identifying the optimal number of clusters, it may be more challenging to implement than the preceding methods (Tibshirani, Walther, Hastie 2001).

## Clustering and Risk Parity

Asset allocation is a key issue in quantitative finance. The risk parity method is one of the most common approaches to balancing risks by assigning weights to assets in inverse proportion to their volatility. However, this method does not take into account the diversity and composition of the portfolio, which limits its effectiveness.

Clustering offers an alternative for portfolio management by:

* Simplifying management by dividing assets into groups
* Improving understanding of portfolio behavior in different market conditions
* Creating more diversified portfolios to reduce risk

Clustering can also improve the risk parity method by overcoming its limitations. By grouping assets into categories, this method can be applied to each group to build more diversified and market-resistant multi-asset portfolios. Studies have confirmed the effectiveness of this approach, including the one conducted by Meucci and Ardia in "Beyond Black-Litterman: Clustering and Improved Dynamic Portfolio Allocation" (2011), which demonstrated the effectiveness of clustering in constructing multi-asset portfolios with the risk parity method.

Risk parity method is used in combination with clustering. This method can help investors manage risk while maximizing their returns.

### Weighting Scheme

In the context of portfolio management using clustering techniques, it is essential to determine the appropriate weights to be assigned to the assets within each cluster. Different approaches can be considered for assigning weights, such as based on the assets' level of volatility, their contribution to the overall risk of the portfolio, or their historical performance.

#### Intra Cluster Risk Parity

The intra-cluster risk parity method (Roncalli, 2013) is a prevalent technique for assigning weights to assets. This method seeks to balance the risk across assets within a cluster by assigning weights based on their respective contributions to the overall volatility. As a result, this approach allows for the creation of multi-asset portfolios that are more diversified and more resistant to market changes within each cluster.

#### Markowitz Optimal Weighting

The Markowitz optimal weighting method (Markowitz, 1952) is another commonly used approach for weighting assets within a cluster. This method aims to maximize portfolio returns while minimizing risk. Consequently, this approach can be employed to assign weights to assets within each cluster in order to optimize portfolio performance.

#### Weighted Risk Parity

In addition, there are techniques that seek to merge the risk parity and Markowitz optimal weighting approaches to construct more diversified and performant multi-asset portfolios. One such method is the weighted risk parity method (Choueifaty and Froidure, 2012), which strives to balance both intra-cluster and inter-cluster risks by utilizing Markowitz optimal weighting for assets between clusters. By doing so, this method allows for the creation of multi-asset portfolios that are more diversified and able to withstand market changes both within and between clusters.

## Conclusion

Optimizing a portfolio requires integrating the clustering method with risk parity weighting. The clustering analysis allows us to group similar assets based on their risk characteristics. However, equal weighting should not be used within or between clusters. As a result, cluster weighting should be based on the risks associated with each cluster (Choueifaty and Coignard, 2008).

Nonetheless, clustering is not always an effective means of portfolio optimization, as it may not improve portfolio performance or the Sharpe ratio in all circumstances. In some instances, clustering may even lead to a greater weighting of underperforming assets. Rather than identifying outperforming assets, clustering should be used to manage risk effectively. It is a useful technique for determining the number of similar assets/strategies in the portfolio and for diversifying them efficiently. However, clustering algorithms should be used in conjunction with a return predictor, such as momentum, to select suitable assets for the portfolio (Roncalli, 2013).
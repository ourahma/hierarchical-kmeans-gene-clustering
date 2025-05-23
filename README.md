# Gene Clustering Analysis using Hierarchical and K-Means Methods

This project applies clustering techniques (Hierarchical Clustering and K-Means) to gene expression data. The objective is to identify groups of genes with similar expression patterns across individuals and compare the quality of the clusters using silhouette scores.

## Dataset

- The dataset contains gene expression values across **78 individuals** for **3229 genes**.
- Categorical columns like `"Gene Description"` and `"Gene Accession Number"` have been removed to focus on numerical data only.
- Source : [Kaggle](https://www.kaggle.com/datasets/crawford/gene-expression)

## Methods

### 1. Standardization
All features are standardized using `StandardScaler` to ensure zero mean and unit variance, which is essential for distance-based algorithms like clustering.

### 2. Hierarchical Clustering
- Performed using `scipy`'s `linkage` and `fcluster` methods.
- Dendrograms are plotted to visualize the structure.
- Silhouette plots and per-cluster silhouette scores are calculated to evaluate cluster cohesion.

### 3. K-Means Clustering
- The same standardized data is clustered using K-Means (`sklearn.cluster.KMeans`).
- The elbow method and silhouette score are used to determine optimal number of clusters.
- Cluster assignments and silhouette plots are generated.

### 4. Comparison
- Both methods are compared using global silhouette scores and per-cluster silhouette analysis.

```
Silhouette Score (Hiérarchique): 0.9379
Silhouette Score (KMeans): 0.9346
```
```
Davies-Bouldin (K-means): 0.4195393887197569
Davies-Bouldin (Hierarchical): 0.44330416555614544
```

| Aspect                  | K-Means (DB=0.419)              | Hierarchical (DB=0.443)          |
|-------------------------|----------------------------------|----------------------------------|
| **Algorithm Behavior**  | - Excels with spherical clusters <br>- Sensitive to initialization but achieved optimal results here | - Robust to initialization <br>- Naturally handles nested cluster structures |
| **Cluster Quality**     | - **Superior separation** (lower DB) <br>- Tight, well-defined clusters | - Slightly less compact clusters <br>- Still excellent performance |
| **Biological Relevance**| - Clear group separation suggests <br> meaningful biological patterns | - Dendrogram structure may reveal <br> additional hierarchical relationships |
| **Practical Guidance**  | **Preferred choice** when: <br>- Cluster shapes are spherical <br>- Computational speed is prioritized | Consider when: <br>- Exploring hierarchical relationships <br>- Cluster shapes are uncertain |

## Visualizations

- **Dendrograms** (Hierarchical and K-Means representations)
- **Silhouette plots** for both clustering algorithms

    - Hierarchical clustering : 
        ![](figs/1.png)

        **Dendrogramme**
        ![](figs/dendro.png)


    - K-means : 
        ![](figs/2.png)
- **Scatter plot after Clustering**

    ![](figs/scatter.png)



## Authors :

- **OURAHMA Maroua**
    - **Email:** [Email](mailto:marouaourahma@gmail.com)
    - **LinkedIn:** [Linkedin](www.linkedin.com/in/maroua-ourahma)
- **ANEJJAR Wiame**
- **AAMER Fadma**

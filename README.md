# K_Means_Clustering_for_Housing_Market

This code reads the training and test sets, created externally for a consistent evaluation of the examined methods, then creates $n$ clusters $\{C_i\}_{i=1}^n$ from the training data using the K-means algorithm with the usual Euclidean distance evaluated on the longitude and latitude coordinates of our dataframe.  

These implicitly create (closed) Voronoi cells
```math
K_n \triangleq \overline{
\left\{
x \in \mathbb{R}^d \mid \|\pi_2(x)- C_k\| \leq \|\pi_2(x)- C_j\|\; \text{for all}\; j \neq k
\right\}
},
```
where $\pi_2:\mathbb{R}^d \to \mathbb{R}^2$ is the canonical projection onto the first $2$ coordiates.  In our dataframe, the first two coordinates are the longitude and latitude data.  Here, it makes sense to cluster using Eucldiean distance, whereas it may not be as meaningfull for other entries.

This defines a parition of $\mathbb{R}^d$.  

The test data-set are then set in their respective Voronoi sells.

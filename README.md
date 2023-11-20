# machine_learning_project-unsupervised-learning

## Objective
The main goal of the project is to explore a wholesale customer data set and to cluster data using more than one method to determine the optimal number of obversations and to see which components contribute to the highest amount of changes.

## The Dataset
The data set for this project is a wholesale customer dataset where the data refers to the distributor's clients. It consists of entirely numerical data, and contains the following information:
- The region of the customers (Lisnon, Oporto or other)
- The channel, which is like the type of customer (hotel/restaurant/cafe or retail)
- Fresh products (annual spending in monetary units)
- Milk products (annual spending in monetary units)
- Grocery products (annual spending in monetary units)
- Detergents and paper products (annual spending in monetary units)
- Delicatessen products (annual spending in monetary units)

While all the data is numeric, the region and channel features are categorical and were treated as such. There were no null values, and outliers at the upper end were excluded during analysis as all the continuous data were heavily right-skewed. For modeling, the categorical data was left out, as using categorical data very heavily skews the clustering. After omitting the outliers and the categorical features, the data was scaled using the standard scaler.

For a detailed breakdown of the EDA, please refer to the Unsupervised Learning notebook file (Unsupervised Learning - Project.ipynb).

## Modeling

First an elbow plot was made using 20 clusters to determine the best number of clusters to use. The plot showed that two clusters would be best to use, even though there was a somewhat gradual decrease in the inertia rather than a sharp fall-off which would make the optimal number of clusters stand out more.

A K-means clustering model was fitted using two clusters, and while the centroids did show a large gap, the distribution of data points (which was made obvious once graphed) showed that separating the two wouldn't be as obvious, which would also explain the elbow plot.

A heirarchical clustering model was also fitted using the data, and the dendrogram also revealed the data can be partitioned into two clusters.

Lastly, carrying out a principal component analysis showed that three out of six components explained over 80% of the variance, with one component explaining roughly 50%, another explaining over 20% and the third explaining nearly 15%.

For detailed model evaluations, please refer to the Unsupervised Learning notebook file (Unsupervised Learning - Project.ipynb).

## Conclusion

Based on the EDA and modeling, the following conclusions can be made:
- A bulk of the orders tend to be within 10,000 m.u.
- Certain types of orders seem to be correlated to each other, such as groceries and milk, groceries and detergent/paper, and milk and detergent/paper. Delicatassen has some weak correlation with groceries, milk, fresh and frozen products
- Both the elbow method for K-means clustering and the dendrograms showed that two is the best number of clusters
- PCA component 1 explains nearly 50% of the variance, and component 2 explains over 20% of the variance



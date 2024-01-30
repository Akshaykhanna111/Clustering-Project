### Overview
This project focuses on building an unsupervised machine learning model using the "Wholesale Customers" dataset, which represents clients of a wholesale distributor. The dataset includes annual spending in monetary units (m.u.) on various product categories. The goal is to gain insights into customer segmentation and behavior.

### Dataset

- Fields:
- FRESH: Annual spending (m.u.) on fresh products (Continuous)
- MILK: Annual spending (m.u.) on milk products (Continuous)
- GROCERY: Annual spending (m.u.) on grocery products (Continuous)
- FROZEN: Annual spending (m.u.) on frozen products (Continuous)
- DETERGENTS_PAPER: Annual spending (m.u.) on detergents and paper products (Continuous)
- DELICATESSEN: Annual spending (m.u.) on delicatessen products (Continuous)
- Channel Categories:
	- Hotel/Restaurant/Cafe (Horeca): 1 (Represents customers in the hotel, restaurant, and cafe industry.)
	- Retail: 2 (Represents customers in the retail industry.)
- Region Categories: 
	- Lisbon: 1
	- Oporto: 2
	- Other: 3 (Represents customers located in regions other than Lisbon and Oporto.)


### Tools and Libraries

- Python, Pandas, NumPy, Seaborn, Matplotlib
- Scipy and Sklearn - KMeans and Hierarchical Clustering

### Exploratory Data Analysis (EDA)

- Checked summary statistics, missing values, and outliers.
- Created a grouping column for Region and Channel.
- Analyzed differences across groups for a comprehensive understanding.

#### Data Preprocessing

- Converted 'Channel' and 'Region' to categorical columns.
- Created a new column representing the combination of 'Region' and 'Channel'.
- Treated outliers by capping at 5th and 95th percentiles.

#### Analysis of Products

- Studied distribution, summary statistics, and outliers for each product across Region and Channel groups.
- Channel seems to largely dictating the variance in distribution across groups for following products - Fresh, Milk, Grocery, and Detergent Paper
- Identified key findings related to product distributions and correlations.
	- For channel 2
   
	-> All the products distribution is right skewed, but the tail size have reduced owing to outlier capping
	-> Strong correlation between following - 
	1. Grocery and Detergents_Paper
	2. Milk and Detergents_Paper
	3. Milk and Grocery
	
	For channel 1

	-> All the products distribution is right skewed, but the tail size have reduced owing to outlier capping
	-> Strong correlation between following - 
	1. Grocery and Detergents_Paper
	2. Milk and Grocery

### Dimensionality Reduction

- Applied PCA for dimensionality reduction.
- Chose the number of components based on the scree plot.
- Considered dropping highly correlated columns.

### Clustering

- Utilized K-Means clustering with 5 clusters based on the elbow method.
- Explored cluster profiles and customer segmentation.
- Evaluated the model using Hierarchical Clustering.

### Conclusion

The project aims to uncover patterns in customer behavior and group similar customers together. The clustering model provides insights into different customer segments, helping the wholesale distributor tailor strategies for improved customer satisfaction and business growth.

### Cluster Profiles 

#### Cluster 0:

- Channel: Retail (2)
- Region: Other (3)
- Spending Pattern:
    - Highest spending on Grocery and Detergents_Paper.
    - Moderate spending on Fresh and Milk.
    - Relatively lower spending on Frozen and Delicassen.
    - Highest count of records in this cluster, and hence more emphasis shall be laid to this cluster.

#### Cluster 1:

- Channel: Hotel/Restaurant/Cafe (1)
- Region: Other (3)
- Spending Pattern:
    - Extremely high spending on Fresh products.
    - Moderate spending on Frozen, Delicassen, and Grocery.
    - Low spending on Milk and Detergents_Paper.

#### Cluster 2:
- Channel: Hotel/Restaurant/Cafe (1)
- Region: Other (3)
- Spending Pattern:
    - Low to moderate spending across all product categories.
    - Slightly higher spending on Fresh products.
    - Lowest spending on Grocery and Detergents_Paper.

#### Cluster 3:
- Channel: Hotel/Restaurant/Cafe (1)
- Region: Oporto (2)
- Spending Pattern:
    - Moderate spending on Fresh and Grocery.
    - Relatively lower spending on Milk, Frozen, Detergents_Paper, and Delicassen.

#### Cluster 4:
- Channel: Retail (2)
- Region: Other (3)
- Spending Pattern:
    - Highest spending on Grocery, Milk, and Detergents_Paper.
    - Moderate spending on Fresh and Frozen.
    - Relatively lower spending on Delicassen.



These findings provide insights into the distinct spending patterns of each cluster, which can be valuable for tailoring marketing strategies, supply chain management, and customer relationship initiatives. Further analysis and actions can be taken based on these cluster profiles to optimize business operations and enhance customer satisfaction.

### Next Steps

- Further refine clustering by experimenting with different algorithms like DBSCAN
- Explore additional features or data sources to enhance segmentation.
- Implement the model in a real-world scenario and assess its effectiveness over time.

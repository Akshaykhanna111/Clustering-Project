### Overview
This project focuses on building an unsupervised machine learning model using the "Wholesale Customers" dataset, which represents clients of a wholesale distributor. The dataset includes annual spending in monetary units (m.u.) on various product categories. The goal is to gain insights into customer segmentation and behavior.

### Dataset
Kaggle Link For Data
Fields:
FRESH: Annual spending (m.u.) on fresh products (Continuous)
MILK: Annual spending (m.u.) on milk products (Continuous)
GROCERY: Annual spending (m.u.) on grocery products (Continuous)
FROZEN: Annual spending (m.u.) on frozen products (Continuous)
DETERGENTS_PAPER: Annual spending (m.u.) on detergents and paper products (Continuous)
DELICATESSEN: Annual spending (m.u.) on delicatessen products (Continuous)
Channel Categories:
	Hotel/Restaurant/Cafe (Horeca): 1 (Represents customers in the hotel, restaurant, and cafe industry.)
	Retail: 2 (Represents customers in the retail industry.)
Region Categories: 
	Lisbon: 1
	Oporto: 2
	Other: 3 (Represents customers located in regions other than Lisbon and Oporto.)


### Tools and Libraries
Python, Pandas, NumPy, Seaborn, Matplotlib
Scikit-learn, Imbalanced-learn, Joblib

### Exploratory Data Analysis (EDA)
Checked summary statistics, missing values, and outliers.
Created a grouping column for Region and Channel.
Analyzed differences across groups for a comprehensive understanding.

#### Data Preprocessing
Converted 'Channel' and 'Region' to categorical columns.
Created a new column representing the combination of 'Region' and 'Channel'.
Treated outliers by capping at 5th and 95th percentiles.

#### Analysis of Products
Studied distribution, summary statistics, and outliers for each product across Region and Channel groups.
Identified key findings related to product distributions and correlations.

### Dimensionality Reduction
Applied PCA for dimensionality reduction.
Chose the number of components based on the scree plot.
Considered dropping highly correlated columns.

### Clustering
Utilized K-Means clustering with 5 clusters based on the elbow method.
Explored cluster profiles and customer segmentation.
Evaluated the model using silhouette score.

### Conclusion
The project aims to uncover patterns in customer behavior and group similar customers together. The clustering model provides insights into different customer segments, helping the wholesale distributor tailor strategies for improved customer satisfaction and business growth.

### Next Steps
Further refine clustering by experimenting with different algorithms like DBSCAN
Explore additional features or data sources to enhance segmentation.
Implement the model in a real-world scenario and assess its effectiveness over time.
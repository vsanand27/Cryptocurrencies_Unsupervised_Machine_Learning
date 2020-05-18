# Cryptocurrencies_Unsupervised_Machine_Learning
Unveil data patterns and perform unsupervised machine learning models

# Purpose

Utilize Unsupervised machine learning to determine cryptocurrencies trading on the market and how cryptocurrencies could be grouped toward creating a classification for developing this new investment product.

Challenge File: https://github.com/vsanand27/Cryptocurrencies_Unsupervised_Machine_Learning/blob/master/CryptoCurrency_Challenge.ipynb

# Key Takeaways

A.	The datasets needed further cleansing specially TotalCoinsSupply. There were white spaces and multiple decimal in a value. This required further datacleansing. Exbibit A

B.	6 features were converted to 98 feature as we used get dummies function for evaluation.

C.	PCA is a statistical technique to speed up machine learning algorithms when the number of input features (or dimensions) is too high. PCA reduces the number of dimensions by transforming a large set of variables into a smaller one that contains most of the information in the original large set.we reduced 98 features to 3 main features.  See Exhibit A

D.	pca.explanation_ratio_ was very low between the three variable i.e. PC 1, PC 2, PC 3.  Variance is the square distance from each point from the center, added together, and divided by the total number of points. This tells us that is that the first principal component contains 2.7%, the second 2.13% and the third 2.05% of the variance. Together, PC1, PC2, & PC3 contain 6.88% of the information which is very low and does not represent dataset well.  

E.	Elbow curve showed us 4 cluster as a classification for developing the investment product.  However, Cluster#1 showed outlier dots.  Once you remove outliers.  I believe the results will improve and # number of cluster will be 3. See Exhibit B

F.	Build charts utilizing 2D hvplot and 3D plotly.express to analyze data show outliers in both class 1 and 2.  We need to remove outliers to get better clustering results. Exhibit C and D

# Recommendations:

1.	Further perform data cleansing to take out whitespaces and multiple decimals from a TotalCoins Supply feature values

2.	Look for a newer datasets and rerun the analysis.  The pca.explanation ratio was only 6.88% which does not represent crypto current well.

3.	Remove outliers to help improve cluster results from Cluster 1 “BITTORENT” coin and 1 data point from cluster 2 Turtle coin.

# Analysis
## A.	Pre-processing of data:
1)	Utilized dropped function to remove Crypto currencies not trading based on 
“IsTrading” feautre being false

2)	Revised dataframe to include only crypto currency where algorithm is not equal to Null

3)	Dropped IsTrading column from the dataset utilizing df.drop(columns)  function

4)	Removed null rows through the use of df.dropna function

5)	Revised dataframe to include only rows where TotalCoinsMined was greater than zero.

6)	Create new coin_name dataframe.  Note: There was 1 duplicate name but the index ticker was different.

7)	Dropped CoinName column using df.drop function

8)	For Unsupervised machine learning, utilized get.dummies function to change all values to numeric in the dataframe.  Note: The dataframe went from 6 to 98 features.

9)	Part of pre-processing the database, we also need to utilize StandardScaler to fit and transform dataset to features that are weight in an order for analysis 

# B.	Reducing Data Dimension using Principal Component Analysis (PCA)

PCA is a statistical technique to speed up machine learning algorithms when the number of input features (or dimensions) is too high. PCA reduces the number of dimensions by transforming a large set of variables into a smaller one that contains most of the information in the original large set.

## Exhibit A: Processed Data
![alt text]( https://github.com/vsanand27/Cryptocurrencies_Unsupervised_Machine_Learning/blob/master/Images/processed_data.PNG) 

# C.	Clustering Cryptocurrencies Using K-means

First we need to create Elbow diagram to see what are the best number of cluster required.  As you can see from Elbow image below that curve starts to flatten out a four.  So we used 4 cluster to create KMeans analysis that segregates the datframe data-set into four clusters.

## Exhibit B: Elbow Chart
![alt text]( https://github.com/vsanand27/Cryptocurrencies_Unsupervised_Machine_Learning/blob/master/Images/Elbow_Chart.PNG) 


Next assigned created KMeans cluster and created a dataframe that combines dataset from the original table, coin name and PC1, PC2 and PC3 with class field that categorizes datset into 4 cluster.

# D.	Visualization 

## Exhibit C: 3D Chart with Cluster
![alt text]( https://github.com/vsanand27/Cryptocurrencies_Unsupervised_Machine_Learning/blob/master/Images/3d_scatter_cluster.PNG)

## Exhibit D: 2D Chart with Clusters based on scaled data
![alt text]( https://github.com/vsanand27/Cryptocurrencies_Unsupervised_Machine_Learning/blob/master/Images/2d_scatter_cluster.PNG)

## Exhibit E: Hvplot Table
![alt text]( https://github.com/vsanand27/Cryptocurrencies_Unsupervised_Machine_Learning/blob/master/Images/hp-plot%20table.PNG) 

# End of file


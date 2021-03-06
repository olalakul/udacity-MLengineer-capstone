# Capstone Project

This is the 'Arvato' capstone project for Udacity Nanodegree 'Machine Learning engineer'

## Data

The following data files are provided by Udacity and are _not_ included in this repository

* Udacity_AZDIAS_052018.csv
* Udacity_CUSTOMERS_052018.csv
* Udacity_MAILOUT_052018_TRAIN.csv
* Udacity_MAILOUT_052018_TEST.csv

They should be stored at directory 'arvato_data'.
The same directory is used for storing intermediate data

##  Algorithm and Techniques

I start by analyzing the data and treating the missing  values.
Then I select variables that are the most important for the problem in hand.  For this purpose I will use azdias and customers datasets, formulate the problem as binary classification and use random forest for prediction. Random forest provides feature importance and identifies the top features. 
I visualize top-10 features and and compare their distribution for customer and  general population.

The I will make segmentation of general population based on the selected top variables. I will use one-hot encoding (OHE) for all features and apply a clustering algorithm. Before clustering it is desirable to perform dimensionality reduction. The widely known and used PCA is designed to work with  numerical, continuous data. In our case with categorical variables I consider it as not applicable and strongly oppose using it. The natural way of handling OHE data (or small integer data, like count data) originally comes from the area of text preprocessing - Latent Dirichlet Allocation (LDA). I use this method for dimensionality reduction and show that it also provides soft clustering. By using argmax soft clustering can always be converted to hard clustering.

For mail order problem I will use random forest as benchmark and feed-forward neural network as described above. 
I propose to build a feed-forward neural network for solving the binary classification problem. I will use sigmoid activation in the last layer and binary cross entropy as loss function. To handle categorical variables I will use 2-dimensional embedding for each variable. To handle ordinal variables I will use 1-dimensional embedding for each variable. This approach to handling the categorical and ordinal values is the main reason why I prefer neural network. 1- and 2-dimensional embeddings allow easy visualization of each embedding. This allows comparison of each embedding with our human understanding of the categories. 



## Software

This project uses

* numpy
* scipy
* pandas
* scikit-learn
* tensorflow (keras API)

For visualization

* matplotlib
* seaborn 
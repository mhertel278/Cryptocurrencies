# Cryptocurrencies

## Resources
    
Python 3.7.9, scikit=learn 0.24.1, jupyter notebook 6.1.4

## Overview

The purpose of this project was to take data about various types of cryptocurrency, dertermine which currencies are currently tradeable on the open market, and create a machine learning algorithm that could group the various currencies into classes.  I first preprocessed the data set.  I removed unecessary columns, dropped filtered to only cryptocurrencies currently being traded, converted text fields into numeric data to be ingestable by the machine learning model, and scaled the data with StandardScaler.

I then used PCA to reduce the dimensions of the data set to three principal components to prepare the data for clustering by K-Means.  I then calculated the inertia for the K-Means model for 1-10 clusters and plotted an Elbow Curve in order to determine the optimal number of clusters.

From the Elbow Curve I determined that 4 clusters would optimal, I fit the K-Means with 4 clusters to the data and predicted the classes.  I joined the predicted classes as a new column to the original dataframe to show the class for each currency.  I then used hvplot to create a 3d scatter plot visualizing the cryptocurrencies in the 4 clusters.

Additionally, I created a scatter plot using the TotalCoinsMined and TotalCoinsSupply columns of the final data set as the x and y axes, with Coin Name and Class in the hover data, to visualize the amount of each tradeable currency on the market.  In order to more easily visualize this data, I scaled the TotalCoinsMined and TotalCoinsSupply columns data with the MinMaxScaler.
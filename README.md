# Cryptocurrencies

## Background
Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data that will be worked with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what we are looking for, we has decided to use unsupervised learning. To group the cryptocurrencies, we decided on a clustering algorithm. we will use data visualizations to share her findings with the board.

## Tools used
- Pandas 3.6.15
- Numpy
- hvplot
- plotly
- sklearn

## Results
ETL was initially performed from data extracted from this crypto API https://min-api.cryptocompare.com/data/all/coinlist.
After cleaning up the data the following Data frame was used:

![Diliv1.1](https://github.com/Iffadanwar/Cryptocurrencies/blob/main/Images/Diliv1.1.png)

The coin names were used as the Index to this data frame. The algorithm indicates the technique used to code the currency. Prooftype indicates security used to encrypt the currency. TotalCoinsMined is the number of individual coins mined around the world. lastly, the Totalcoinsupply is the coins currently in circulation.

![Diliv1.2](https://github.com/Iffadanwar/Cryptocurrencies/blob/main/Images/Diliv1.2.png)

We then used get_dummies() command to qualify the TotalCoinsMIned and TotalCoinSupply so that they can be used in the clustering algorithm.

![Diliv1.3](https://github.com/Iffadanwar/Cryptocurrencies/blob/main/Images/Diliv1.3.png)

The values were then normalized using the StandardScaler().fit_transform() which uses a linear transformation to allow PCA processes to be done on the Data.

![Diliv2.1](https://github.com/Iffadanwar/Cryptocurrencies/blob/main/Images/Diliv2.1.png)

After performing Principal Component Analysis (PCA), we were able to create 3 Principal Components out of the data. This will be used to create a KMean Elbow curve to allow us to better understand how many clusters will be appropriate for the data.

![Diliv3.1](https://github.com/Iffadanwar/Cryptocurrencies/blob/main/Images/Diliv3.1.png)

After creating the elbow curve, we decided to use 4 clusters for our module. Due to the nature of elbow curves, the K values closest to the graph becoming horizontal will be the number of clusters adequate to perform this task.

![Diliv3.2](https://github.com/Iffadanwar/Cryptocurrencies/blob/main/Images/Diliv3.2.png)

Our findings were then added to our initial cleaned dataset to allow us to visualize the data using multiple ways and categorize each crypto currency by the level of risk.

![Diliv4.1](https://github.com/Iffadanwar/Cryptocurrencies/blob/main/Images/Diliv4.1.png)

First, a 3-D model was graphed to better show the spread of data points using the Principal Component as matrices.

![Diliv4.2](https://github.com/Iffadanwar/Cryptocurrencies/blob/main/Images/Diliv4.2.png)

The a table was created to better graph a scatter plot.

![Diliv4.3](https://github.com/Iffadanwar/Cryptocurrencies/blob/main/Images/Diliv4.3.png)

Lastly, a relational scatter plot was created to graph Total Coin Supply vs Total Coins Mined shows a loss of positive correlation.

## Summary

We provided the client with a list of cryptocurrencies being traded and classified them into 4 clusters. The clusters represent the different distribution of currencies totals mined vs total supply:
- High Total Mined, High Total Supply
- High Total Mined, low Total Supply
- low Total Mined, High Total Supply
- low Total Mined, low Total Supply

This information will allow our client to better decide what cryptos were more readily available to invest in and which are more sought after.

## Conclusions

- Bitcoin is in a class by itself. This is obvious in both the three-dimensional cluster modelling and the scatterplot. This is useful as Bitcoin can be studied as an exemplar.
- It would be very instrumental to run this analysis again without the Bitcoin data, to see if the elbow curve finds a different optimal cluster value and so that we can see the distribution of the data better in the three-dimensional plot. Essentially there are two classes, Bitcoin and all others.
- We can use these findings to compare all cryptocurrencies against Bitcoin and to re-run the unsupervised machine learning without Bitcoin to more fully understand the rest of the cryptocurrency market.

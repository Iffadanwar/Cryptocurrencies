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

# LSTM-Google-Stock-Prediction

This is an ongoing project as part of the UCSD Data Science Student Society(DS3) Projects Committee 2023. This project began with a dataset of historical S&P 500 data and even though the original goal was to develop a stock reccomendatoin system - i.e use AI and ML techniques to predict the stock movement of a given stock. Given this background, we appraoched it in 2 ways:

Financial Modelling
Scraping Twitter API for stock information - Sentiment Analysis of tweets as a prediction Feature
Modern Portfolio Theory

Since this is an ongoing project there are a lot more Machine Learning and Financial Models we would like to incorporate. We will be adding more to this repository as we improve our implementations

# 1) LSTM Google Stock Prediction

This model attempts to predict the Opening Price of Google Stock between March 10th to Aptil 14th 2023. As the graph in the project notebook suggests, our model is able to predict the GOOGL Stock Opening Price with a resonable level of accuracy  in terms of Price Movements. Our model seems to consistently overpredict by average of 3.04$ per day, with a maximum prediction error = 6$

However, LSTMs are not a good Model to use in Stock Prediction in general, and does not seem to be generally used in the Quantitative Analysis field. As a result, we will consider using "Modern Portfolio Theory" to better model the Stock performance along the lines of industry standards. 

# 2) Twitter Sentiment Analysis

As part of the project we were very interested in looking to see if we can use Social Media behaviour to predict the movement of a stock. Using the Twitter API v1. we were able to collect a dataset of Tweets that were discussing AAPL (Apple) Stocks. We were able to use the ZADER corpus and nltk python package to be able to correctly classify the tweets while taking into account Social-Media slang and euphemisms. 

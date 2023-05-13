# Winter23-Stock-Prediction-Project

This is an ongoing project that began as part of the UCSD Data Science Student Society (DS3) Projects Committee 2023.However, even though the project committee has concluded, I have continued to expand on the project by myself to try and improve my understanding of Financial Modelling, Machine Learning and Neural Networks. 

The original project started with a dataset of historical S&P 500 data and had a goal of building a 'Stock Recommendation System' - i.e use AI and ML models to predict the Opening Price movement of a given stock.


# Challenges:
As work on the project began, I realised that we had run into a few challenges:

## 1) Random Walk Hypothesis:
The Random Walk Hypothesis is a theory that suggests that the movement of prices of a financial asset, are unpredictable and follow a random pattern. In simpler terms, it proposes that future changes in the variable cannot be predicted based on past behavior or any other information.
Therefore, I realised early on that I would be unable to simply predict the behaviour of Stock Prices using ML Algorithms that I had previously implemeneted in the classroom. However, it was still true that large Hedge-Funds and Quantitative Analysts do use Machine Learning algorithms to develop stock predicition models. So there was still large scope for this project to expand and grow. 

## 2) Non Stationary:
Even though Stock Prices can be viewed as time-series data, we realise the price movements are Non-Stationary. This means that the distribution (mean and variance) of the data set changes over time. This makes it very difficult to develop a prediction model that is accurate and usable across any extended time period. 

# Solutions

## Method 1: LSTMs

Long Short-Term Memory (LSTM) networks are a type of RNN that can enhance the modeling of long-term dependencies. By incorporating memory cells and gating mechanisms, LSTMs can selectively 'remember' or 'forget' information, enabling them to capture and utilize long-range dependencies in sequential data.

In light of this, we attemped to overcome the problem of Non-Stationarity in our dataset by using an LSTM to predict the Opening Price of Google (GOOGL) stock between March 14th to Aptil 10th 2023. The project for this LSTM implementation can be found [here](https://github.com/Shrsht/Winter23-Stock-Prediction-Project/blob/main/twitter_scraper.ipynb). 

### Results:
As the graph in the project notebook suggests, our model was able to predict the GOOGL Stock Opening Price with a resonable level of accuracy, at least in terms of direction of Price Movements. Our model seems to consistently overpredict by an average of 3.04$ per day, with a maximum prediction error = 6$


<img width="763" alt="Screenshot 2023-05-13 at 3 24 33 PM" src="https://github.com/Shrsht/Winter23-Stock-Prediction-Project/assets/102553723/3ee56f7c-a97c-4f11-9d90-802515dd0ad9">

### Issues with LSTM Models:

Unfortunately,in spite of LSTMs being able to overcome the issue of Non-Stationarity, they are not a sufficiently good model to use in Stock Prediction. Simply because they do not resolve the issue of the **"Random Walk"** Hypothesis of Stock Prices. To put it simply, knowing previous stock price movement does not help very much in predictint the movement of stocks in the future. Even though LSTMs are really good at studying historical data and long-range dependancies, that is not particularly useful in Extrapolation to future stock price data. 

# Method 2: Twitter Sentiment Analysis

As part of the project we were very interested in looking to see if we can use Social Media behaviour to predict the movement of a stock. Using the Twitter API v1. we were able to collect a dataset of Tweets that were discussing AAPL (Apple) Stocks. We were able to use the ZADER corpus and nltk python package to be able to correctly classify the tweets while taking into account Social-Media slang and euphemisms. 

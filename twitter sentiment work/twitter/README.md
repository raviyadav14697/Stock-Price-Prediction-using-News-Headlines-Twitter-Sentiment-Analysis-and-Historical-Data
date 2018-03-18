# Twitter Sentiment Analysis for Stock Prediction
EECS 486 Winter 2017 Final Project by Group 8: Benjamin Rathi, Kevin Shah, Yashan Thakkar, Samidha Visai

***

### Description of Project:
We want to collect tweets for a company (given a stock ticker symbol) and perform a sentiment analysis on the tweets to see if one should buy the stock.
 
We do this by first finding the company's information, such as company name and other trademarked names, using a user input of a ticket symbol, and the Yahoo Finance API. From there, we collect tweets using the Twitter Search API. We then tokenize the text and score each tweet based on sentiment. The scores are normalized by length of the tweet and weighed by the number of followers the tweet's author has.

The sentiment and emoji dictionaries were compiled from two different sources. The emoji dictionary was obtained from previous research (kt.ijs.si/data/Emoji_sentiment_ranking/) and turned into a csv file. The sentiment library was collected from SentiWordNet (sentiwordnet.isti.cnr.it). These dictionaries contain a positivity and negativity score for each token. We use these scores when obtaining the sentiment value of a tweet.

Finally, the data included in this project are some tweets from 04/03/2017 to 04/10/2017 about five automotive industry stocks: GM, Tesla, Ford, Volkswagen, and Toyota.

***

##### File Manifest:
* app2.py
* demo.py
* EmojiSentiment.csv
* SentiWordNet.txt
* File directories containing tweets: ford, gm, toyota, tsla, volkswagen
* Excel sheet with stock price data: AutoStockData_4-3_4-10.xlsx

***

##### Datasets:
File directories of ford/, gm/, toyota/, tsla/, volkswagen/: Collection of tweets from 4/3/17 to 4/10/17 for Ford, GM, Toyota, Tesla, and Volkswagen

The files containing tweets need to be formatted as follows:
```sh
ID: [ID], [Tweet text, Number of followers]
Example: id: 849061127199870976 ,[u'Electric car maker Tesla, Inc. had a record quarter from January to March 2017, during which it both produced and... https://t.co/Ipoftmm3lM', 41649]
```

AutoStockData_4-3_4-10.xlsx: Financial data for each of the five auto stocks from 3/31/17 to 4/10/17, used to obtain percent change of each stock's price daily and weekly. The data was taken from Yahoo Finance, and has been slightly annotated for clarity and ease of analysis (i.e., rounding, percent change calculations, averages).

***

##### How To Use:
Install necessary packages using "pip install". Below, please find some packages you may need to install:
```sh
pip install unidecode
pip install schedule
pip install requests
pip install oauth2
```
##### Running Software:
To run it on any stock ticker using the most recent tweets, run 
```sh
python demo.py [INSERT STOCK TICKER]
Example: python demo.py goog
```

To run on collected tweets (of the five auto companies) run 
```sh
"python app2.py [INSERT NAME OF DIRECTORY CONTAINING TWEET FILES]/"
Example: python app2.py gm/
```

GITHUB REPO: https://github.com/iamyashan/EECS486project

***

##### Authors:
Benjamin Rathi, Kevin Shah, Yashan Thakkar, Samidha Visai

##### Acknowledgements:
We would like to thank Professor Rada Mihalcea, Michael Vander Lugt, Mathew Wiseman, and Zheng Wu for their guidance and support in EECS 486, Winter 2017. 



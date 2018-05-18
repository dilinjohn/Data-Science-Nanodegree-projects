Making use of Twitter API calls using tweepy for WeRateDogs Twitter account
----------------------------------------------------------------------------

In this project, I be using Tweepy to query Twitter's API for additional data beyond the data included in the WeRateDogs Twitter archive. This additional data will include retweet count and favorite count.

Tweet data is stored in JSON format by Twitter. The Twitter API is one that requires users to be authorized to use it, which involves setting up of some auth tokens which are described as below to create API object.

import tweepy

consumer_key = 'YOUR CONSUMER KEY'
consumer_secret = 'YOUR CONSUMER SECRET'
access_token = 'YOUR ACCESS TOKEN'
access_secret = 'YOUR ACCESS SECRET'

auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_secret)

api = tweepy.API(auth)

* Twitters rate limits are set to 15 minutes so as to limit the number of API calls to their servers

There are a couple of file created

1) twitter_archive_enhanced.csv - This is the WeRateDogs Twitter archive
2) tweet_json.txt - this stores the JSON data into a text file for the corresponding tweet id in the twitter archive.
3) image_predictions.tsv - The tweet image predictions, i.e., what breed of dog (or other object, animal, etc.) is present in each tweet according to a neural network. This data is downloaded using the 'Requests' library, following a URL hosted on Udacity servers
4) df_master.csv - this is the final .csv file that contains the cleaned data, which will be used for final analysis and projection
5) Wrange&analyze_twitter_data.ipynb - the Ipython notebook for EDA, data wrangling, asssesment and visualization, conclusions
6) wrangle_report.ipynb - Summary report

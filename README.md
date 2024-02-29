<img src = "https://th.bing.com/th/id/OIP.2LXwB7b0Ybp9-t_CkBBHwgHaD4?pid=ImgDet&rs=1" width = "1000"/>

<h1 align = 'center'>WeRateDogs Twitter Handle Analysis</h1>
<!-- <h2 align = 'center'>Updated: September 14</h2> -->

# Overview
- WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. The account was started in 2015 by college student Matt Nelson, and has received international media attention both for its popularity and for the attention drawn to social media copyright law when it was suspended by Twitter for breaking these aforementioned laws. [Read more]('https://en.wikipedia.org/wiki/WeRateDogs')

- The main objective of this project is data wrangling. In this project, I did web scraping using the Request library and Tweepy. I also performed little exploratory and explanatory analysis, found insights and suggested ways to increase tweet retweeting.


# Exploratory Analysis <sup>[1](wrangle_act.ipynb)</sup>
## Data Gathering:  
This project required gathering three data sets. The method used to gather each data was different and are as follows.

- Twitter archive file: This can be downloaded manually or programmatically with the use of the Request library

- The tweet image predictions: This can only be downloaded programmatically using the Request library because the file `image_predictions.tsv` is hosted on Udacity's servers and cannot be accessed manually.

- Tweets: Each tweet's retweet count and favorite ("like") count at minimum, and any additional data found to be interesting are scraped. This is done by:
    - Extracting the tweet IDs in the WeRateDogs Twitter archive and store in another file (tweet_id.txt)
    - Quering the Twitter API for each tweet's JSON data using Python's Tweepy library and store the data in another file (tweet_json.txt)

## Data Quality Issues

**In the `archive` table**
- Change the datatype for some of the columns e.g timestamp
- A lot of missing data in the features
- Missing values represented as `None`
- Expanded_url containing more than one url

**In the `image` table**
- Lowercase for P1, P2, and P3 sometimes
- Text column not properly formatted

**In the `tweet` table**
- Extract the date from Created_at column
- Rename the Created_at column as Timestamp to bridge uniformity

**Data Tidiness**
- P1, P2, and P3 should be formatted properly in the `image` table
- Remove html tags form the source column in the `archive` table
- Tweet_id in `archive` table duplicated in `image` and `tweet` tables

A new data set named 'twitter_archive_master' was produced by merging the three data sets named above, on tweet_id. [Read more]('wrangle_report.ipynb')



# Explanatory Analysis <sup>[2](act_report.ipynb)</sup>
## Insights
- Favorite count and retweet count has been found to reach their peaks in June. This can be rationally attributed to the fact that dog festival normally occur during this period. Followed by this month is January and December for favorite count and retweet count respectively. Third on the list is also December and January (respectively). This may be due to increased festive activities during the perionds
  
- Saturday usually has the highest favorite count  followed by Friday. This is probably due to less busy schedules on these days (weekend).

- Also, as expected, the correlation between favorite count and retweet count is, positively, very strong (0.86). Hence, favorite tweets are more likey to be retweeted.

- On the other hand, the correlation between the each feature (favorite count and retweet count) and numerator rating is and denominator rating is very weak, positive for the former and negative for the latter.

## Recommendations
- It is prefferable that posts are targeted on Fridays and Saturdays.
- Dog events should be hosted around June, December or January.
- Another factor should be used in predicting probability of retweeing as the numerator and denominator ratings are not effective.

# Resources
- [Wikipedia](https://en.wikipedia.org/wiki/WeRateDogs)

- [Python functions – Avoid repeating code](https://hub.packtpub.com/python-functions-avoid-repeating-code/)

- [Automate the boring stuff with python](https://automatetheboringstuff.com/)
- [W3school](https://www.w3schools.io/file/markdown-super-sub-script/)

## Access on
[![Kaggle Badge](https://img.shields.io/badge/-Kaggle-0e76a8?style=flat&labelColor=0e76a8&logo=dev.to&logoColor=white)](https://www.kaggle.com/code/nurudeenabdulsalaam/weratedogs-twitter-analysis)

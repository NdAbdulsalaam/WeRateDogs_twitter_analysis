## Introduction
> WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. The account was started in 2015 by college student Matt Nelson, and has received international media attention both for its popularity and for the attention drawn to social media copyright law when it was suspended by Twitter for breaking these aforementioned laws. [Read more]('https://en.wikipedia.org/wiki/WeRateDogs')

> The main aim of this project is centered on data wrangling. Although, little insights were explored. The raw datasets were then used to produce a master data that can be used for analysis.


## Exploratory Analysis
> This project make use of three data sets. The ‘twitter_archive_enhanced.csv’ which was downloaded directly from the ‘WeRateDogs’ twitter archive data, the ‘image_predictions.tsv’ that was downloaded from the tweet image prediction with the use of the request library, and lastly, the tweets using twitter API (tweepy). Data quality issues that were identified include:

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

**Data tidiness**
- P1, P2, and P3 should be formatted properly in the `image` table
- Remove html tags form the source column in the `archive` table
- Tweet_id in `archive` table duplicated in `image` and `tweet` tables

A new dataset named 'twitter_archive_master' was later genrated, by merging the datasets named above on tweet_id, after all the steps listed above were done. While uniformity of the column names is crucial for readability, it is also important to enable merging of the datasets. Note that the source link in the `archive` table was dimmed neccessary to be extracted from the html tag so as make it more humnan readable and loadable in the browser.
Although, not all the data quality and tideness issues were addressed (e.g melting the stages of the dog: `doggo`, `puppo`, `floofer ` and `pupper` should be in a single column), most all the important cleanings were done. [Read more]('wrangle_report.ipynb')



## Explanatory Analysis
> Favorite count and retweet count has been found to reach their peak in June. This can be rationally attributed to the fact that dog festival normally occur at the period. Followed by this month is the month of January for favorite count and December for retweet count. While the third month for the counts is the reverse of their second months (December and January respectively). This must have been due to the fact that months, January and December, are festive periods filled with holidays

> It was gathered from these insights that the day of the week that normally receive the highest favorite count is Saturday followed by Friday. This may be due to the fact that people will be less busy on these days (weekend). Therefore, it will be wise to target these days for tweet.

> Also, as expected, the correlation relationship between favorite count and retweet count is positive and close to 1 (0.86). That is, the higher the favorite count, the higher the retweet count and vice versa and that this correlation is so strong.

> However, the correlations between these features (favorite count and retweet count) with rating numerator and rating denominator are weak. They are positive for the former and negative for the later. [Read more]('act_report.ipynb')
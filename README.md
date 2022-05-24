# Project 3: Web APIs & NLP  Executive Summary

### Goals:
Use Pushshift.io API, collect data  from two subreddits of my choice (r/ApplyToCollege and r/gardening).
Use NLP to train a classifier model on which subreddit a given post came from.

### Process:
Data collection: Reddit and pushshift.io APIs
Data cleaning and EDA
Preprocessing and Modeling
Conclusions

### Data Collection:
Used pushshift.io APIs to  collect data on subreddit posts. We can collect post (submission) and comments of main post. After collecting both data, studied some of their features, I decided to use comments to compare these two subreddits. Because one subreddit has way more text than another. One drawback of comments might be that if we collect data from a hot post, the content may not represent the whole subreddit, but we can increase data size to avoid the problem.
 
### Data Cleaning and EDA
 Duplicate messages were dropped.  Words in the comments were lemmatized and stop words were removed. Preliminary EDA showed that of the 30 most frequent words in each class, approximately 1/5 were unique to the class and 4/5 were the same in both class

### Preprocessing and Modeling 
CountVectorizer and TfidfVectorizer were used to process and convert text data. The following modules with their accuracy scores:

CountVectorizer LogisticRegression on train: 0.9679046309032554 on test:0.875|

CountVectorizer RandomForestClassifieron train: 0.9917469050894085test on test 0.8255494505494505

CountVectorizer and MultinomialNB on train0.9504814305364512 on test 0.9107142857142857

TfidfVectorizer and  LogisticRegression on train 0.974782209995415 on test : 0.8873626373626373

TfidfVectorizer and RandomForestClassifier on train: 0.9917469050894085  on test_ 0.8214285714285714  

TfidfVectorizer and MultinomialNB on train: 0.9637780834479597  on test: 0.9107142857142857


### Conclusions
All models have pretty good performance on accuracy score, they all tend to overfit. In all these models,  I would recommend to use TfidfVectorizer and Multinomial Naive Bayes, because it has the best performance on test data.

Next step, I would like to perform sentiment analysis to find out if there are difference for the two groups. Study more words to add in stop words (to remove them when processing the data), more gridsearching to optimize models, include n-gram parameter in gridsearch, try more models 




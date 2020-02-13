# Sentiment-Analysis
This particular set of code carries out sentiment analysis on the tweets on our Honorable Prime Minister Narendra Modi using Tweepy and TextBlob.

To do this we first
* We fetch tweets through Twitter API, for which we need to Create an App and fetch the Consumer Key and Access details. Through this we get the access to a particular number of tweets about a particular person.
* As the tweets are in our hands, we carry out sentiment analysis by using [TextBlob](https://textblob.readthedocs.io/en/dev/quickstart.html#sentiment-analysis)

The Sentiments were asked to be classified into 

1.   Happy
2.   Neutral
3.   Unhappy
4.   Sad

Which was successfully done by the code: 

```
if analysis.sentiment.polarity > 0: 
            return 'happy'
        elif analysis.sentiment.polarity == 0: 
            return 'neutral'
        elif analysis.sentiment.polarity < 0 and analysis.sentiment.polarity > -0.25: 
            return 'unhappy'
        elif analysis.sentiment.polarity < -0.25: 
            return 'sad'
```
For selecting the person/ organisation whose tweets/related ones are to analysed can be done by chaning this code:
```
# calling function to get tweets 
    tweets = api.get_tweets(query = 'Narendra Modi', count = 300000) 
```
Here we have given the name = 'Narendra Modi' with analysis on 300,000 tweets!

### The Result:
Out of all the tweets scanned for its sentiments, there are: 

|Tweet Type| Percentage|
|-----|----|
|Happy tweets percentage| 29.09090909090909 %|
|Neutral tweets percentage| 58.18181818181818 %|
|Unhappy tweets percentage| 10.909090909090908 %|
|Sad tweets percentage| 1.8181818181818181 %|

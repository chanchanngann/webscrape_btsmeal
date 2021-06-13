# Social listening #btsmeal by webscraping IG data

### Background
The BTS Meal by McDonald, is definitely a hot topic around the world recently. Although I am not a BTS fan, the unprecedented levels of hype caught my attention. I am curious about the reactions from the BTS army (BTS fans) upon getting the limited-edition meal, that is the social media sentiment "online mood" towards the campaign/brand.

### Objective
__To find out the feedback on the #btsmeal campaign by discovering consumers' reactions on Instagram.__


### Questions
1. Any findings in the hashtags trend?
2. What are the emotions from BTS fans?
3. What are the most common topics (words) they would talk about?

### Steps
1. Webscrape Instagram data - the links of first 25 posts in #btsmeal hub and the post details (likes,comments,hashtags...)
2. Hashtags trend
3. Clean and export the data
4. Translate all the comments into English (a common language)
5. Detect the emotions from the comments and caculate the mean index
6. Build word cloud to show what people are talking about
7. Find out the most common words appearing in comments

I would refer the ones who posted on #btsmeal to be fans of BTS in this exercise.

*About The BTS Meal: The meal consists of 10 piece Chicken McNuggets, Cajun and Sweet Chili Sauces, Medium Fries and a Coke®.https://www.mcdonalds.com/us/en-us/bts-meal.html*

### More about Social Listening

Through social listening, you can also unearth trends among your industry, competitors, and consumer experiences. You can then make necessary changes to stay ahead of the curve and keep customers happy. (https://blog.sprinklr.com/difference-between-social-monitoring-and-social-listening/)

***
## Details

### Webscrape Instagram posts

First, we will create a function applying Selenium package to call the chrome browser to land on Instagram and search for the hashtag #btsmeal. Then we will extract the top 9 posts appearing in the #btsmeal hub and save the post details in a dataframe.

### Hashtags Trend

Except for the core #btsmeal tag,people usually tag #bts and #mcdonalds.

![](https://github.com/chanchanngann/webscrape_btsmeal/blob/master/images/01_hashtags.png)

### Export data

The webscraped data is ready for export.

![](https://github.com/chanchanngann/webscrape_btsmeal/blob/master/images/02_data.PNG)

### Translate the comments to English

Since the posts are extracted from around the world, comments are in different languages. We need to first translate the comments into a common language - English.
The google translator python package will do the job.

### Emotion analysis

After gathering all the comments from the posts, we can dive into each comment and find out what people are actaully talking about on #btsmeal. However, there are so many comments I would just focus on the overall emotions behind, wheather they feel happy or sad.

Text2emotion is a python package developed to find the appropriate emotions embedded in the text data. The pacakge can process the text and find the emotions embeded, then summarize into 5 categories: Happy, Angry, Surprise, Sad and Fear. Each emotion will be assigned by a score and the total score will add up to 1.

I will dig out the emotion scores from each post and calculate the average index.

![](https://github.com/chanchanngann/webscrape_btsmeal/blob/master/images/03_emotions.PNG)

![](https://github.com/chanchanngann/webscrape_btsmeal/blob/master/images/04_emotions_radar.png)

The major reaction was 'Surprise' among the fans while posting, followed by 'Happy'. I would consider the overall reaction to be positive among the fans (or the target audiences)

This is a good news to the brand since the positive social media sentiment denoted campaign success.

### Wordcloud

I am also curious about the topics (words) the fans usually talk about. I will use the NLTK library to trim down the comment passages into words and filter the words by eliminating the useless ones.

Then, I will visualize the words pattern that those fans are talking about using Wordcloud.

![](https://github.com/chanchanngann/webscrape_btsmeal/blob/master/images/05_wordcloud.png)

### Most common topics in comments

Using the NLTK library, we are able to get the frequency of each word. I will get 15 most common words by aggregating the post comments and plot out the graph for summary.

![](https://github.com/chanchanngann/webscrape_btsmeal/blob/master/images/06_mostcommonwords.png)

'bts', 'sauce','meal' are the most popular terms. Some terms are related to food such as 'chicken','eat','spicy','sweet'; some are related to the brand 'mcdonald' and 'bts'; Some are descriptive such as 'cute', 'limited','like'.

## Conclusion

In this exercise I tried to webscrape IG data and dig out the reactions among the BTS fans towards the #btsmeal campaign. The most common hashtags were #bts and #mcdonalds ; the major emotion was 'surprise'; the most mentionings in comments were 'bts','sauce'and 'meal'.

I found the overall response to be quite positive. This is a good news to the brand since positive social media sentiment denotes campaign success.

*References:*


- *Selenium doc: https://selenium-python.readthedocs.io/locating-elements.html#locating-elements-by-tag-name*
- *Selenium Tutorial: https://medium.com/analytics-vidhya/web-scraping-instagram-with-selenium-b6b1f27b885*
https://medium.com/swlh/tutorial-web-scraping-instagrams-most-precious-resource-corgis-235bf0389b0c*
- *Xpath: https://www.lambdatest.com/blog/complete-guide-for-using-xpath-in-selenium-with-examples/*
- *nltk tutorial: https://www.datacamp.com/community/tutorials/text-analytics-beginners-nltk*
- *text2emotion: https://towardsdatascience.com/text2emotion-python-package-to-detect-emotions-from-textual-data-b2e7b7ce1153*
*https://analyticsindiamag.com/social-media-monitoring-emotional-analysis-using-text2emotion-in-python/*
- *BTS meal: https://www.gq.com.au/lifestyle/food-wine/mcdonalds-bts-meal-is-creating-unprecedented-levels-of-deepfried-hype/news-story/97afb*
*https://www.koreaboo.com/lists/funniest-army-reactions-bts-meal-fails/*



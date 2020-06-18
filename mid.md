# A possible future application of word embeddings

We would like to use word embedding to discover the connection between people's willingness to invest / consume and the real economic cycle.


## Motivation

The economy goes through peaks and recessions. More specifically, there are four stages of the economy, namely, expansion, peak, contraction, and trough. One indicator of where we are in the economic cycle is the saving level. Saving level is strongly influenced by people's willingness to invest and consume. 

How to quantitatively measure the willingness? One possible way is to conduct sentiment analysis of comments on the future economic outlook. If the overall opinion towards the future economy is negative, theoretically people will be more inclined to saving instead of consuming.

Therefore, our analysis aims to exploit the connection between people's opinion on the future economic outlook and the real economic cycle.

A possible application of this study is that it can assist policymakers in predicting when the economic recession will end.

For example, Covid-19 has led many countries into the highest unemployment rate in centuries. Many, therefore, predict that there will be a fast increase in consumption after lockdown being released. However, there is no solid evidence to support it. Sentiment analysis can provide such proof. If society expects the recession to end and those unemployed can find occupation soon enough, they will tend to consume more as compensation for having to stay inside for such a long time. 



## Data
We need two sources of data: economic data and the textual data on which we can train and test our NLP model.

### Textual data on views

Due to differences in the timing and extent of infection in different countries, as well as the use of mainstream social medias in some countries, we need to distinguish between the location of the authors and obtain data from different software. For example, most Western countries use Twitter, Facebook, or Instagram as their main social platforms, while China uses Weibo as the main social platform.

So, based on our goal, we need to collect data separately by country. The data we need from social platforms are people’s views, post time, and geographical locations. We can find people’s views about COVID-19 by searching for tags on social platforms, such as “COVID-19”, “economy”, “unemployment rate”, etc., and use web scraping to get the content of the views, the time of post, and posters’ location from profile page if possible. Word embedding could help us to find location information from the content, because it breaks down the whole views into individual words, which can help us identify whether the word is in the geographic information we are looking for, as long as we set the geographic information in advance. If the content does not contain the geographic information we need, we could consider using the location from poster's profile.

### Economic data set
The national economy can be evaluated from different aspects. Under the certain context of Covid-19 we want to put more focus on the indexes like employment-to-population ratio. Except for the employment rate, some other indexes can also be taken into account such as GDP(Gross 

Domestic Product), CCI(Consumer Confidence Index) and CPI(Consumer Price Index). These data can be obtained from the government report as well as the employment report.   

Because of the uncertainty of time span, we may encounter situations where the indexes go through different calendar years. Some data may have the indexes seperated by quarter or months, if not we need to select the time span in order to make the indexes paralleled with the data collected from public opinion part.  .

When all the necessary data has been obtained, we may start to do some pre-processing of the data, we need to apply standardization approach in order to make sure the data is of the same scale.

To clearly identify the trend of public opinion and national economy, we can use line chart to demonstrate the trend in a vivid way. Comparisons may then be made to identify whether public opinion and national economy have correlation or not.




## Sentiment Analysis

After collecting the data, we need to analyze the sentiment score of people's view.
In order to identify whether the view is positive or negative, it is important to notice that the positive views contains positive adjective words such as ‘good’, ‘pleasant’  and adverbs like “very” good, meaning that the adjectives and adverbs are reliable features which can identify sentiment of the text. On the other hand, the negative words can be ‘sick’, ‘shocked’, and etc. It is also assumed that the positive views have only positive words, whereas the negative views contain only negative ones. However, it’s not always true to say that that people who have positive view will express only positive words. A sentence may comprise of various words with different sentiments, these words can be compared with others to be identified which one has more weight.

The base-line approach is lexicon-based as following:

    ``` If sentences contain positive words, which have more weight than overall negative words, this is classified as a positive review and vice versa. These collections of weights is called sentiment lexicons
    ```


A great example of such resource is  SocialSent developed by Stanford University. It is an opensource so anyone can use at  https://nlp.stanford.edu/projects/socialsent .

However, this does not work if language is more complicated and creative, i.e. each word means different thing in different possible contexts.






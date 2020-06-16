## Sentiment Analysis


In order to identify whether the view is positive or negative, it is important to notice that the positive views contains positive adjective words such as ‘good’, ‘pleasant’  and adverbs like “very” good, meaning that the adjectives and adverbs are reliable features which can identify sentiment of the text. On the other hand, the negative words can be ‘sick’, ‘shocked’, and etc. It is also assumed that the positive views have only positive words, whereas the negative views contain only negative ones. However, it’s not always true to say that that people who have positive view will express only positive words. A sentence may comprise of various words with different sentiments, these words can be compared with others to be identified which one has more wight.

The base-line approach is lexicon-based as following:

    ```
 If sentences contain positive words, which have more weight than overall negative words, this is classified as a positive review and vice versa. These collections of weights is called sentiment lexicons
    ```


A great example of such resource is  SocialSent developed by Stanford University. It is opensource so anyone can use at  https://nlp.stanford.edu/projects/socialsent .

However, this does not work if Language is more complicated creative, i.e. each word means different thing in different possible contexts.
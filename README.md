# Text Analytics Individual Project (MSBA 2020/21)

The project analysed the management discussions in the 10-K datasets. The project aimed to detect useful relationships between the management discussions and stock prices. The download process was done in Python and the analysis process, including data preparation, sentiment analysis, and topic modelling, was done in R. The result shows there is a significant relationship between the text and the stock prices. However, the correlation is trivial.

---

## Data collection and preparation

### Text preparation workflow

![圖片](https://user-images.githubusercontent.com/43996798/135534439-ea5349b6-04a2-4060-8488-9f0622837b8a.png)

The 10-K dataset was first downloaded using Python since the R API did not work. After that, I extracted management discussions from the downloaded documents. Then, only English text were kept. I also removed documents that is too short to be analysed. Besides, I extracted some features, such as readability, number of punctuations, and number of digits, from the documents. Finally, I used a Udpipe model to remove stopwords and tokenise the text into tokens.

---

## Sentiment Analysis

In this section, I calculated sentiment scores of the given documents. Then, I trained a regression with the sentiment scores and the stock prices to inspect their correlation. The correlation did exist significantly.

---

## Topic Modelling

In this part, I used unsupervised method "topic modelling" to find out the best number of topics among the documents. The optimal number of topics is 61. After that, the first 19 topics were kept while the others were dropped in order to reduce the complexity and dimension of the solution. Then, I labelled each documents with a topic and developed another regression model to predict the stock prices with topics. Eventually, I discovered that only 3 topics significantly affected the stock prices.

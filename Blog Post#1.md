# Blog Post#1 Introduction of project
Hi everyone, we are group from 2019 NLP Class and we are currently initiating our first project on American market sentimental factors analysis using what we learned from the class. We will post our progress here and this blog will be the first one mainly focusing on our idea initiating and preparation we made over the last weeks. 

In this blog, we will briefly introduce the following topics:
1. What are we doing
2. Inspirations from Academic
3. Potential data source 
4. Technical tools
5. Project timeline

## What are we doing

## Inspirations from Academic
We got our idea from an experiment on emotions from Terrance Odean (*Andrade, E., Odean, T., & Lin, S. (2016). Bubbling with Excitement: An Experiment. Review of Finance, 20(2), 447-466.*). Terrance Odean is one of the most famous scholars in behavioral finance area. In his paper, Odean found that investor emotion intertwined with stock market bubble. Odean reached his conclusion by simulation experiment. We will try to reach this by empirical methodology and real news data.

In our project we plan to use “Wayback Machine” to fetch historical news. We got this idea from a working paper from UC-Berkeley: *Chew, M., Puri, S., Sood, A., & Wearne, A. (2017). Using Natural Language Processing Techniques for Stock Return Predictions*.

## Potential data source 
We evaluated mainstream financial media from three dimensions: data accessibility, financial relevance and web-scraping difficulty. As we are focusing on Chinese stock market, so we include both English and Chinese websites. We decided to use Yahoo Finance, Market Watch and Reddit as our main data sources in English and use Snow Ball (Xueqiu), Sina Finance and East Money as our main Chinese data sources.

We believe that these medias are all influential mainstream media platform in finance field with smart investors and active stock community.

## Technical tools
For web scraping, we will use package Scrapy and Selenium. For preprocessing we plan to use the best Python Chinese word segmentation module-JIEBA to do tokenization in Chinese and remove noise by filtering extreme words, numbers, and etc. Then we do BoW and calculate similarity. We will do morphological similarity analysis using word2vec and semantic similarity analysis using Chinese open wordnet(COW). By Choosing 100 words that appear in ﬁnancial news frequently and also have speciﬁc sentiment as our label words, we try to construct our sentiment dictionary and calculate sentiment score.

For further analysis, we will try different variables such as market trend & individual stock, volume & return and try to find the connection between market crash and investors sentiment.

Lastly, our project also aims to construct a trading strategy that long high sentiment stocks and short low sentiment ones if any relationship is proven and compute key indicators: return, volatility, Sharpe ratio, maximum drawdown etc.

## Project timeline
Our project timeline is as follows and we will post our latest progress in the following blogs:

• Week #1: 

Data Collection & Pre-processing

• Week #2: 

Text Analysis & Senti-score Computation

• Week #3: 

Construct trading strategy & Wrap up final results

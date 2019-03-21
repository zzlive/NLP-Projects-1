# Blog Post#2 Progress report
Hi everyone, we are group from 2019 NLP Class and we are currently initiating our first project on American market sentimental factors analysis using what we learned from the class.

In this blog, we will briefly go through the following topics:
1. Review of Previous Session 
2. Our Progress So Far 
3. Web-scrapping
4. Data Pre-processing

## Review of Previous Session: 4 steps to forecast market trend
**STEP 1 Determine Target**
- According to the property of different stock markets, we choose a most suitable stock market to be our research target. And choose the right text pool(website) to provide ingredient.

**STEP 2 Web Scrapping**
- After we locate the right stock market and right text pool that we focus on, we then do web scrapping to gain data to be processed. 

**STEP 3 Natural Language Processing**
- Next, we integrate all the data and do nature language processing

**STEP 4 Forecast Stock Market Trend**
- Leveraging the big data and NLP, we can know what the attitude of majority in the stock market and analyze the economic trend according to our observation and theoretical framework.

## Our Progress So Far: where we have reached
**STEP 1 Determine Target**
- Choose S&P500, which is changeable due to our progress
- Choose Reddit as our targeted data source

**STEP 2 Web Scrapping**
- We did web-scrapping on Reddit and obtain the final result and do optimization as far as possible

**STEP 3 Natural Language Processing**
- Finished the pre-processing part
- Use machine learning to compute sentiment score

**STEP 4 Forecast Stock Market Trend**
- Finish the pre-processing part
- Visualization

## Web-scrapping
**Data Source:**
- We finally choose Reddit News as our data source. News title and timestamp are available on Reddit News from 2016/01 – 2019/02. The data size (number of news observation) is about 200,000 which is large enough for our research.
![avatar](https://github.com/zzlive/Pictures/blob/master/1.png)

**Get URLs from Wayback Machine:**
- The bigger the circle, the more snapshots.
![avatar](https://github.com/zzlive/Pictures/blob/master/2.png)
- There are 25 news in each snapshot.
![avatar](https://github.com/zzlive/Pictures/blob/master/3.png)
- What we do first is scraping the URLs of those snapshots. The tool we use here is Selenium.
![avatar](https://github.com/zzlive/Pictures/blob/master/4.png)
- What we get

    - 516 URLs for 2016
 
    - 4763 URLs for 2017
 
    - 4398 URLs for 2018
 
    - 451 URLs for 2019
    
![avatar](https://github.com/zzlive/Pictures/blob/master/5.png)

**Get news titles using URLs:**
- What we do next is scraping the news titles and timestamp. The tool we use here are request and Beautifulsoap.
![avatar](https://github.com/zzlive/Pictures/blob/master/6.png)

- What we get

  - 252558 observations in total.

  - 2016: 501 URLs succeed but 15 failed.

  - 2017: 4759 URLs succeed but 4 failed.

  - 2018: 4390 URLs succeed but 8 failed.

  - 2019: 451 URLs succeed but 0 failed.

![avatar](https://github.com/zzlive/Pictures/blob/master/7.png)

## Data Pre-processing
- Punctuation Mark
  - pattern = r',|\.|/|;|\'|`|\[|\]|<|>|\?|:|"|\{|\}|\~|!|@|#|\$|%|\^|&|\(|\)|-|=|\_|\+|，|。|、|；|‘|’|【|】|·|！|…|（|）’_str = re.sub(pattern, '', _str)
![avatar](https://github.com/zzlive/Pictures/blob/master/8.png)
![avatar](https://github.com/zzlive/Pictures/blob/master/9.png)

- Deal with special nouns
  -We sometimes get wrong tokenization when Wrong Tokenization & Wrong Format when dealing with special nouns. For example, when we tokenize this sentence: “Consumers won’t know meat origin after US ends labelling law.” The special noun ‘US’. 
![avatar](https://github.com/zzlive/Pictures/blob/master/10.png)

  -_str = [w for w in word_tokenize(_str.lower()) if w.isalpha
  
![avatar](https://github.com/zzlive/Pictures/blob/master/11.png)

  - _str = [w for w in word_tokenize(_str) if w.isalpha()]
  
![avatar](https://github.com/zzlive/Pictures/blob/master/12.png)

  - We solve the problem by ach sentence is analysed and tags are appended to nouns, verbs, etc. 
  
![avatar](https://github.com/zzlive/Pictures/blob/master/13.png)

- Deal with website address
  - When we encounter a website address, Regular Expression helps a lot. We use regex to find stuff in web links, parse email addresses, and remove unwanted characters.
![avatar](https://github.com/zzlive/Pictures/blob/master/14.png)
![avatar](https://github.com/zzlive/Pictures/blob/master/15.png)

- After cleaning, we still keep special nouns, but no URL, no wrong case. After that, we vectorize the document into Bow. 

![avatar](https://github.com/zzlive/Pictures/blob/master/16.png)
![avatar](https://github.com/zzlive/Pictures/blob/master/17.png)
![avatar](https://github.com/zzlive/Pictures/blob/master/18.png)

**Regression & Forecast**
-	Tokenize: Jieba. “Jieba” (Chinese for “to stutter”) Chinese text segmentation: built to be the best Python Chinese word segmentation module. Support three types of segmentation mode:
  -	Accurate Mode attempts to cut the sentence into the most accurate segmentations, which is suitable for text analysis.
  -	Full Mode gets all the possible words from the sentence. Fast but not accurate.
  -	Search Engine Mode, based on the Accurate Mode, attempts to cut long words into several short words, which can raise the recall rate. Suitable for search engines.
- Remove noise. If we think about some word as an unrelated variable for, it might actually be a good idea to remove this word from the text document because it just introduces unwanted noise.
- BoW model. The bag-of-words (BoW) model is probably the simplest way of converting text into numbers. The basic idea is to simply count the words in a given text document. If some words appear more frequently than others it might indicate that these words bear a particular significance for the meaning of this piece of text.
- Regression: Market: 2016-2019
  - S&P 500: Close price, Volume
  - VIX: volatility

![avatar](https://github.com/zzlive/Pictures/blob/master/19.png)
![avatar](https://github.com/zzlive/Pictures/blob/master/20.png)
![avatar](https://github.com/zzlive/Pictures/blob/master/21.png)

Thanks for your reading, and any comments and suggestions are warmly welcomed for discussion. See you :)

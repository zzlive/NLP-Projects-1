# Blog Post #3 Summary of our findings

Hi everyone, we are group from 2019 NLP Class and we are currently summarizing our project on market sentimental factors analysis using what we learned from the class. 

In this blog, we will briefly go through the following topics:
1. Some figures on what we did
2. Overview of our data
3. Regression and analysis 
4. Problems & Review
5. Conclusions

## Some figures
- News: We crawled over 250,000 news.
- Days: We covered over 1,000 days
- Codes: We had over 500+ codes

## Overview of our data
We first constructed a sentiment dictionary with 1,000 most common words. However, we should look to a Harvard sentiment dictionary inspired by Dr.Gao. We will check about that later on. Another picture is the property of our data set.
![avatar](https://github.com/zzlive/Pictures/blob/master/22.png)
![avatar](https://github.com/zzlive/Pictures/blob/master/23.png)

## Regression and analysis
We try to find out the relationship between sentiment score and news. We did simple Linear Regression at first, but the outcome is not significant. We then used some machine learning to work out, like Logistic, XGBoost and random forest. Among these models, we find the XGBoost Model fit our data most. We also tried different dataset and found the post data only looks good.
![avatar](https://github.com/zzlive/Pictures/blob/master/24.png)

## Problems & Review
- Data problems: Data pool is not large enough and there is an unreasonable Month Distribution of Samples.
  - We will redo the web-scraping and try Yahoo Finance source.
- We cannot forecast on continuous value
  - We will optimize construction approach of emotional score and try control variable in our model.

## Conclusions
- Bad news might not be able to move the whole market, unless it is financial crisis or 911.
- On the contrary, the movement of market might have the power to affect sentiment.

Thanks for your reading, and any comments and suggestions are warmly welcomed for discussion. See you :)

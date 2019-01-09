# Predictive-Model-of-Stomach-Ulcers


1. Introduction
2. Data Collecting
3. Data Cleaning
4. Feautre Engineering
5. Model Building


## Introduction

In this project, I built a predictive model using the dataset of 6,000,000 tweets from more than 3,000 twitter users. Besides mining information from the textual data inside the tweets, I also collected the 6 kinds of customize numerical information from each users who are suffering from stomach ulcers, including their follower, following, picture number and tweets amount. After data collection and cleaning, I split our original data into numerical and textual variables. For the numerical dataset, I utilized 10 different kinds of machine learning algorithms to build the classiﬁcation model, and tried cross validation and grid search methods to tune the hyperparameters in each function. In textual data part, I encoded all the tweets using TF-IDF methods to transfer the quantify text into numerical variables, then used one of the neural network model: Multi-layer perceptrons to do the analysis. Our results not only compared the accuracy of models based on different kinds of data source, but also selected out the best algorithm with its most suitable parameters setting when predicting the stomach ulcer disease.

## Data Collecting

There are two major Python packages we used here: One is called Selenium, while another is Beautiful Soup. 

Selenium is an open source tool which is used for automating the tests carried out on web browsers, which means it has the power to achieve automatic interaction with the webpage. Since Twitter is a dynamic website, each time when we jump into a new page, the earlier information is always hidden below the latest ones. Therefore you need use some tools to roll the webpage continuously and expand all the content you need. 

Beautiful Soup, another tool we used, is a python library that extract data from HTML and XML documents, which is a excellent option for navigating, searching, and modifying a parse tree. Beautiful Soup can solve this question easily thanks to its scraping logistic. 

[Data Collecting: User Filtering](https://github.com/ZihanChen1995/Predictive-Model-of-Stomach-Ulcers/blob/master/Data%20Collecting:%20User%20Filtering)

This is the script which helps us find the user who has the Stomach Ulcers, then we collect the data of these users.

[Data Collecting: User Info](https://github.com/ZihanChen1995/Predictive-Model-of-Stomach-Ulcers/blob/master/Data%20Collecting:%20User%20Info)

Using this script, we can follow the links we collected before, and then get all the customize infomarion from each user.


## Data Cleaning

[Data Cleaning](https://github.com/ZihanChen1995/Predictive-Model-of-Stomach-Ulcers/blob/master/Data%20Cleaning)

In this file, I used Pandas to clean the raw data we got from Twitter website. Here are the things I did:

1. Fill in the missing value by different methods. (Mean, Mode)
2. Change string into int. ('K' to 1,000, 'M' to 1,000,000, e.g.)
3. Split single coloumn into several parts, which are more meaningful.
4. Delete the value which contains useless information.
5. Clean the Stopwords, Punctation, Non-English words.
6. Transfer the same words in different tense or form. (eat, ate)
7. Detect the Outliers.

## Feautre Engineering

[Feature Engineering](https://github.com/ZihanChen1995/Predictive-Model-of-Stomach-Ulcers/blob/master/Feature%20Engineering)

I did these works in the stage of Feature Engineering:
1. Delete the outlier, based on the principle on standard deviation. (4 Standard Deviations from the Mean)
2. Use Min-Max Normalization to normalize the data
3. Choose the reliable features that we can use in our model, which means those features have high correlation with our target variable. (I used the Random Forest methods here, to get the score of each feature.)

## Model Building
[Model Building](https://github.com/ZihanChen1995/Predictive-Model-of-Stomach-Ulcers/blob/master/Model%20Building)

[Grid-Search](https://github.com/ZihanChen1995/Predictive-Model-of-Stomach-Ulcers/blob/master/Grid-Search:%20Hyper-Parameters)

Till now we have all the data that has been cleaned, including seven feature columns, and one target column called ”label”. Before we started our ﬁnal model building, here is a brief introduction of all the input features our model will use.

#### tweets: The number of tweets this user has 
#### following: The number of account this user is following 
#### followers: The number of follower for this user 
#### join time: The time period since this user started use Twitter 
#### picture: The number of pictures or videos this user has 
#### likes: How many likes this user received tweet con: Whole tweet content of 300 recent tweets 
#### label: Target Value. 1 means stomach ulcer, 0 means normal 


As we talked at the beginning, we used the ﬁrst six columns, which all contain numerical data, to build the classiﬁcation model, and the last feature column, tweet content, to build another model based on this textual information. Utilizing different data source and algorithms, we will compare the accuracy in the result part.

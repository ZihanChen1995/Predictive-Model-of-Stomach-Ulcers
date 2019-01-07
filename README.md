# Predictive-model-of-Stomach-Ulcer


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

Another tool we used, Beautiful Soup, is a python library that extract data from HTML and XML documents, which is a excellent option for navigating, searching, and modifying a parse tree. Beautiful Soup can solve this question easily thanks to its scraping logistic. 

[Data Collecting: User Filtering](https://github.com/ZihanChen1995/Predictive-Model-of-Stomach-Ulcers/blob/master/Data%20Collecting:%20User%20Filtering)
This is the script which helps us find the user who has the Stomach Ulcers, then we collect the data of these users.

[Data Collecting: User Info](https://github.com/ZihanChen1995/Predictive-Model-of-Stomach-Ulcers/blob/master/Data%20Collecting:%20User%20Info)
Using this script, we can follow the links we collected before, and then get all the customize infomarion from each user.


## Data Cleaning

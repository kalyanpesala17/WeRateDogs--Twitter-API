# WeRateDogs--Twitter-API
Project is part of a Udacity Data Analyst nanodegree. Focused on gathering data from various sources, assessing data issues, cleaning the data in tidy format for exploring and visualizing the key findings. 

## Introduction
In the following project I am going to gather and analyze data all around the Twitter account "WeRateDogs". For that, data is gathered via manual download, programmatical download and over an API. After that I am going to assess this data, define the issues found during the assessment and clean these issues to get a cleaned master dataframe for analyzing and visualizing the data.

## Data
- df_tweets : twitter archived data of WeRateDogs account.
- df_predictions : image predictions of dog breed 
- df_api : twitter API data 

<a id = 'assessingsum'></a>
## Assesing Summary

#### Quality
##### `df_tweets` table
- the datatype for the timestamps columns is object and should be datetime
- some of the dogs are not classified as one of dog stage categories("doggo", "floofer", "pupper" or "puppo") and contain all "None" instead
- some of the dog names are not correct (the,one, an, by, a, ...)
- contains retweets
- some of the ratings are not correctly extracted (mostly if there are more than one entries with the same format as rating) 
- some of the ratings are in decimals which are not correctly extracted to save the correct rating we have to convert rating_numerator data type from int to float
- the source column contains html code

##### `df_predictions` table
 - some words are starting with uppercase letters some are lowercase letters. convert everything in the same format
 - some predictions are not dog images
 - there are duplicate images in the data
 
##### `df_api` table
 - display_text_range is stored as two values in a list and data type is object. Since lower range is always 0 we can convert range to integer by removing lowerlimit and change the column name to be appropriate
 
#### Tidiness
##### `df_tweets` table
 - "doggo", "floofer", "pupper" and "puppo" columns should be reduced to one column as dog stage categories.
 
##### `df_predictions` table
 - p1,p2,p3 columns should be reduced to one column as predictions.
 - p1_conf,p2_conf,p3_conf columns should be reduced to one column as confidence.
 
##### `df_api` table
 - Merge this table with the twitter archive because data in the two tables are from same observation unit
 
 **Questions**

1. Which dog breed has more posts overall and each year?
2. Which dog breed has most favorite count in a single post overall and each year?
3. Is there any pattern between month of the year and number of posts?

# Recreational Activities Trends across World

This project is a powerful web application that helps the user compare you to others on many fronts in terms of recreation activities followed by people around the world. Recreation is part of any human life. All human beings need some break from their hectic schedule to spend time on activities they enjoy like music, sports, dance, watching television etc. This boost their energy multifold. 

As part of this project we have collected 130000+ instances of tweets across the globe using Twitter APIs in form of JSON file. The JSON(JavaScript Object Notation) data is one of lightweight data-interchange format. It is very easy to interpret by human beings as well as machines.

Now on top of this tweets we are analyzing various trends across the globe using Spark SQL.
We have designed meaningful queries to analyze various recreational activities people of various age groups choose and talk about, across the world by using twitter data
and designing meaningful queries. 

Some of the recreational activities we analyzed are as, we included:

- Sports, Extreme Sports
- Travel, Trips, Adventure, Theme Parks, National Parks
- Watching, Listen, Eating activities
- Dancing, Yoga, Gym ,Relaxation activities
- Hobbies such as poetry, collection, DIY etc. 

We particularly designed queries to analyze what all countries people involves in recreational activities and in turn revealing their work life balance. Also what all are the most popular activities, what king of age group they belong to, popular trending hashtags are part of this project.

## Architecture

Following is the software architecture for the project.

![Architecture](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/architecture.jpg)


## Requirements

- Operating System: Windows 10	

- IDE: Eclipse Neon 4.6.1

- Language: Java
                            
- Database: Apache Spark SQL

- Library: Apache Spark Core, Spark Ml lib, Spark SQL, Twitter4j, Sun Jersey
                           
- Public API: uClassify

- Visualization Charts: HighCharts.js, Google Geo Charts.js, d3.js

                           

## User Interface

**Snapshot:**

![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/Phase%203/HomeScreen.JPG)

## Queries

As part of this project, I have created one Java class to setup Spark Configuration and SQLContext. This class will be utilized in all further classes.

## Source code for this is shown below:

 ![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/Phase%202/SparkCOnf.JPG)


## Keywords to collect Tweets: 
 
 ![KeyWords](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/Phase%202/KeywordsList.java)



## Query1: Dataframe to return top countries
 
**Description:** It returns the top countries where people talk about recreation.
Numerous keywords related to sports, adventure, and activities were included to extract a large number of tweets.

Here the countries whose tweets are less than 100 will be considered as others.
And the countries whose tweets are more than 100 will be respective countries and union operation is performed with the former dataframe.

**Special features:** Dataframe , Union

**Output:**

![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/query1/query1countrywiseoutput.JPG)

**Visualization:**

![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/Phase%203/country.jpg)


## Query2: Dataframe to return top hashtags

**Description:**  This query returns the top hashtags people used in their tweets.
This query makes use of the hashtag file provided. It is basically join of hashtags from hashtag file plus tweets.

**Special features:** Dataframe , Join with another hashtags text file ,groupBy,orderBy

**Output:**
![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/query2/query2hashtagsoutput.JPG)

**Visualization:**
![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/Phase%203/hashtags.jpg)
 

## Query 3: Dataframe to call Public API to classify tweets based on age group
 
**Description:**  
For query 3, a public API “UClassify” is used in which tweet text is fed to API and it returns the age group to which  the user belongs who tweeted that particular text. Also this query is dynamically collecting tweets. As the uClassify calls have limitation, we have performed this query with 100 tweets. 

**Special features:** UDF, calling Public API

**UClassify JSON Response:**

 ![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/query3/uclassifyjsonresponse.JPG)

**Output:**

![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/query3/query3agegroupoutput.JPG)

**Visualization:**

 ![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/Phase%203/agegroup.jpg)


## Query 4: JAVA RDD query to get Top activities

**Description:**  This query will perform the map and reduce on tweets . It will get the top activities among all countries.

**Special features:**  Java RDD, mapToPair, reduceByKey, flatMap, sortBy, swap

**Output:**

 ![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/query4/query4popularwordsoutput.JPG)

**Visualization:**

![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/Phase%203/popularwords.JPG)
 


## Query 5: JAVA RDD query to classify Risky vs Non Risky Activities

**Description:**  This query will perform the map and reduce on tweets . It will classify the tweets based on people following risky activities like sky diving, jumping, kayak etc.

**Special features:** Java RDD, mapToPair, reduceByKey, flatMap

**Output:**
![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/query5/query5output.JPG)

**Visualization:**
![](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/Phase%203/riskyvsnonrisky.jpg)
 

## Report : 

[Project Report](https://github.com/bhandari-nitin/Analysing-Twitter-Tweets/blob/master/documentation/Phase%203/Phase%203/PB-Team%2018%20Phase%203.pdf)

## Ackwnowlegements

1. https://spark.apache.org/examples.html
2. https://www.javacodegeeks.com/2012/03/twitter-api-on-your-java-application.html

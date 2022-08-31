# What Makes a Movie Successful?
 
# IMDB Business-Problem
I have been hired to produce analyze IMDB's extensive publicly-available dataset, supplement it with financial data from TMDB's API, convert the raw data into a MySQL database, and then use that database for extracting insights and recommendations on how to make a successful movie.
I will use a combination of machine-learning-model-based insights and hypothesis testing to extract insights for our stakeholder.

**Specifications and Constraints:** 


* The stakeholder wants to focus on attributes of the movies themselves, vs the actors and directors connected to those movies.


* They only want to include information related to movies released in the United States.


* They also did not want to include movies released before the year 2000.


* The stakeholder is particularly interested in how the MPAA rating, genre(s), runtime, budget, and production companies influence movie revenue and user-ratings.
## Initial IMDB Data Processing
**IMDB Movie Metadata**

***
* I will download fresh movie metadata from IMDB's public datasets and filter out movies that meet the stakeholder's requirments/constraints. 

* IMDB Provides Several Files with varied information for Movies, TV Shows, and much more. 
    * Overview/Data Dictionary: https://www.imdb.com/interfaces/
    * Downloads page: https://datasets.imdbws.com/

* Files used: 
    * title.basics.tsv.gz
    * title.ratings.tsv.gz
    * title.akas.tsv.gz

## EDA Overview of Extracted Data From TMDB

* How many movies had at least some valid financial information (values > 0 for budget OR revenue)?

![image](https://user-images.githubusercontent.com/55251527/187796174-91d8cf07-73fa-47af-a176-ca075faea30d.png)


## What Years are represented?

![image](https://user-images.githubusercontent.com/55251527/187796253-db0fcbe8-a0dd-49f0-b5fc-4effbe5ebb48.png)

## Average Revenue By Year

![image](https://user-images.githubusercontent.com/55251527/187796295-ba116249-a289-4895-bf91-1fc12a5c8fb2.png)

## How many movies are there in each of the certification categories (G/PG/PG-13/R)?

![image](https://user-images.githubusercontent.com/55251527/187796327-57f49528-9475-44a4-a4c9-62c438da93ef.png)

## What is the average revenue per certification category?

![image](https://user-images.githubusercontent.com/55251527/187796354-de94c241-07db-41cb-a415-3f6b1aaf4939.png)

## What is the average budget per certification category?

![image](https://user-images.githubusercontent.com/55251527/187796379-52ac6a68-37df-45b8-ae36-ebca9129c869.png)

## What is the average ROI (%) for Movies with All Financial Data?

![image](https://user-images.githubusercontent.com/55251527/187796417-1c37404b-4e8b-4675-ae83-7870835871fa.png)

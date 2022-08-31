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


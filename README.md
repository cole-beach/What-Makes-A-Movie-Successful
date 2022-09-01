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

# MySQL Database

![image](https://user-images.githubusercontent.com/55251527/187797837-18012ed3-2860-4936-9e42-d7d31179179f.png)

# Hypothesis Testing

* $H_0$ *(Null Hypothesis)*: All MPAA ratings generate have equal average revenue.


* $H_A$ *(Alternative Hypothesis)*: Some MPAA ratings earn significantly more/less revenue than others.

**Selecting the Right Test**

* Numerical Data with more than 2 groups and we want **one** way ANOVA.

**ANOVA Assumptions**

* No signification outliers
* Normality
* Equal Variance

**Outliers**

![image](https://user-images.githubusercontent.com/55251527/187798419-396ec90a-1f8b-4e63-82e5-2734dbc8cc2a.png)

**Check for Normality**

![image](https://user-images.githubusercontent.com/55251527/187798506-386b7cc0-1d09-425e-926b-5180a5f0abe5.png)

* Didn't meet assumption of normality and current batch of data n is too small to disregard (for G movies).


* Do not need to test for equal variance, but will do so anyway, since it will not change my chosen test at this point. Additionally, more data is being extracted from the API and all group n's should increase in the near future.

## Checking for Equal Var

**LeveneResult(statistic=75.1307193499567, pvalue=2.2402973839869673e-75)**

* The groups do NOT have equal variance.

**KruskalResult(statistic=572.4484428432596, pvalue=1.8117464246224629e-121)**

*True

* Our Kruskal Wallis test returned a p-value <.0001.


* There is a significant difference in the average revenue for different movie certifications.


* A post-hoc test is needed to determine which ratings were different.

### Post-Hoc Tukey's Multiple Comparison

![image](https://user-images.githubusercontent.com/55251527/187798770-2d16a145-7c80-4b26-9ba8-b2104553fa6d.png)

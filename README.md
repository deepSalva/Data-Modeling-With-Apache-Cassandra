# Data Modeling with Apache Cassandra



This repository is a use case for designing and developing a Data Model for a **NoSQL** database with **Apache 
Cassandra**. The use case is based on an
imaginary music streaming startup, Sparkify, that wants to analyze the data they've been collecting on songs and 
user activity on their new music streaming app. The analysis team is particularly interested in understanding
what songs users are listening to. Currently, there is no easy way to query the data to generate the results, 
since the data reside in a directory of CSV files on user activity on the app.


We are performing the data engineer role, so we are tasked to create an Apache Cassandra database
which can create queries on song play data to answer the questions needed for the App. 
We'll test the database by running given queries by the analytics team from Sparkify.


The project is based on the project: Data Modeling in the Data Engineer course, Udacity.


Prerequisites:
* Python mid level
* NoSQL model basic understanding 
* Comfortable with SQL basic operations for database creation. 
* Basic data modeling, 3rd Normal Form, denormaliztion, etc... will be a plus

## Dataset

For this project, we'll be working with one dataset: event_data. The directory of CSV files partitioned by 
date. Here are examples of filepaths to two files in the dataset:

```commandline
event_data/2018-11-08-events.csv
event_data/2018-11-09-events.csv
```

## Project environment

This project is writen in Python using Jupyter notebook. 

### Necessary dependencies

1. iPython environment, such us conda or [Anaconda](https://docs.anaconda.com/anaconda/install/index.html)
2. [cassandra](https://anaconda.org/conda-forge/cassandra-driver)
3. pandas
4. numpy

The project runs as an iPython notebook without further installations or connections

## Project steps

Below are steps we followed to complete each component of this project.

1. Modeling NoSQL Apache Cassandra database:
   1. Design tables to answer the queries outlined in the project 
   2. Write Apache Cassandra `CREATE KEYSPACE` and `SET KEYSPACE` statements 
   3. Develop the `CREATE` statement for each of the tables to address each question 
   4. Load the data with `INSERT` statement for each of the tables 
   5. Include `IF NOT EXISTS` clauses in the `CREATE` statements to create tables only if the tables do not 
   already exist. We also include `DROP TABLE` statement for each table,
   this way we can run drop and create tables whenever we want to reset the database and test our 
   ETL pipeline 
   6. Test by running the proper select statements with the correct `WHERE` clause


2. Build ETL Pipeline
   1. Iterate through each event 
   file in `event_data` to process and create a new CSV file in Python 
   2. Include Apache Cassandra 
   `CREATE` and `INSERT` statements to load processed records into relevant tables in our data model 
   3. Test by running `SELECT` statements after running the queries on the database
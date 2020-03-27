# Udacity Data Engineer Nanodegree - Data Modeling with Postgres

## Create a Postgres database with tables designed to optimize queries on song play analysis

### Introduction

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

As a data engineer, I've created a Postgres database with tables designed to optimize queries on song play analysis. My role is to create a database schema and ETL pipeline for this analysis, test the database I created and ETL pipeline by running queries given to me by the analytics team from Sparkify and compare my results with their expected results.

### Files

1. [`test.ipynb`](test.ipynb) displays the first few rows of each table to check the database.
2. [`create_tables.py`](create_tables.py) drops and creates your tables. You run this file to reset your tables before each time you run your ETL scripts.
3. [`etl.ipynb`](etl.ipynb) reads and processes a single file from song_data and log_data and loads the data into your tables. This notebook contains detailed instructions on the ETL process for each of the tables.
4. [`etl.py`](etl.py) reads and processes files from song_data and log_data and loads them into your tables.
5. [`sql_queries.py`](sql_queries.py) contains all the SQL queries, and is imported into the last three files above.

### The Schema for the Song Play Analysis

Using the song and log datasets, I've created a star schema optimized for queries on song play analysis. This includes the following tables.

#### Fact Table

1. `songplays` - records in log data associated with song plays i.e. records with page NextSong
 - songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

#### Dimension Tables

1. `users` - users in the app
 - user_id, first_name, last_name, gender, level
2. `songs` - songs in the music database
 - song_id, title, artist_id, year, duration
3. `artists` - artists in the music database
 - rtist_id, name, location, latitude, longitude
4. `time` - timestamps of records in songplays broken down into the specific unit
 - `start_time`, hour, day, week, month, year, weekday

### Use
Remember to run [`create_tables.py`](create_tables.py) before running [`etl.py`](etl.py) to reset your tables. 
Run test.ipynb to confirm your records were successfully inserted into each table.

NOTE: You will not be able to run [`test.ipynb`](test.ipynb), [`etl.ipynb`](etl.ipynb), or [`etl.py`](etl.py) until you have run create_tables.py at least once to create the sparkifydb database, which these other files connect to.

Visit [my blog post](https://towardsdatascience.com/data-modeling-for-a-music-streaming-app-db46a4595e4e) to follow along

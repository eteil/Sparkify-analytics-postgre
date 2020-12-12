## Sparkify Music's Play Analytics

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to.

The purpose of this project is to extract datas from the songs and log files of Sparkify, transform them and load in tables organized in a star schema to meet their needs.

To do that we created 5 tables(1 fact tables and 4 dimensions):
- songplays(fact) to respond to track the activity of the users
- users to record users
- songs to record songs
- artists to record artists
- time to record the hour, date, etc. of the activities.

We first extract data from the songs files to load them in the songs and artists tables. After that we do the same from log files to load it in users, time and songplays tables.


### Structure of the project

#### Data

The data directory contains: 
- files of songs partitioned by the first three letters of each song's track ID and each file is in a JSON format.
- Files of log partitoned by the year and the month and are also in JSON format.

#### sql_queries

This file contains all the queries to drop, create, insert and select tables in the final database. There we have:
- DROP, CREATE, INSERT on  the songplays table.
- DROP, CREATE, INSERT, SELECT on  the songs table.
- DROP, CREATE, INSERT, SELECT on  the artists table.
- DROP, CREATE, INSERT on  the users table.
- DROP, CREATE, INSERT on  the time table.


#### etl.ipynb

Here we implement the whole process of the ETL on a subset of the data.

#### etl.py

This file is just as same as the etl.ipynb but it processes all data in the directory

#### create_tables.py

With this script we can drop and create the tables so that our database stay clean.


### How to run

To run the ETL, we need to:
- Create the tables with create_tables.py: `python create_tables.py`
- Run the ETL process with etl.py: `pyhton etl.py`




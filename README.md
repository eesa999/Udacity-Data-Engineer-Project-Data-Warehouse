# Cloud Data Warehouses

## Overview
In this project, we will work with Data Modeling with Redshift and build an ETL pipeline using Python.


## Project Files

```sql_queries.py``` -> contains sql queries for dropping and creating tables for fact and dimension . Also, contains insertion and copy queries.

```create_tables.py``` -> contains code for creating the fact and dimension tables.

```etl.py``` -> Python script to extract the needed information from Song and Log data inside the S3 buckets and parsing/inserting them to the created Redshift database schema and tables




# Schema

## Fact Table

songplays

```
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
```

## Dimension Tables

1- users

```
user_id, first_name, last_name, gender, level
```

2- songs

```
song_id, title, artist_id, year, duration
```

3- artists

```
artist_id, name, location, latitude, longitude
```

4- time

```
start_time, hour, day, week, month, year, weekday
```

## staging Tables

1- staging_events

```
artist   ,auth  ,firstName ,gender  ,itemInSession  ,lastName ,length  ,level  ,location  ,method  ,page  ,registration  ,sessionId  ,song  ,status int ,ts BIGINT ,userAgent  ,userId
```

2- staging_songs

```
songs ,artist_id ,artist_latitude ,artist_longitude ,artist_location ,artist_name ,song_id ,title ,duration ,year
```


# How to run the python scripts

First Fill we need to create the tables and run the ETL pipeline, you must run the following two files in the order that they are listed below

To create tables:
```bash
python3 create_tables.py
```
To fill tables via ETL:
```bash
python3 etl.py
```

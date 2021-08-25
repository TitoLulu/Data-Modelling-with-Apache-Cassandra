## Data modelling with Apache Cassandra
ETL Project for a fictional company SParkify; the ETL pipeline creates a database that allows analysis on song play data. 

Tables are modelled based on the following queries 
    1. artist, song title, and song length in music app history that was heard during sessionId = 338 and itemInSession = 4
    2. name of artist. song(filtered by item in session) and (first name and last name) for userId = 10 and sessionId = 182
    3. Every user name(first and last) who listened to the song "All Hands Against His Own"
    
## Approach 

Modelled tables based on queries Analytics teams are interested in. The tables created are:

*artists*

    |artist|song_title|song_length|sessionid|iteminsession|
    |:----------------------|:----------------|:-------|:--|:--|
    |Faithless Music Matters|(Mark Knight Dub)|495.3037|338|4|

*songs*

    |artist|song|iteminsession|user|userid|sessionid|
    |:-----|:---|:------------|:---|:-----|:--------|
    |Faith;ess Music Matters|All Hands Against His Own|4|Tito Magero|10|182|

*users*

    |user_name|song|
    |:--------|:---|
    |tito|All Hands Against His Own|
    
Created and set kespace *song_data* in which the tables above were created

Retrieved data from csv file in a folder called *event_data* then built a python ETL Pipeline to process and insert data from the csv file into the various tables. 

## References

-[REFERENCE #1](https://classroom.udacity.com/nanodegrees/nd027):**Data Engineering Nano Degree - Data Modelling with Apache Cassandra**

-[REFERENCE #2](https://stackoverflow.com/questions/46921455/cassandra-error-order-by-only-supported-when-partition-key-is-restricted-by-eq):**Partition Key Restriction on Order BY and GROUP BY operations**

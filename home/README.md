Data Modeling with Postgres

        Project Sparkify Database – Schema and ETL
        
Introduction

A Sparkify is a startup that wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they do not have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

Structure

The project contains the following elements:

                •data/ contains song and log files on user activity in JSON format
                •sql_queries.py All queries used in the ETL pipeline.
                •create_tables.py Clean previous schema and creates the Sparkify database and tables
                •etl.py Read JSON logs and JSON metadata and load the data into generated tables.
                •etl.ipynb and test.ipynb sketch out and test some of the elements contained in the Python scripts
Schema

The database contains the following fact table:

                •songplays: Records in log data associated with song plays
                •users: Users in the app
                •songs: Songs in music database
                •artists: Artists in music database
                •time: Timestamps of records in songplays broken down into specific units
 Instructions
 
To run the project in Udacity's Project Workspace, open IPython and enter the following:

    run create_tables.py
    run etl.py
    
Make sure your working directory is at the top-level of the project.

Query Example

Once you've created the database and run the ETL pipeline, you can test out some queries:

    %load_ext sql
    %sql postgresql://student:student@127.0.0.1/sparkifydb
    %sql SELECT * FROM songplays LIMIT 5;
    
There is also an example of what a single song file, TRAABJL12903CDCF1A.json, looks like.

    {
      "num_songs": 1,
      "artist_id": "ARJIE2Y1187B994AB7",
      "artist_latitude": null,
      "artist_longitude": null,
      "artist_location": "",
      "artist_name": "Line Renaud",
      "song_id": "SOUPIRU12A6D4FA1E1",
      "title": "Der Kleine Dompfaff",
      "duration": 152.92036,
      "year": 0
    }

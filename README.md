# data-modeling-with-postgres
## Context:

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app.

## Analytical goals:

The analytics team is particularly interested in understanding what songs users are listening to.

## Database schema design:

### Fact Table

1. **songplays** - records in log data associated with song plays i.e. records with page `NextSong`.

	* songplay\_id, start\_time, user\_id, level, song\_id, artist\_id, session\_id, location, user\_agent

### Dimension Tables

2. **users** - users in the app

	* user\_id, first\_name, last\_name, gender, level
	
3. **songs** - songs in music database
	* song\_id, title, artist\_id, year, duration

4. **artists** - artists in music database
	* artist_id, name, location, latitude, longitude
5. **time** - timestamps of records in songplays broken down into specific units
	* start\_time, hour, day, week, month, year, weekday

## ETL pipeline
run: `python etl.py` under the main directory.

The script will first transfer json files in `song_data` directory into `songs` and `artists` tables. 

Then it will transfer json files in `log_data` directiory into `time`, `users` and `songplays` tables.

## Sample code
In the main directory:

first run:
`python create_tables.py`

second run:
`python etl.py`

you should see

```
74 files found in data/song_data
1/74 files processed.
2/74 files processed.
3/74 files processed.
4/74 files processed.
5/74 files processed.
6/74 files processed.
...
```

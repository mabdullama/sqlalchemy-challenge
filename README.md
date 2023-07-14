# sqlalchemy-challenge

## Part 1: Analyze and Explore the Climate Data

In this section, you’ll use Python and SQLAlchemy to do a basic climate analysis and data exploration of your climate database. Specifically, you’ll use SQLAlchemy ORM queries, Pandas, and Matplotlib. To do so, complete the following steps:
1. Note that you’ll use the provided files (climate_starter.ipynb and hawaii.sqlite) to complete your climate analysis and data exploration.
2. Use the SQLAlchemy create_engine() function to connect to your SQLite database.
3. Use the SQLAlchemy automap_base() function to reflect your tables into classes, and then save references to the classes named station and measurement.
4. Link Python to the database by creating a SQLAlchemy session.
5. Perform a precipitation analysis and then a station analysis by completing the steps in the following two subsections.

### Precipitation Analysis

1. Find the most recent date in the dataset.
2. Using that date, get the previous 12 months of precipitation data by querying the previous 12 months of data.
3. Select only the "date" and "prcp" values.
4. Load the query results into a Pandas DataFrame. Explicitly set the column names.
5. Sort the DataFrame values by "date".
6. Plot the results by using the DataFrame plot method, as the following image shows:
![precitation](https://github.com/mabdullama/sqlalchemy-challenge/blob/main/SurfsUp/Output/precipitation.png)

7. Use Pandas to print the summary statistics for the precipitation data.

### Station Analysis

1. Design a query to calculate the total number of stations in the dataset.
2. Design a query to find the most-active stations (that is, the stations that have the most rows). To do so, complete the following steps:
3. List the stations and observation counts in descending order.
3. Design a query that calculates the lowest, highest, and average temperatures that filters on the most-active station id found in the previous query.
4. Design a query to get the previous 12 months of temperature observation (TOBS) data. To do so, complete the following steps:
	. Filter by the station that has the greatest number of observations.
	. Query the previous 12 months of TOBS data for that station.
	. Plot the results as a histogram with bins=12, as the following image shows:
![tobs histogram](https://github.com/mabdullama/sqlalchemy-challenge/blob/main/SurfsUp/Output/tobs.png)

5. Close your session.

## Part 2: Design Your Climate App

Now that you have completed your initial analysis, design a Flask API based on the queries that you have just developed.

Use FLASK to create your routes.
Routes

/

Home page.

List all routes that are available.

/api/v1.0/precipitation

Convert the query results to a Dictionary using date as the key and prcp as the value.

Return the JSON representation of your dictionary.

/api/v1.0/stations

Return a JSON list of stations from the dataset.
/api/v1.0/tobs

query for the dates and temperature observations from a year from the last data point.
Return a JSON list of Temperature Observations (tobs) for the previous year.
/api/v1.0/<start> and /api/v1.0/<start>/<end>

Return a JSON list of the minimum temperature, the average temperature, and the max temperature for a given start or start-end range.

When given the start only, calculate TMIN, TAVG, and TMAX for all dates greater than and equal to the start date.

When given the start and the end date, calculate the TMIN, TAVG, and TMAX for dates between the start and end date inclusive.

## Hints
    . Join the station and measurement tables for some of the queries.
    . Use the Flask jsonify function to convert your API data to a valid JSON response object.

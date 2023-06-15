# nosql-challenge
# UK Food Establishment Database Analysis

This repository contains the code and analysis for the UK Food Establishment Database.

## Contents

1. [Database and Jupyter Notebook Set Up](#database-and-jupyter-notebook-set-up)
2. [Update the Database](#update-the-database)
3. [Exploratory Analysis](#exploratory-analysis)

## Database and Jupyter Notebook Set Up

In this section, we set up the database and Jupyter Notebook environment.

1. Import the data provided in the `establishments.json` file into the `uk_food` database and `establishments` collection.

   Terminal command used for data import:

2. Import the necessary libraries: PyMongo and Pretty Print (pprint).

3. Create an instance of the Mongo Client.

4. Confirm that the database and collection were created successfully:
- List the databases in MongoDB to ensure `uk_food` is listed.
- List the collections in the `uk_food` database to ensure `establishments` is present.
- Find and display one document from the `establishments` collection using `find_one` and `pprint`.
- Assign the `establishments` collection to a variable for further use.

## Update the Database

In this section, we make the requested modifications to the database.

1. Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.

2. Update the new restaurant, "Penang Flavours," with the BusinessTypeID found in the previous step.

3. Check the number of documents containing the Dover Local Authority. Remove any establishments within the Dover Local Authority from the database and verify the deletion.

4. Convert the number values stored as strings to decimal numbers for latitude and longitude using `update_many`.

5. Convert the RatingValue to integer numbers using `update_many`.

## Exploratory Analysis

In this section, we perform an exploratory analysis on the UK Food Establishment Database.

1. Which establishments have a hygiene score equal to 20?
- Display the number of documents matching the query using `count_documents`.
- Display the first document in the results using `pprint`.
- Convert the result to a Pandas DataFrame, print the number of rows, and display the first 10 rows.

2. Which establishments in London have a RatingValue greater than or equal to 4?
- Use regex to search for establishments in London Local Authority.
- Display the number of documents matching the query using `count_documents`.
- Display the first document in the results using `pprint`.
- Convert the result to a Pandas DataFrame, print the number of rows, and display the first 10 rows.

3. What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
- Compare geocodes to find the nearest locations within 0.01 degree range.
- Display the number of documents matching the query using `count_documents`.
- Display the first document in the results using `pprint`.
- Convert the result to a Pandas DataFrame, print the number of rows, and display the first 10 rows.

4. How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest and print the top ten local authority areas.
- Display the number of documents matching the query for each Local Authority using `count_documents`.
- Sort the results in descending order and print the top ten local authority areas

#Refrence https://stackoverflow.com/questions/4973095/how-to-change-the-type-of-a-field , https://www.mongodb.com/docs/manual/reference/operator/aggregation/convert/?_ga=2.177953381.1797965468.1686169586-257113580.1685574371#std-label-convert-to-int

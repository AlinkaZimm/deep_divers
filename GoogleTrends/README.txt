Author: Alexandra Alinka Zimmermann
Date: 24.04.2022
Team: Deep-Divers
Project Name: Data-Driven Restaurants. How To Use Data to Create Attractive Menus?

Data Source: Google Trends API
Goal: To extract the food and diet preferences of the population in Switzerland.
Frequency: Data fetched every Sunday

1) Fetch & Load
First, the data was extracted from the Google Trends API and loaded as 6 CSV files into an S3 Bucket on AWS. 
The corresponding code is saved into the Python script: Fetch_Load_S3.py

2) Write Data into Tables
From the CSV files stored in the S3 Bucket, the data from the most recent CSV file of each of the 6 categories was written into its corresponding PostgreSQL table in the data lake. 
The corresponding code is saved into the Python script: Write_Data_Table.py

3) Validate Data in Tables
After that the data was written into the tables, a validation table was created for each of the 6 tables in the data lake. They validate that the correct number of data points were written into the tables. 
The corresponding code is saved into the Python script: tables_data_validation.py


Notes
To use my Python scripts:
Python version for the Lambda functions: 3.7

1) Create lambda function and an S3 Bucket.
2) Create an encrypted environment variable containing the name of the S3 Bucket.
3) Paste the code from Fetch_Load_S3.py into the function and adjust the Lambda function name to your chosen Lambda function name and your S3 Bucket name.
4) Deploy the changes and run the code.
The data will be then fetched and uploaded into the S3 bucket.

5) Create a PostgreSQL database.
6) Create another lambda function which will run the Python code to write the data into the tables.
7) Create environment variables for the S3 Bucket name, the database name, username, the password, and the database endpoint.
8) Paste the code from Write_Data_Table.py into the Lambda function and adjust the names of the environment variables to the ones you chose.
9) Deploy the changes and run the code.
The data will be written into the tables in the PostgreSQL database.

10) Create a last lambda function which will contain the Python code to validate the data that was written into the data tables
11) Create environment variables for the the database name, the username, the password, and the database endpoint.
12) Paste the code from tables_data_validation.py and adjust the names of the environment variables.
13) Deploy the changes and run the code.
The data will be validated and 6 additional tables will be created.
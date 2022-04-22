--> explain technicalities of your repository. (How to run your repo, files description, goals, authors etc.)

Date: 24.04.2022
Team: the Deep-Divers
Project Name: Data-Driven Restaurants. How To Use Data to Create Attractive Menus?
 
The authors of the files in this repository are: Ezgi Köker Gökgöl, Vithushan Mahendran, Alexandra Alinka Zimmermann. 

The project's data comes from 3 data sources: Google Trends API, Edamam API, the supermarket Coop Website. 
For each data source, the author extracted the data, transformed it and loaded it into a data lake.

1) Google Trends API (Alexandra Alinka Zimmermann):
Goal: To extract the food and diet preferences of the population in Switzerland.
Frequency: Every Sunday
1.1) Fetch & Load 
First, the data was extracted from the Google Trends API and loaded as 6 CSV files into an S3 Bucket on AWS. 
The corresponding code is saved into the Python script: Fetch_Load_S3.py
1.2) Write Data into Tables
From the CSV files stored in the S3 Bucket, the data from the most recent CSV file of each of the 6 categories was written into its corresponding table in the data lake. 
The corresponding code is saved into the Python script: Write_Data_Table.py
1.3) Validate Data in Tables
After that the data was written into the tables, a validation table was created for each of the 6 tables in the data lake. They validate that the correct number of data points were written into the tables. 
The corresponding code is saved into the Python script: tables_data_validation.py


* Edamam API

* Coop Website
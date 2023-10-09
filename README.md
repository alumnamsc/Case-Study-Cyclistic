# Trabajo-final-data-analysis
Case Study: How to Achieve Quick Success for a Bike Sharing Business?

### Scenery

I'm a junior data analyst working on the marketing analyst team at Cyclistic, a bike-sharing company in Chicago. The marketing director believes that the company's future success depends on maximizing the number of annual memberships. Therefore, my team wants to understand what differences exist in the use of Cyclistic bicycles between casual riders and annual members to design a new marketing strategy. 

### Characters and teams

● Cyclistic: A bike-sharing program that includes 5,800 bikes and 600 stations. Cyclistic stands out by also offering recumbent bikes, manual tricycles and cargo bikes that offer more inclusive use of bike sharing for people with disabilities and cyclists who cannot use a standard two-wheeled bicycle. Most cyclists choose traditional bicycles, around 8% of cyclists use assisted options. Cyclistic users are more likely to use their bike for recreation, but around 30% use it to commute to work each day.

● Lily Moreno: The marketing director and my manager. Moreno is responsible for developing campaigns and initiatives to promote the bike sharing program. Campaigns can include email, social media and other channels.

● Cyclistic Marketing Data Computational Analysis Team: A team of data analysts responsible for collecting, analyzing and reporting data that helps drive Cyclistic's marketing strategy. I joined this team six months ago and have dedicated myself not only to understanding Cyclistic's mission and business goals, but also to seeing how I can help Cyclistic achieve them, from my position as a junior data analyst.

● Cyclistic Executive Team: The highly detailed executive team will decide whether to approve the recommended marketing program.

### Ask

Three questions will guide the future marketing program:
1. How are annual members and casual riders different when it comes to using Cyclistic bikes?
2. Why would casual cyclists purchase Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual cyclists to become members?

### Task

Increase the number of annual memberships

### Data source

As it is a fictitious company, I used public data to explore how the types of customers who use Cyclistic bikes differ, between August 2022 and July 2023 (12 months). They have been provided by Motivate International Inc. under this license and can be downloaded at https://divvy-tripdata.s3.amazonaws.com/index.html.

### Prepare

It consists of 12 files (one file per month) with 13 columns each. Each column includes information such as the id of the rider, the type of bicycle used, the starting time, the ending time, the starting station, the ending station, the starting location, the ending location, and the type of user.
BigQuery was used to combine all the files into one database because it supports huge volumes of data.

### Data combined

12 cvs files were loaded into a dataset called cyclistics_trip_data. Then, the combined_data table was created, where there are combined the data of all the files. It contains 5,723,606 rows and 13 columns.

### Data exploration

•	There are six columns with null values, which are start_station_name, end_station_name, start_station_id, end_station_id, end_lat, end_lng. 

•	There are not duplicate rows.

•	All the ride_id have a length of 16.

•	The are three types of bikes: electric_bike, classic_bike y dokhed_bike

•	There are two types of riders: casual and member.

•	The start and the end time of the trip has YYYY-MM-DD hh:mm:ss UTC format. New column ride_length is created to inform the total trip duration. There are 153165 trips less than a minute and 5292 trips longer than a day. 

### Data Cleaning

•	All the rows having missing values are deleted.

•	Trips with duration less than a minute and longer than a day are excluded.

•	Rows were reduced from 5,723,606 to 4,249,346 (1,474,260 rows were removed)

### Analysis

The analysis question is: How do annual members and casual riders use Cyclistic bikes differently?
The data is stored appropriately and is now prepared for analysis. I queried multiple relevant tables for the analysis and visualized them in Tableau.

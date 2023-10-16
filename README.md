# Trabajo-final-data-analysis
Case Study: How to Achieve Quick Success for a Bike Sharing Business?

### Scenery

I am a junior data analyst. I work on the marketing analyst team at Cyclistic, a fictitious bike-sharing company in Chicago. The marketing director believes that the company's future success depends on maximizing the number of annual memberships. Therefore, my team wants to understand what differences exist in Cyclistic bicycle use between casual riders and annual members to design a new marketing strategy. 

### Characters and teams

● Cyclistic: A bike-sharing program that includes 5,800 bikes and 600 stations. Cyclistic stands out by also offering recumbent bikes, manual tricycles and cargo bikes that offer more inclusive use of bike sharing for people with disabilities and cyclists who cannot use a standard two-wheeled bicycle. Most cyclists choose traditional bicycles, and around 8% of cyclists use assisted options. Cyclistic users are more likely to use their bike for recreation, but around 30% use it to commute to work each day.

● Lily Moreno: The marketing director and my manager. Moreno is responsible for developing campaigns and initiatives to promote the bike-sharing program. Campaigns can include email, social media and other channels.

● Cyclistic Marketing Data Computational Analysis Team: A team of data analysts responsible for collecting, analyzing and reporting data that helps drive Cyclistic marketing strategy. I joined this team six months ago and have dedicated myself not only to understanding Cyclistic mission and business goals but also to seeing how I can help Cyclistic achieve them, from my position as a junior data analyst.

● Cyclistic Executive Team: The highly detailed executive team will decide whether to approve the recommended marketing program.

### Ask

Three questions will guide the future marketing program:
1. How are annual members and casual riders different when it comes to usage Cyclistic bikes?
2. Why would casual cyclists purchase Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual cyclists to become members?

### Task

Increase the number of annual memberships

### Data source

I used public data to explore how the types of customers who use Cyclistic bikes differ, between August 2022 and July 2023 (12 months). They have been provided by Motivate International Inc. under this license and can be downloaded at https://divvy-tripdata.s3.amazonaws.com/index.html.

### Prepare

It consists of 12 files (one file per month) with 13 columns each. Each column includes information such as the id of the rider, the type of bicycle used, the starting time, the ending time, the starting station, the ending station, the starting location, the ending location, and the type of user.
BigQuery was used to combine all the files into one database because it supports huge volumes of data.

### Data combined

12 cvs files were loaded into a dataset called cyclistics_trip_data. Then, the combined_data table was created, where there are combined the data of all the files. It contains 5,723,606 rows and 13 columns.

### Data exploration

•	There are six columns with null values, which are start_station_name, end_station_name, start_station_id, end_station_id, end_lat, end_lng. 

•	There are no duplicate rows.

•	All the ride_id have a length of 16.

•	The are three types of bikes: electric_bike, classic_bike and dokhed_bike

•	There are two types of riders: casual and member.

•	The start and the end time of the trip have YYYY-MM-DD hh:mm:ss UTC format. A new column ride_length is created to inform the total trip duration. There are 153165 trips less than a minute and 5292 trips longer than a day. 

### Data Cleaning

•	All the rows having missing values are deleted.

•	Trips with a duration of less than a minute and longer than a day are excluded.

•	Rows were reduced from 5,723,606 to 4,249,346 (1,474,260 rows were removed)

### Analysis

The analysis question is: How do annual members and casual riders use Cyclistic bikes differently?
The data is stored appropriately and is now prepared for analysis. I queried multiple relevant tables for the analysis and visualized them in Tableau.

The members make up 62,09% of the total while the remaining 37,91% constitutes casual riders.

![image](https://github.com/alumnamsc/Trabajo-final-data-analysis/assets/94757124/06f16e65-e2ab-40d4-966d-fca3444452f4)

The most used bike is the electric followed by the classic bike. Docked bikes are used the least and only by casual riders.

![image](https://github.com/alumnamsc/Trabajo-final-data-analysis/assets/94757124/b821ccec-61a0-4303-8166-2fd10c6d29a6)

![image](https://github.com/alumnamsc/Trabajo-final-data-analysis/assets/94757124/f5a5abb7-de32-4ee5-8278-4ad0a65c0fcf)

Next, the number of trips distributed by the months, days of the week and hours of the day are examined.
As a reminder, the first month is August because the data are from August 2022 to July 2023 (the last 12 months).

![image](https://github.com/alumnamsc/Trabajo-final-data-analysis/assets/94757124/0f00dd22-480c-4090-b1d6-f45e68bf8b8c)

Both casual and members have the same behavior. They have more trips in the spring and summer and fewer in the winter.
The difference in the number of trips seems to be constant, except in winter, when it is bigger. 

![image](https://github.com/alumnamsc/Trabajo-final-data-analysis/assets/94757124/015ef391-9e03-404b-bb94-8b7abaefd242)

Regarding the days of the week, it is discovered that casual riders make more trips on the weekends, with a peak on Saturday, while members show a decline from Thursday to Sunday. 
On no day of the week, total number of trips of casual riders exceeds the number of trips of members.

![image](https://github.com/alumnamsc/Trabajo-final-data-analysis/assets/94757124/d412b4a4-0854-4be1-8f85-0e290566e474)
 
Member’s trips have two peaks throughout the day. One at 8 a.m. and another one at 5 p.m.. 
Casual biker trips begin to increase without any significant peak until 5 p.m., when they reach their maximum and begin to decrease. Between 11 pm and 4 am the trend for each type of rider is similar.

![image](https://github.com/alumnamsc/Trabajo-final-data-analysis/assets/94757124/c83bdaeb-0a10-46e5-b3fe-b3605b9fd4dd)

The average Ride Duration on member riders ranges from 10 to 15 minutes throughout the year. While for casual riders it ranges approximately from 15 to 25 minutes, where the longer are on May and July. 

![image](https://github.com/alumnamsc/Trabajo-final-data-analysis/assets/94757124/0ce38ca2-eb8a-4332-b80e-6209be5b03e2)

Throughout the week, the average ride duration by casual bikers is longer than member bikers.
In both casual and member bikers, the average ride duration is longer on the weekend. 
The average on member bikers from Monday to Thursday is constant and then it increases but not significantly. It has the maximum peak on Saturday.
The average for casual bikers begins to decrease until it reaches its minimum peak on Wednesday. Then, it increases slightly until Sunday. 

![image](https://github.com/alumnamsc/Trabajo-final-data-analysis/assets/94757124/cea03966-7606-4199-aab2-71260e4584de)
 
As in the previous graphs, on member users, the average throughout the day doesn´t have significant variations. But on casual riders, the average decreases from 2 a.m. to 7 a.m. and it significantly increases from 7 a.m. to 11 a.m. 
Locations of starting and ending stations were analyzed too. To conclude, the stations with the most trips are considered.

![image](https://github.com/alumnamsc/Trabajo-final-data-analysis/assets/94757124/e2c67a90-0677-441b-8bb0-c1f56356ff68)

![image](https://github.com/alumnamsc/Trabajo-final-data-analysis/assets/94757124/e7c05cdc-25eb-45b1-a00a-319a0e87d366)
 
Casual riders start and end their trips at stations nearby to tourist attractions such as museums, parks, beaches, harbor points and aquariums. A large volume can be seen from Streeter Dr & Grand Ave Station,  where are located the Centennial Wheel, the Navy Pier and  the Chicago Children’s Museum.
On member riders, starting and ending stations are close to universities, residential areas, restaurants, hospitals, grocery stores, theatres, schools, banks, factories, train stations and parks.

### Conclusions

Casual users prefer using bikes throughout the day, more frequently over the weekends in summer and spring for recreational/tourist activities. On the other hand, members prefer to use bicycles during work/study hours, especially during arrival and leaving times (8 a.m. and 5 p.m.) in summer and spring (from March to September).

Members travel more frequently but the average ride duration is always lower than the casual riders.

### Act

Casual riders use Cyclistic only for recreational activities, so the company may be offered a temporary membership, either monthly, weekly or weekend. 

During the low season months (autumn and winter), a discount could be offered so that the difference in the number of trips is not so significant compared to the high season.

Casual travelers could be incentivized to obtain a temporary membership by giving them a discount for making trips with an average duration of 20 minutes or more.

Marketing campaigns should be realized in the spring/summer season in recreational/tourist places of the city since that is when the largest number of trips are made. They should be focused on the use of bicycles for daily use since this could reduce car traffic and pollution.


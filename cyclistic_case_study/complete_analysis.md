
## Table of Contents

1. [Introduction](complete_analysis.md#introduction)
2. [Business Task and Stakeholders](complete_analysis.md#business-task)
3. [Data: Collection and Preparation](complete_analysis.md#data)
4. [Data: Processing and Cleaning](complete_analysis.md#processing-and-cleaning)
5. [Analysis](complete_analysis.md#analysis)
6. [Summary and Recommendations](complete_analysis.md#summary)
7. [Conclusion](complete_analysis.md#conclusion)


## Introduction

 Chicago-based Cyclistic is a bike-share firm that provides full-access annual subscriptions and single-ride passes. A significant percentage of riders are casual users who buy single-ride or day passes, even though yearly members offer a more reliable source of income. The primary business goal is to increase annual memberships by converting casual riders into members.
 
## Business Task and Stakeholders

### Business Task:
To determine how casual riders and annual members use Cyclistic differently.

> **Goal**: The goal of this analysis is to identify key differences in riding behavior between casual riders and annual members and provide data-driven recommendations to help the marketing team develop strategies that encourage casual riders to become members.
The insights gained from this analysis will help Cyclistic’s marketing team develop targeted strategies to encourage casual riders to purchase annual memberships, increasing customer retention and revenue.

### Stakeholders:
1. Director of Marketing: Lily Moreno
2. Cyclistic Executive Team

### Key Business Questions:
1.	What are the usage patterns and riding behaviors of casual riders compared to annual members?  (e.g., trip duration, frequency, time of day, and station usage)
2.	When and where do casual riders use Cyclistic bikes the most? (e.g., peak hours, popular routes, and seasonal trends)
3.	What factors could influence casual riders to become members?
4.	What trend can help influence marketing strategies? 


## Data: Collection and Preparation
* **Source:**  [Cyclistic historical trip data](https://divvy-tripdata.s3.amazonaws.com/index.html) has been made available by Motivate International Inc. and has been protected under the data-privacy license mentioned here: [license](https://ride.divvybikes.com/data-license-agreement).
* The data range used for the purposes of this study and analysis was December 2023–November 2024.
* This publicly available dataset can be used for studying the usage of Cyclistic bikes by various customer types. We are unable to link pass purchases to credit card numbers since users are prohibited from using riders' personally identifiable information due to data privacy concerns.

### How is the data organized? 
* Each file has 13 columns, which are: ride_id, rideable_type, started_at, ended_at, start_station_name, end_station_name, start_station_id, end_station_id, start_lat, start_lng, end_lat, end_lng, member_casual
* ride_id is a unique rider ID and is used to identify each ride's data.
* rideable_type columns contain the type of bikes, such as electric bike and classic bike.
* started_at and ended_at columns contains date-time data and formatted as YYYY-MM-DD HH:MM:SS format.
* start_station_name, end_station_name, start_station_id, and end_station_id columns consists of station informations.
* start_lat, start_lng, end_lat, and end_lng, these columns contain latitude and longitude data.
* The member_casual column contains membership information, which is Member or Casual.


## Data: Processing and Cleaning

### Tools Used

-   SQL (sqlite, DB Browser): To process and clean data for further analysis

-   Microsoft Excel: To analyze and visualize data

### Cleaning and Transformation of Data

1.  All 12 months of data were uploaded to the SQL server and then combined into a full-year view using the following code:
```{sql eval=FALSE, include=FALSE}

CREATE TABLE full_year AS
SELECT * FROM "jan-tripdata"
UNION ALL
SELECT * FROM "feb-tripdata"
UNION ALL
SELECT * FROM "mar-tripdata"
UNION ALL
SELECT * FROM "apr-tripdata"
UNION ALL
SELECT * FROM "may-tripdata"
UNION ALL
SELECT * FROM "jun-tripdata"
UNION ALL
SELECT * FROM "jul-tripdata"
UNION ALL
SELECT * FROM "aug-tripdata"
UNION ALL
SELECT * FROM "sep-tripdata"
UNION ALL
SELECT * FROM "oct-tripdata"
UNION ALL
SELECT * FROM "nov-tripdata"
UNION ALL
SELECT * FROM "dec-tripdata";

```   
2. After joining the 12-month data, the COUNT() function was used to check the total row count of the aggregated dataset. There are 4244722 rows in this dataset.
![Image: row count](./screenshots/count.png)
3. 
4.  To assist in analysis, 2 new columns were added: ride_length (calculates the length of each ride) and day_of_week (calculates the day of the week each ride started.

## Analysis

## Summary and Recommendations

## Conclusion

# Bellabeat_Case_Study
Google Data Analytics Capstone Project
--SQL Queries 
--To validate user id length consistency 

Select LENGTH(CAST(Id AS STRING)) 
FROM bellabeat-378316.Bellabeat.Daily_Activity

Select 
Id
From bellabeat-378316.Bellabeat.Daily_Activity
WHERE LENGTH(CAST(Id AS STRING)) > 10

Select
 Id
From bellabeat-378316.Bellabeat.Daily_Activity
WHERE LENGTH(CAST(Id AS STRING)) < 10

Select
 Id
From bellabeat-378316.Bellabeat.Daily_Calories
WHERE LENGTH(CAST(Id AS STRING)) > 10

Select
 Id
From bellabeat-378316.Bellabeat.Daily_Calories
WHERE LENGTH(CAST(Id AS STRING)) < 10

Select
 Id
From bellabeat-378316.Bellabeat.Daily_Sleep
WHERE LENGTH(CAST(Id AS STRING)) > 10

Select
 Id
From bellabeat-378316.Bellabeat.Daily_Sleep
WHERE LENGTH(CAST(Id AS STRING)) < 10

Select
 Id
From bellabeat-378316.Bellabeat.Daily_Steps
WHERE LENGTH(CAST(Id AS STRING)) > 10

Select
 Id
From bellabeat-378316.Bellabeat.Daily_Steps
WHERE LENGTH(CAST(Id AS STRING)) < 10

Select
 Id
From bellabeat-378316.Bellabeat.Weight_Log
WHERE LENGTH(CAST(Id AS STRING)) > 10

Select
 Id
From bellabeat-378316.Bellabeat.Weight_Log
WHERE LENGTH(CAST(Id AS STRING)) < 10

--verify the number of users per table

Select
DISTINCT Id
FROM `bellabeat-378316.Bellabeat.Daily_Activity`
--33 users for this table

Select
DISTINCT Id
FROM `bellabeat-378316.Bellabeat.Daily_Calories`
--33 users for this table

Select
DISTINCT Id
FROM `bellabeat-378316.Bellabeat.Daily_Sleep`
--24 users for this table

Select
DISTINCT Id
FROM `bellabeat-378316.Bellabeat.Daily_Steps`
--33 users for this table

Select
DISTINCT Id
FROM `bellabeat-378316.Bellabeat.Weight_Log`
--8 users for this table

--left join to join all 5 tables by user ID’s
SELECT a.Id, AVG(a.TotalDistance) AS total_distance,
AVG(a.LoggedActivitiesDistance) AS logged_activity,
AVG(b.Calories) AS calories,
AVG(c.TotalMinutesAsleep)/60 AS avg_sleep_hours,
AVG(e.WeightPounds) AS avg_logged_weight,
AVG(d.Steptotal)/60 AS avg_sleep_hours,
FROM `bellabeat-378316.Bellabeat.Daily_Activity`
AS a LEFT JOIN `bellabeat-378316.Bellabeat.Daily_Calories`
 AS b ON a.Id = b.Id
 LEFT JOIN `bellabeat-378316.Bellabeat.Daily_Sleep`
 AS c ON a.Id = c.Id
 LEFT JOIN `bellabeat-378316.Bellabeat.Daily_Steps`
 AS d ON a.Id = d.Id
 LEFT JOIN `bellabeat-378316.Bellabeat.Weight_Log`
 AS e ON a.Id = e.Id
 GROUP BY a.Id;





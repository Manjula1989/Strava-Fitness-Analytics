STRAVA FITNESS DATA ANALYTICS
PROJECT REPORT

Smart-Device Fitness Data Analysis using Python, SQL and Streamlit
Project Element	Details
Dataset	Fitness / smart-device datasets including daily, hourly, sleep and weight data
Primary Tools	Python • Pandas • SQL / SQLite • Streamlit • Matplotlib / Seaborn
Primary Deliverable	Interactive Fitness Data Analytics Dashboard + SQL Analysis
Project Focus	Activity, steps, calories, intensity, hourly behaviour, sleep and weight
Prepared By	Manjula M
Date	29th September 2026
Github 	https://github.com/Manjula1989/-Strava-Fitness-Project-.git


 
Executive Summary
This project analyses smart-device fitness data to understand patterns in physical activity, steps, calories, activity intensity, hourly behaviour, sleep and weight. The objective is to transform raw fitness records into meaningful analytical insights that can support wellness product and marketing decisions.
Python and Pandas were used for data loading, preparation and exploratory analysis. SQL was used for data cleaning, aggregation and analytical queries. An interactive Streamlit application was developed with dashboard sections for overview, activity, calories and intensity, hourly analysis, sleep and weight, SQL analysis and data exploration.
The analysis identified useful patterns including average daily activity, activity-level segments, sleep behaviour and higher-activity hours. The dashboard also provides filters for date range and users and allows filtered datasets or SQL results to be downloaded.
Validated Analysis Snapshot
Metric	Result
Daily activity records	940
Hourly records	22,099 per hourly dataset
Sleep records	413
Weight records	67
Average daily steps	7,638
Average daily calories	2,304
Average sedentary time	991 minutes
Average very-active time	21.2 minutes
Average sleep	6.99 hours
Average time in bed	7.64 hours

STAGE 0 — Project Goal & Problem Statement
1. Project Goal
The goal is to analyse smart-device fitness data, clean and structure the supplied datasets, identify meaningful activity and wellness patterns, and communicate the results through an interactive dashboard and analytical outputs.
2. Business / Analytical Problem
Raw wearable and smart-device data contains activity, calorie, intensity, sleep and weight information across different time granularities. The challenge is to transform these records into clear insights that can help understand user behaviour and support data-driven wellness decisions.
3. Objectives
•	Clean and standardise the supplied fitness datasets.
•	Understand daily and hourly activity patterns.
•	Analyse steps, distance, calories and activity intensity.
•	Examine sleep and weight information where available.
•	Segment activity days into Low, Moderate and High activity groups.
•	Use SQL for cleaning, aggregation and analytical queries.
•	Create Python-based visualisations for exploratory analysis.
•	Build an interactive Streamlit dashboard.
•	Provide downloadable filtered data and SQL results.
•	Translate the analysis into practical business and wellness insights.
4. Role of Each Tool
Tool	Role in the Project
Python / Pandas	Data loading, cleaning, transformation and exploratory analysis
SQL / SQLite	Data cleaning, aggregation, joins, segmentation and analytical queries
Matplotlib / Seaborn	Static exploratory visualisations
Streamlit	Interactive dashboard, filters, SQL analysis and data explorer
Power BI / Tableau	Optional business-facing dashboard required by the case-study brief

STAGE 1 — Data Cleaning & Preparation
1. Dataset Structure
The project uses multiple fitness datasets covering daily activity, daily calories, daily intensities, daily steps, hourly calories, hourly intensities, hourly steps, sleep and weight.
Dataset	Records / Availability	Purpose
Daily Activity	940	Daily steps, distance, activity minutes and calories
Daily Calories	940	Daily calorie expenditure
Daily Intensities	940	Daily intensity information
Daily Steps	940	Daily step measurements
Hourly Calories	22,099	Hourly calorie patterns
Hourly Intensities	22,099	Hourly intensity patterns
Hourly Steps	22,099	Hourly step patterns
Sleep	413	Sleep duration and time in bed
Weight	67	Weight-related observations

2. Data Cleaning
•	Loaded the CSV datasets using Python/Pandas.
•	Converted date fields into consistent date/datetime formats.
•	Converted activity, distance, calorie and duration fields into numeric types.
•	Removed or excluded records where essential identifiers or dates were missing.
•	Created cleaned analytical structures for SQL queries.
•	Checked the resulting row counts and data explorer output.





3. SQL Cleaning Logic
The SQL workflow creates cleaned analytical views such as daily_activity. Identifiers are converted to integers, dates are parsed, and activity measures are cast to numeric types. Records with missing user IDs or activity dates are excluded from the cleaned view.
 
STAGE 2 — Data Description & Understanding
1. Descriptive Statistics / Initial Insights
Measure	Observed Result
Average steps/day	7,638
Average calories/day	2,304
Average sedentary time	991 minutes
Average very-active time	21.2 minutes
High-activity days	303
Moderate-activity days	334
Low-activity days	303
Average sleep	6.99 hours
Average time in bed	7.64 hours

2. Activity Segmentation
Daily activity was segmented using total steps: fewer than 5,000 steps was classified as Low, 5,000 to fewer than 10,000 steps as Moderate, and 10,000 or more steps as High.
Activity Segment	Days
Low	303
Moderate	334
High	303

3. Hourly Behaviour
The initial analysis identified 18:00, 19:00 and 17:00 as the top three hours by average recorded steps, with approximately 599, 583 and 550 average steps respectively.
STAGE 3 — Feature Engineering
Feature engineering was used to convert raw fitness fields into analytical variables that are easier to compare and visualise.
Derived Feature	Description
Activity Segment	Low / Moderate / High based on daily total steps
Sleep Hours	Minutes asleep converted into hours
Hour of Day	Extracted from hourly activity timestamps
Average Daily Steps	Mean steps across selected records/users
Average Daily Calories	Mean calories across selected records/users
Active Minutes	Activity duration fields used to understand intensity
Weekday	Derived from activity date for weekday comparisons

These engineered features support segmentation, weekday analysis, hourly analysis, sleep/activity comparison and dashboard filtering.
STAGE 4 — SQL Analysis & Analytical Modeling
1. Average Steps by Weekday
The SQL analysis groups cleaned daily activity by weekday and calculates average steps. This helps identify whether activity varies across the week.
 

2. Activity Segmentation
A CASE expression classifies each activity day as Low, Moderate or High based on total steps. The query then calculates the number of days and average steps/calories for each segment.
 
3. Sleep and Activity Relationship
Daily activity is joined with sleep records using user ID and date. The analysis compares average steps with average sleep hours for matched records.
 


4. Highest-Calorie Days
The SQL query orders daily activity by calories in descending order and returns the highest-calorie days for further inspection.
 
5. Analytical Modeling Approach
This project is primarily descriptive and diagnostic rather than predictive. The analytical model uses derived activity segments and aggregated measures rather than a machine-learning prediction model. Future predictive modelling is described separately in the Future Engineering section.
STAGE 5 — Python Visualisation & Exploratory Analysis
Python visualisations are used to communicate activity and wellness patterns before and alongside the interactive Streamlit dashboard.
Suggested Visual	Purpose
Average Steps by Weekday	Compare activity across weekdays
Activity Segment Distribution	Compare Low, Moderate and High activity days
Steps vs Calories	Explore the relationship between movement and calorie expenditure
Hourly Steps	Identify periods of higher recorded activity
Sleep Distribution	Understand variation in sleep duration
Activity Intensity Comparison	Compare active and sedentary behaviour
	

 
 
STAGE 6 — Streamlit Dashboard
The Streamlit application provides an interactive interface for exploring the fitness datasets. The sidebar contains dashboard navigation, date filtering and user selection.
Dashboard	Purpose
Overview	High-level KPIs and daily activity trend
Activity Analysis	Detailed activity and movement analysis
Calories & Intensity	Calories and intensity patterns
Hourly Analysis	Hourly activity behaviour
Sleep & Weight	Sleep and weight analysis
SQL Analysis	Interactive SQL queries and results
Data Explorer	Dataset selection, filtering and data download

6.1 Dynamic Filters
•	Date range filter
•	User selection filter
•	Dataset selection in Data Explorer
6.2 Dashboard Features
•	KPI cards for key fitness measures
•	Interactive charts
•	SQL query execution
•	Filtered data exploration
•	Download filtered dataset
•	Download SQL query results
6.3 Dashboard Validation
Test	Status
Dashboard navigation	Pass
Overview	Pass
Activity Analysis	Pass
Calories & Intensity	Pass
Hourly Analysis	Pass
Sleep & Weight	Pass
SQL Analysis	Pass
Data Explorer	Pass
Date range filter	Pass
User filter	Pass
Dataset selection	Pass
SQL execution	Pass
Download functionality	Pass

 
STAGE 6A — Dashboard Layout & User Experience
The dashboard follows a simple left-to-right and top-to-bottom reading path. Navigation and filters are placed in the sidebar, while KPIs, charts, analytical results and detailed records are displayed in the main content area.
The Data Explorer is particularly useful for validating filtered results because it displays the number of records and columns and provides a downloadable filtered dataset.
STAGE 7 — Insights & Storytelling
1. Daily Activity
Across the supplied daily activity records, average steps were approximately 7,638 per day and average calories were approximately 2,304 per day.
2. Activity Segmentation
The activity segmentation produced 303 Low-activity days, 334 Moderate-activity days and 303 High-activity days. The distribution is relatively balanced across the three defined segments.
3. Sedentary Behaviour
Average sedentary time was approximately 991 minutes per day, indicating that inactivity represents an important component of the observed daily behaviour.
4. Sleep
The supplied sleep records averaged approximately 6.99 hours asleep and 7.64 hours in bed.
5. Peak Activity Hours
The initial hourly analysis identified 18:00, 19:00 and 17:00 as the top three hours by average recorded steps. These periods can be examined further when considering user engagement timing.
Plain-Language Insight Cards
Insight	Finding
Insight 1	Average daily movement was about 7,638 steps, with activity spread across Low, Moderate and High segments.
Insight 2	Sedentary behaviour was substantial, averaging about 991 minutes per day.
Insight 3	Evening hours around 17:00–19:00 showed higher average recorded steps in the hourly analysis.

Business / Wellness Recommendations
•	Use activity reminders and challenges to encourage consistent daily movement.
•	Consider engagement messages around periods of higher recorded activity, especially the evening activity window identified in the analysis.
•	Use sleep and activity information together to provide more complete wellness insights.
•	Provide users with activity-segment feedback so that progress can be tracked over time.
•	Use the dashboard's user and date filters to support more personalised analysis.
STAGE 8 — Data Availability, Limitations & Interpretation
•	The analysis is descriptive of the supplied smart-device dataset and should not automatically be generalised to all users.
•	Not every dataset contains the same number of records; for example, sleep and weight records are fewer than daily activity records.
•	Device-recorded activity may not capture every form of physical activity.
•	Observed relationships between sleep, activity and calories should not automatically be interpreted as causal relationships.
•	The analysis is based on historical supplied data rather than a live wearable-data stream.
STAGE 9 — Future Engineering
The current project provides a strong descriptive analytics foundation. The following enhancements could be implemented in a future production version:
•	Predictive models to forecast activity or calorie trends.
•	Personalised activity recommendations based on user history.
•	Sleep-quality prediction and wellness alerts.
•	Automated ETL pipelines for continuously ingesting wearable data.
•	Cloud deployment with a production database.
•	Real-time integration with wearable or smart-device APIs.
•	Advanced user segmentation using clustering techniques.
•	Automated anomaly detection for unusual activity or sleep patterns.
•	Role-based access and production-grade monitoring for a deployed application.
Conclusion
This project demonstrates an end-to-end fitness analytics workflow using Python, SQL and Streamlit. The supplied smart-device datasets were cleaned and transformed into analytical structures, SQL was used for structured analysis, and an interactive dashboard was created to allow users to explore fitness behaviour through filters and multiple analytical views.
The analysis highlights daily activity, calories, intensity, sedentary behaviour, sleep and hourly patterns. The project can be extended into predictive and personalised wellness analytics through future feature engineering, machine learning and real-time data integration.
Final Submission Checklist
•	Python project files saved and reproducible.
•	CSV/data files included or referenced correctly.
•	SQL analysis file saved.
•	Streamlit dashboard tested.
•	All dashboard radio buttons/navigation options tested.
•	Date and user filters tested.
•	Data Explorer tested.
•	SQL queries tested.
•	Download functionality tested.
•	Python visualisation screenshots inserted.
•	Final Streamlit screenshots inserted.
•	Power BI/Tableau dashboard included if required by the case-study brief.
•	Project video recorded.
•	Word report reviewed and formatted.
Appendix A — Key Analytical Fields
Field Group	Examples
Identity	Id / User ID
Date / Time	ActivityDate, hourly timestamps
Activity	TotalSteps, TotalDistance, TrackerDistance
Intensity	VeryActiveDistance, ModeratelyActiveDistance, LightActiveDistance
Duration	VeryActiveMinutes, FairlyActiveMinutes, LightlyActiveMinutes, SedentaryMinutes
Energy	Calories
Sleep	Minutes asleep, time in bed
Weight	Weight-related fields

Appendix B — SQL Analysis Topics
•	Daily activity cleaning
•	Average steps by weekday
•	Activity segmentation
•	Sleep and activity relationship
•	Highest-calorie days
•	Hourly activity analysis
•	User-level aggregation
Appendix C — Screenshot Placement Guide
Report Section	Screenshot to Insert
Stage 1	SQL cleaning code
Stage 2	Initial Python analysis / chart
Stage 4	SQL query results
Stage 5	Python Matplotlib / Seaborn charts
Stage 6	Streamlit Overview
Stage 6	Activity / Calories / Hourly dashboard
Stage 6	Sleep & Weight dashboard
Stage 6	SQL Analysis
Stage 6	Data Explorer
Stage 7	Final insight visualisation
Submission	Power BI/Tableau dashboard if completed


Prepared for submission
Manjula M • Fitness Data Analytics • 29th  September 2026

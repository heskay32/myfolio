---
date: 2017-04-14T11:25:05-04:00
description: "Big data analysis"
featured_image: "/images/sparklogo.jpg"
tags: ['Big data', 'PySpark', 'Spark RDD', 'MapReduce', 'DBFS']
title: "Analysis of New York Law Enforcement Civil Service Jobs Using Python PySpark"
disable_share: false
---
- Processed data using Map transformation and filters.
- Carried out aggregation using different transfoemation techniques and MapReduce.
- Exploratory Data Analysis.
- Utilized Data Bricks File System(DBFS) as the data storage tool.



## Motivation

The difficulty with recruitment within the law enforcement agency in the United States has caused a significant problem that is broadly affecting the field of law enforcement. The civil service is an independent body that works with the government by providing different services to the people including employment. I have wondered if the police department has enough qualified candidates and if there are available vacancies for qualified candidates. I have used New York City has a case study. 

## Data

I downloaded two active datasets from the NYC Open Data repository.

- **Civil Service List:** Contains information about qualified candidates for certain job types. Each line describes a single candidate and the job that they are qualified for. 
[Link to Data](https://data.cityofnewyork.us/City-Government/Civil-Service-List-Active-/vx8i-nprf)

- **NYC Jobs:** Contains information about current job postings available on the City of New York’s official jobs site.
[Link to Data](https://data.cityofnewyork.us/City-Government/NYC-Jobs/pda4-rgn4/data)

**Questions to be answered**

- How many Candidates qualify for jobs in the police department? And what job types has most qualified candidates?
- What type of job postings are been advertised in the police department.
- Are there vacancies for qualified candidates?

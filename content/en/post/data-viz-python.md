---
date: 2017-04-14T11:25:05-04:00
description: "Big data analysis"
featured_image: "/images/sparklogo.png"
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

## Methods

**Spark:** Apache Spark™ is a multi-language processing engine for executing data engineering, data science, and machine learning on single-node machines or clusters’https://spark.apache.org/

**Resilient Distributed Dataset (RDD):** A fundamental data structure of Apache Spark that allows the storage and processing of data accross clusters. It is fault-tolerant and can be operated in parallel.

I used big data tools(Spark) because Data like the "civil service list" gets updated frequently and can grow to millions of rows over time.RDD optimizes lazy evaluation to increase Spark computational speed

## Questions to be answered

- How many Candidates qualify for jobs in the police department? And what job types has most qualified candidates?
- What type of job postings are been advertised in the police department.
- Are there vacancies for qualified candidates?

## Data Analysis

I uploaded both data to data bricks and performed the analysis on a single node cluster.
I used Spark RDD filter and map transformation to processing the data into shape. I separated the data into columns corresponding to the header before filtering out the header and columns that are not relevant to answering our questions.

Let’s address the first question: *How many Candidates qualify for jobs in the police department*? *And jobs with most qualified candidates*?


![Number of qualified candidates!](/images/count2.png "fig1")

this is figure 3

![Histogram chart of qualified candidates!](/images/fig33.png "fig2")

We can see that out of 576,998 qualified candidates, 10,789 are available for jobs in the police department. However, Police Officer and Sergeant Police has the highest number of candidate.

funfact: 

I also wanted to know *the types of job postings advertised in the police department*?

![Histogram chart of qualified candidates!](/images/fig2.png "fig3")

Most advertised jobs are the ones that are not available to the general public.

**Further Analysis**

*Advertised Positions with most vacancies*

![Histogram chart of qualified candidates!](/images/fig4.png "fig4")

Shockingly, jobs with available vacancies does not correspond to jobs that has high qualified candidates  

And lastly i wanted to know *the number of vacancies available for qualified candidates and jobs that are vacant*.
To achieve this, i joined the two datasets(mor details in Notebook)

![Histogram chart of qualified candidates!](/images/jobcount.png "fig4")

![Histogram chart of qualified candidates!](/images/jobs.png "fig4")
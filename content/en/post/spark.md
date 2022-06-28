---
date: 2022-06-28T11:25:05-04:00
description: "Big data analysis"
featured_image: "/images/sparklogo.png"
tags: ['Big data', 'PySpark', 'Spark RDD', 'MapReduce', 'DBFS']
title: "Analysis of New York Police Department Civil Service Jobs Using Spark"
disable_share: false
---
- Processed data using Map transformation and filters.
- Carried out aggregation using different transformation techniques and MapReduce.
- Exploratory Data Analysis.
- Utilized Data Bricks File System(DBFS) as the data storage tool.



## Motivation

The difficulty with recruitment within the law enforcement agency in the United States has caused a significant problem that is broadly affecting the [police department](https://www.foxnews.com/us/us-police-departments-cops-job-recruitment-anti-cop-climate). The civil service is an independent body that works with the government by providing different services to the people including employment. With the level of increased crime in New York City and the united state generally, i wonder if there are enough people willing to join the police force and if there are available vacancies for them. I have used New York City has a case study. 

## Data

I downloaded two active datasets from the NYC Open Data repository.

- **Civil Service List:** Contains information about qualified candidates for certain job types. Each row describes a single candidate and the job that they are qualified for. 
[Link to Data](https://data.cityofnewyork.us/City-Government/Civil-Service-List-Active-/vx8i-nprf)

- **NYC Jobs:** Contains information about current job postings available on the City of New York’s official jobs site.
[Link to Data](https://data.cityofnewyork.us/City-Government/NYC-Jobs/pda4-rgn4/data)

## Methods

**Spark:** 'Apache Spark™ is a multi-language processing engine for executing data engineering, data science, and machine learning on single-node machines or clusters’[more info](https://spark.apache.org/). Pyspark makes it possible to write spark applications in python.

**Resilient Distributed Dataset (RDD):** A fundamental data structure of Apache Spark that allows the storage and processing of data accross clusters. RDD optimizes lazy evaluation to increase Spark computational speed

I used big data tools(Spark) because Data like the "civil service list" gets updated frequently and can grow to millions of rows over time.

## Questions to be answered

- How many Candidates qualify for civil service jobs in the police department? And which civil service titles has most qualified candidates?
- What type of job postings are been advertised in the police department.
- Are there vacancies for qualified candidates on the civil service list?

## Data Analysis

I uploaded both data to data bricks and performed the analysis on a single node cluster.
I used Spark RDD filter and map transformation to processing the data into shape. I separated the data into columns corresponding to the header before filtering out the header and columns that are not relevant to answering our questions.

Addressing the first question: **How many Candidates qualify for civil service jobs in the police department? And titles with most qualified candidates?**


![Number of qualified candidates!](/images/count2.png "fig1")


![Histogram chart of qualified candidates!](/images/fig33.png "fig2")

We can see that out of 576,998 qualified candidates, 10,789 are available for jobs in the police department. However, Police Officer and Sergeant Police has the highest number of candidate.

**Advertised Positions with most vacancies**

![Histogram chart of Jobs!](/images/fig4.png "fig4")

Shockingly, jobs with available vacancies are not in the top 10 jobs with high number of qualified candidates

**Further Analysis**
 
 *What type of job postings are advertised in the police department?*

![Histogram chart of job postings!](/images/fig2.png "fig3")

Most advertised jobs are the ones that are not available to the general public.

**Number of civil service title available for qualified candidates and jobs that are vacant**.
To achieve this, i joined the two datasets(mor details in Notebook)

![Job list!](/images/jobcount.png "fig4")

![Job listing!](/images/jobs.png "fig4")

Surprisingly only SENIOR POLICE
ADMINISTRATIVE-10147 and ASSOCIATE STAFF ANALYST-12627 civil service titles are available for qualified candidates. However Senior police administrative has more qualified candidates and vacancies.

## Conclusion

From this analysis we can easily see that there is under recruitement in the New York Police department. One would think that Police Officer and sergeant police would have more job postings since they are more needed and has the highest number of qualified candidates, but results shows that the senior police administrative jobs which has less number of qualified candidates has more job vacancies. This may be because most of the available jobs are internal. However, we see that Jobs are not available for most candidates on the civil service list waiting to be assigned a position within the police department. 

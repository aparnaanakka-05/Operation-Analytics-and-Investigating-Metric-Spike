# Operational Analysis and Investigation Metrics Spike  

## Overview  
This repository contains an analytical project using SQL to investigate both *operational efficiency* and *user engagement metrics*.  
The project is divided into two case studies:  

1. *Job Data Analysis* – focusing on throughput, efficiency, and data quality.  
2. *User Engagement Metrics* – focusing on product usage, growth, retention, and email engagement.  

The goal was to transform raw datasets into actionable insights that explain system performance, highlight trends, and measure user behavior over time.  

---

## Objectives  

### Case Study 1: Job Data Analysis  
- Calculate the number of jobs reviewed per hour for each day in November 2020.  
- Compute the seven-day rolling average of throughput.  
- Determine the percentage share of each language over a 30-day period.  
- Identify and display duplicate rows in the job table.  

### Case Study 2: User Engagement Metrics  
- Calculate weekly user engagement.  
- Measure user growth of the product over time.  
- Analyze weekly engagement segmented by device type.  
- Evaluate email engagement metrics (open rates and click-through rates).  
- Measure weekly user retention based on sign-up cohorts.  

---

## Tools and Technologies  
- SQL for querying and analysis  
- PostgreSQL (or your specific database engine)  
- Datasets simulating job data, user activity, and engagement logs  

---

## Approach  

### Case Study 1: Job Data Analysis  
1. Counted jobs reviewed per hour to evaluate throughput.  
2. Applied SQL window functions to calculate seven-day rolling averages.  
3. Aggregated job language data to compute percentage share by language.  
4. Used grouping techniques to detect duplicate rows in the job table.  

### Case Study 2: User Engagement Metrics  
1. Queried weekly active users to track engagement.  
2. Measured product growth by calculating cumulative user sign-ups.  
3. Segmented engagement by device type (web, mobile, etc.).  
4. Computed email engagement metrics such as open and click-through rates.  
5. Performed cohort analysis to track weekly retention of users.  

---

## Sample Queries  

### Case Study 1: Job Data Analysis  
```sql
-- Jobs reviewed per hour for each day in November 2020
SELECT 
    ds,
   COUNT(job_id) / (SUM(time_spent) / 3600)AS daily_throughput
   from 
    job_data
GROUP BY ds
order by ds ;
